# Onboarding Developers
The [Mojaloop](https://mojaloop.io/) site describes what we're accomplishing.

We use a [standard developer code of conduct](https://www.contributor-covenant.org/version/1/4/code-of-conduct.html)

## How do I start working with Mojaloop
1)	Review the Readme.md, contributor.md and FAQ.md guides in GitHub
* The Docs repository in GitHub includes the overall architecture, component design, message flow, and an overview of the Mojaloop software
* Individual repositories within the GitHub project each describe component-specific details including source and APIs

A)	To Setup a local Cloan: Follow the setup instructions using Vagrant on your local environment in the [readme.md](https://github.com/mojaloop/interop-devops/blob/master/README.md) in the interop-devops repository. 

B) To Setup the Mojaloop Central Ledger: Follow the setup instructions detailed in the [onboarding.md](https://github.com/mojaloop/central-ledger/blob/develop-PI3/Onboarding.md).

C) To Setup Kubernetes to run the Central Ledger: Follow the setup instructions detailed in the [kubernetes.md](https://github.com/mojaloop/central-ledger/blob/develop-PI3/KUBERNETES.md).

* Do some work; Fix a bug, pick up an issue; Remember to write good commit messages

* Create the pull request in GitHub; At this point someone from the maintainers team will review and approve or push back on your request

## External Developer Tools 
(See [Tools Choices](https://github.com/mojaloop/Docs/wiki/Tools,-technology,-and-process-choices) for a longer list that includes the reasoning behind each)
* Shipping docs and code are in GitHub at https://github.com/Mojaloop.
* [GitHub Wiki search bar](https://chrome.google.com/webstore/detail/wiki-search-for-github/gdifdhnjmjaidbajhapmbcbnoocoeooc) This is a Chrome extension that adds a search for the GitHub Wiki. Not a required tool, but useful.
* Continuous Integration is via [CircleCI](https://circleci.com/gh/Leveloneproject)
* Hosting is via AWS, using and AWS VPC. See [test machine info](https://github.com/mojaloop/Docs/blob/master/AWS/Infrastructure/machines.md)
* Docker is used for packaging and deployment and hosts the registry of docker packages. Typically using an [Alpine Linux base image](https://alpinelinux.org/)
* JFrog hosts our package repositories for Docker, Maven, and NodeJS. These should be made public soon.
