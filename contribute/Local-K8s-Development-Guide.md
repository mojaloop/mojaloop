# Kubernetes Development Guide

Development Guide for Mojaloop on a local Kubernetes installation via Minikube.

## Local Minikube Deployment
### Setup local Kubernetes environment
1. Install VirtualBox
    
    Refer to: https://www.virtualbox.org/wiki/Downloads

2. Install Docker
    
    MacOS: `brew install docker`

3. Install Kubectl
    
    MacOS: `brew install kubectl`

4. Install Minikube
    
    MacOS: `brew cask install minikube`

5. Install Helm
    
    MacOS: `brew install kubernetes-helm`

6. Initialise MiniKube
    
    `minikube start`

7. Initialise Helm
    
    `helm init` 

8. Get your Minikube IP address

    `minikube ip`

9. Update your /etc/hosts file with the following entry inserting your minikube IP from the last step

    `<minikube-ip> central-kms.local forensic-logging-sidecar.local central-ledger.local central-end-user-registry.local central-directory.local central-hub.local`

### Setup Helm Charts for deployment

10. Clone Helm repo

    `git clone git@github.com:mojaloop/helm.git`

11. Change to helm repo directory

    `cd helm`
   
12. Switch to develop branch
    git checkout -b origin/develop
    git pull origin develop

13. Update all dependencies

    `sh ./update-charts-dep.sh`

### Deploy Ingress
14. Deploy Ingress Nginx via Helm

    `helm install --namespace=kube-public --name=minikube -f ./config-ingress.yaml ./kube-public/ingress-nginx`

### Deploy Central

14. Deploy Central via Helm

    `helm install --namespace=mojaloop --name=dev -f ./config-central.yaml ./central`

### Test Deployments

15. Refer to `Testing Deployments` Section in the `README.MD` of https://github.com/mojaloop/helm.


## Local Minikube Development

### A.) Using a local Docker registry for development

#### Scenario:

A developer wants to test an enhancement for the Central Ledger Admin API which is running on the Minikube Kubernetes node against all down-stream dependencies to return `OK HELLOWORLD!` instead of `OK` on the /health probe.

#### Steps:

1. Enable the docker registry on your Kubernetes cluster

    Run the following command:

    `minikube addons enable registry`

2. Create a Service to your registry:

    Run the following command:

    `cat <<EOF | kubectl create -f -
    {
    "kind": "Service",
    "apiVersion": "v1",
    "metadata": {
        "name": "registry-nodeport",
        "namespace": "kube-system",
        "labels": {
        "addonmanager.kubernetes.io/mode": "Reconcile",
        "kubernetes.io/minikube-addons": "registry"
        }
    },
    "spec": {
        "ports": [
        {
            "protocol": "TCP",
            "port": 5000,
            "nodePort": 31555
        }
        ],
        "selector": {
        "kubernetes.io/minikube-addons": "registry"
        },
        "type": "NodePort"
    }
    }
    EOF`

    This will create a service to the registry on port `31555`.

3. Test that your Registry is working:

    Run the following command:

    `curl $(minikube service --url -n kube-system registry-nodeport)/v2/_catalog`

    Expected output:

    `{"repositories":[]}`

4. Determine your Minikube Registry details

    Run the following command:

    `echo "$(minikube service --url --format "{{.IP}}" -n kube-system registry-nodeport):$(minikube service --url --format "{{.Port}}" -n kube-system registry-nodeport)"`

    This will display the following information:

    `<IP>`:`<PORT>` e.g. `192.168.99.100:31555`

5. Add the Insecure Registry to your Docker preferences:

    If you’re using Mac OSX Docker client:

    - Go to `Docker` -> `Daemon` -> `Basic` -> `Insecure registries`

    - Add to the list: `<IP>:<PORT>`

    - Restart Docker


    If you’re using a Linux distribution:

    - Open file `/etc/sysconfig/docker`

    - Add `INSECURE_REGISTRY="--insecure-registry=<insecure-docker-hub-hostname> "`

    - Restart Docker


6. Edit your Minikube config to accept your Insecure Docker Registry:

    Edit the following file:

    `vi $HOME/.minikube/machines/minikube/config.json`

    Add your \<IP>:\<PORT> into the `InsecureRegistry` list:
    ``` JSON
    "HostOptions": {
        "Driver": "",
        "Memory": 0,
        "Disk": 0,
        "EngineOptions": {
            "ArbitraryFlags": null,
            "Dns": null,
            "GraphDir": "",
            "Env": null,
            "Ipv6": false,
            "InsecureRegistry": [
                "10.0.0.0/24",
                "<IP>:<PORT>"
            ],
    ```

    Save the changes and restart your Minikube server:

    `minikube stop; minikube start`

7. Modify the code

    `vi ./src/admin/root/routes.js`
    
    Modify the /health route response from `OK` to `OK HELLOWORLD!` as follows:

    ``` JSON   
    {
        method: 'GET',
        path: '/health',
        handler: (request, reply) => reply({ status: 'OK HELLOWORLD!' }).code(200),
        config: RouteConfig.config(tags, 'Status of ledger admin api')
    }
    ```

8. Build your docker image

    Modify the following parameters in the command below: 
    - `<IMAGE_NAME>`
    - `<IMAGE_TAG>`

    Run the following command:

    `docker build -t $(minikube service --url --format "{{.IP}}" -n kube-system registry-nodeport):$(minikube service --url --format "{{.Port}}" -n kube-system registry-nodeport)/<IMAGE_NAME>:<IMAGE_TAG> .`

    This will automagically add the required registry references to the docker image with the following name format: `<REGISTRY_IP>:<REGISTRY_PORT>/<IMAGE_NAME>:<IMAGE_TAG>`

    Verify this by running the following command:

    `docker images | grep <IMAGE_NAME> | grep <IMAGE_TAG>`

9. Push the image to the Docker Repo

    Modify the following parameters in the command below: 
    - `<IMAGE_NAME>`
    - `<IMAGE_TAG>`

    Run the following command:

    `docker push $(minikube service --url --format "{{.IP}}" -n kube-system registry-nodeport):$(minikube service --url --format "{{.Port}}" -n kube-system registry-nodeport)/<IMAGE_NAME>:<IMAGE_TAG>`

    Verify that the image was pushed successfully:

    `curl $(minikube service --url -n kube-system registry-nodeport)/v2/_catalog`

    Expected output:

    `{"repositories":["<IMAGE_NAME>"]}`

    This will publish the Docker Image to the Docker Repo.

10. Edit the Helm `values.yaml` file of an existing Helm release (`<HELM_RELEASE_NAME>`) modifying the `repository` and `tag`

    ``` YAML
    repository: <IP>:<PORT>/<IMAGE_NAME>
    tag: <IMAGE_TAG>
    ```

11. Upgrade your Helm deployment

    `helm upgrade <HELM_RELEASE_NAME> <CHART_DIR>`
    
### B.) Hi-jacking services for local development

#### Scenario:

A developer wants to work on an enhancement for the Central Ledger Admin API which is running against all down-stream dependencies to return `OK HELLOWORLD!` instead of `OK` on the /health probe.

#### Steps:

1. Clone the latest code:
    - `git clone git@github.com:mojaloop/central-ledger.git`
    - `git clone git@github.com:mojaloop/helm.git`

2. Configure `values.yaml` for External Service enablement
    - `cd <HELM_REPO_DIR>`
    - `vi ./config-central.yaml`
        - enabled External Service: `service.external.enabled: true`
        - update the external IP: `service.external.ip: 10.0.2.2`
        - update the external Port for API: `service.external.ports.api.externalPort: 3000`
        - update the external Port for ADMIN API: `service.external.ports.admin.externalPort: 3001`

3. Deploy Central-Ledger
    - `cd <HELM_REPO_DIR>`
    - `sh ./update-charts-dep.sh`
    - `helm install --namespace=mojaloop --name=dev ./centralledger`

4. Expose dependant services running on Kubernetes on the localhost
    - Open a new terminal and run the following command to expose the Central-Ledger Database:
        - `kubectl --namespace=mojaloop port-forward $(kubectl get pods --namespace mojaloop -l "app=dev-centralledger-postgresql" -o jsonpath="{.items[0].metadata.name}") 5432:5432`
    - Open a new terminal and run the following comman to expose the Forensic Logging Sidecar service:
        - `kubectl --namespace=mojaloop port-forward $(kubectl get pods --namespace mojaloop -l "app=forensicloggingsidecar-ledger" -o jsonpath="{.items[0].metadata.name}") 5678:5678`

5.  Configure Central-Ledger Sidecar
    - `cd <CENTRAL_LEDGER_REPO_DIR>`
    - `vi ./config/default.json`
        - Ensure that the `SIDECAR.HOST` and `SIDECAR.PORT` are configured as follows: 
        ``` JSON
        {
            "PORT": 3000,
            "ADMIN_PORT": 3001,
            "HOSTNAME": "http://central-ledger.local",
            "ENABLE_TOKEN_AUTH": false,
            "ENABLE_BASIC_AUTH": false,
            "LEDGER_ACCOUNT_NAME": "LedgerName",
            "LEDGER_ACCOUNT_PASSWORD": "LedgerPassword",
            "AMOUNT": {
                "PRECISION": 10,
                "SCALE": 2
            },
            "SIDECAR": {
                "DISABLED": false,
                "HOST": "localhost",
                "PORT": 5678,
                "CONNECT_TIMEOUT": 45000,
                "RECONNECT_INTERVAL": 5000
            }
        }
        ```

6. Configure Central-Ledger Database environment variable
    - `export CLEDG_DATABASE_URI=postgres://central_ledger:$(kubectl get secret --namespace mojaloop centralledgerdb-postgresql -o jsonpath="{.data.postgres-password}" | base64 --decode; echo)@localhost:5432/central_ledger` 

7. Run the Central-Ledger Service
    - `cd <CENTRAL_LEDGER_REPO_DIR>`
    - `vi ./src/admin/root/routes.js`
        - Modify the /health route response from `OK` to `OK HELLOWORLD!` as follows:
        ``` JSON   
        {
            method: 'GET',
            path: '/health',
            handler: (request, reply) => reply({ status: 'OK HELLOWORLD!' }).code(200),
            config: RouteConfig.config(tags, 'Status of ledger admin api')
        }
        ```
    - Run the Admin API: 
        - `node ./src/admin/index.js`

8. Test Central-Ledger Admin Service is connected to DB:
    - Local direct: `curl http://localhost:3001/accounts`
    - Ingress: `curl http://central-ledger.local/admin/accounts`
        
        Expected Output:
        ``` JSON 
        [
            {
                "name": "LedgerName",
                "id": "http://central-ledger.local/accounts/LedgerName",
                "created": "2017-12-19T09:42:25.107Z",
                "is_disabled": false,
                "_links": {
                    "self": "http://central-ledger.local/accounts/LedgerName"
                }
            }
        ]
        ```

9. Test Central-Ledger Admin Service health enhancement:
    - Local direct: `curl http://localhost:3001/health`
    - Ingress: `curl http://central-ledger.local/admin/health`
     
        Expected Output:
        ``` JSON 
        {
            "status": "OK HELLOWORLD!"
        }
        ```

### C.) Hi-jacking services for local development

#### Scenario:

A developer wants to work on an enhancement for the Central Ledger Admin API which is running against all up-stream down-stream dependencies. The developer wants to access the Central Ledger capabilities via the Central Hub (and its dependencies) which is running on the Minikube Kubernetes node.

#### Steps:

1. Clone the latest code:
    - `git clone git@github.com:mojaloop/central-ledger.git`
    - `git clone git@github.com:mojaloop/helm.git`

2. Configure `values` for External Service enablement
    - `cd <HELM_REPO_DIR>`
    - `vi ./config-central.yaml`
        - enabled External Service: `centralhub.centralledger.service.external.enabled: true`
        - update the external IP: `centralhub.centralledger.service.external.ip: 10.0.2.2`
        - update the external Port for API: `centralhub.centralledger.service.external.ports.api.externalPort: 3000`
        - update the external Port for ADMIN API: `centralhub.centralledger.service.external.ports.admin.externalPort: 3001`

3. Deploy Central-Ledger
    - `cd <HELM_REPO_DIR>`
    - `sh ./update-charts-dep.sh`
    - `helm install --namespace=mojaloop --name=dev ./central`

4. Same steps from section #B.4 to #B.9

5. Confirm that Central Hub is hitting your local Central Ledger ADMIN API
    - `curl http://central-ledger/admin/health`
        
             
        Expected curl command Output:
        ``` JSON 
        {
            "status": "OK HELLOWORLD!"
        }
        ```

        Expected output in Central Ledger log file:
        
        `2017-12-20T09:19:08.628Z - info: L1p-Trace-Id=7a707ac8-bcd5-44ec-9582-3ae707780872 - Response: {"status":"OK"} Status: 200` 

    - Open the following URL in your web page: http://central-hub.local/members

        Expected output in Central Ledger log file:

        `2017-12-20T09:19:46.187Z - info: L1p-Trace-Id=0c8cbda4-4b71-4f3c-80c0-13a918281ec2 - Method: get Path: /accounts?token=some-token Query: {"token":"some-token"}`

        `2017-12-20T09:19:46.187Z - info: L1p-Trace-Id=0c8cbda4-4b71-4f3c-80c0-13a918281ec2 - Headers: {"host":"central-hub.local","connection":"close","x-real-ip":"192.168.99.1","x-forwarded-for":"192.168.99.1","x-forwarded-host":"central-hub.local","x-forwarded-port":"80","x-forwarded-proto":"http","x-original-uri":"/api/accounts","x-scheme":"http","user-agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_2) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.108 Safari/537.36","accept":"*/*","referer":"http://central-hub.local/members","accept-encoding":"gzip,deflate","accept-language":"en-US,en;q=0.9","traceid":"0c8cbda4-4b71-4f3c-80c0-13a918281ec2"}`

        `2017-12-20T09:19:46.200Z - info: L1p-Trace-Id=0c8cbda4-4b71-4f3c-80c0-13a918281ec2 - Response: [{"name":"LedgerName","id":"http://central-ledger/accounts/LedgerName","created":"2017-12-20T09:19:09.646Z","is_disabled":false,"_links":{"self":"http://central-ledger/accounts/LedgerName"}}] Status: 200`
