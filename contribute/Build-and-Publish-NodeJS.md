# Publishing to the Private Repo
See the [DeployTest](https://github.com/mojaloop/deploytest) repo for example code

There are three files you need for build/deploy in CircleCI

**package.json**

    "name": "@Mojaloop/YourRepoName",  
    "license": "SEE LICENSE IN LICENSE",  
  
The package is identified with the Mojaloop organization name and License file.

**CirceCI.yml**

    machine:  
      node:  
        version: 6.5.0  
	
    deployment:  
      releases:  
        branch: master  
      commands:  
        - npm publish  

The CircleCI file defines the version of Node to use and when to publish to the repo (typically from a push to master branch).

**.npmrc**

    registry=https://modusbox.jfrog.io/modusbox/api/npm/level1-npm-release
    _auth = ${NPM_TOKEN}
    email = ${NPM_EMAIL}
    always-auth = true

The .npmrc file for the repo defines where the private npm package repo is, the authorization token to write to it and the email to notify. To test that publishing works locally, you'll run _npm publish_. You'll want a local .npmrc file at cd ~ that defines the real values for your email and the auth token. [Here are instructions to get the auth token](https://docs.npmjs.com/private-modules/ci-server-config#getting-an-authentication-token).

CircleCI doesn't have your local environment variables so you have to add the email and auth token to it. Use the UI at
https://circleci.com/gh/mojaloop/YourRepoNameHere/edit#env-vars to add the two variables. 

Your account will need full read and write access to your private npm repo. 

See more info at [Adding a new project into CircleCI](https://github.com/mojaloop/docs/blob/master/DevOps/CircleCi.md)

# Installing from the Private Repo
So, you have another repo that takes a dependency on the package you've published...in order to npm install from the private repo you need a few pieces in the package.json

    "repository": {
       "type": "git",
       "url": "git@github.com:Mojaloop/thecurrentrepo.git"
     },
     "dependencies": {
        "@Mojaloop/thepackageyoupublished": "^0.1.0"
     },
     "publishConfig": {
        "registry": "https://modusbox.jfrog.io/modusbox/api/npm/level1-npm-release"
     }
