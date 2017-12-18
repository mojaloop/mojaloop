# K8s Development Guide

Development Guide for Mojaloop on a local Kubernetes installation via Minikube.

Refer to the following git repo for more information on running Mojaloop on Kubernetes: https://github.com/mojaloop/helm
## Local Minikube Deployment
### Setup local K8s environment
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

### Test Deplyoments

15. Refer to `Testing Deployments` Section in the `README.MD` of https://github.com/mojaloop/helm.


## Local Minikube Development

### Setup local registry for development

1. Enable the docker registry on your K8s cluster

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

7. Build your docker image

Modify the following parameters in the command below: 
- `<IMAGE_NAME>`
- `<IMAGE_TAG>`

Run the following command:

`docker build -t $(minikube service --url --format "{{.IP}}" -n kube-system registry-nodeport):$(minikube service --url --format "{{.Port}}" -n kube-system registry-nodeport)/<IMAGE_NAME>:<IMAGE_TAG> .`

This will automagically add the required registry references to the docker image with the following name format: `<IP>:<PORT>/<IMAGE_NAME>:<IMAGE_TAG>`

Verify this by running the following command:

`docker images | grep <IMAGE_NAME> | grep <IMAGE_TAG>`

8. Push the image to the Docker Repo

Modify the following parameters in the command below: 
- `<IMAGE_NAME>`
- `<IMAGE_TAG>`

Run the following command:

`docker push $(minikube service --url --format "{{.IP}}" -n kube-system registry-nodeport):$(minikube service --url --format "{{.Port}}" -n kube-system registry-nodeport)/<IMAGE_NAME>:<IMAGE_TAG>`

Verify that the image was pushed succesfully:

`curl $(minikube service --url -n kube-system registry-nodeport)/v2/_catalog`

Expected output:

`{"repositories":["<IMAGE_NAME>"]}`

This will publish the Docker Image to the Docker Repo.

9. Edit the Helm `values.yaml` file of an existing Helm release (`<RELEASE_NAME>`) modifying the `repository` and `tag`

``` YAML
    repository: <IP>:<PORT>/<IMAGE_NAME>
    tag: <IMAGE_TAG>
```

10. Upgrade your Helm deployment

`helm upgrade <RELEASE_NAME> <CHAR_DIR>`
