# Onboarding Developers
The [Mojaloop](https://mojaloop.io/) site describes what we're accomplishing.

We use a [standard developer code of conduct](https://www.contributor-covenant.org/version/1/4/code-of-conduct.html)

## External Developer Tools 
(See [Tools Choices](https://github.com/mojaloop/docs/decisions.md) for a longer list that includes the reasoning behind each)
* Shipping docs and code are in GitHub at https://github.com/Mojaloop.
* [GitHub Wiki search bar](https://chrome.google.com/webstore/detail/wiki-search-for-github/gdifdhnjmjaidbajhapmbcbnoocoeooc) This is a Chrome extension that adds a search for the GitHub Wiki. Not a required tool, but useful.
* Continuous Integration is via [CircleCI](https://circleci.com/gh/Leveloneproject)
* Hosting is via AWS, using and AWS VPC
* Docker is used for packaging and deployment and hosts the registry of docker packages. Typically using an [Alpine Linux base image](https://alpinelinux.org/)
* JFrog hosts our package repositories for Docker, Maven, and Node.js. These should be made public soon.

## How do I start working with Mojaloop
1)	Review the Readme.md, contributor.md and FAQ.md guides in GitHub
* The Docs repository in GitHub includes the overall architecture, component design, message flow, and an overview of the Mojaloop software
* Individual repositories within the GitHub project each describe component-specific details including source and APIs
2)	Before you start working with Mojaloop it is recommend that you review the details under the contribute folder with specific emphasis on the roadmap.md
3)	Once you are ready to contribute to Mojaloop it is recommended that you follow GitHub fundamentals:

* Setup a local clone of the project locally; To perform a local setup, follow the setup instructions using Vagrant on your local environment in the [readme.md](https://github.com/mojaloop/interop-devops/blob/master/README.md) in the interop-devops repository. 

* Do some work; Fix a bug, pick up an issue; Remember to write good commit messages

* Create the pull request in GitHub; At this point someone from the maintainers team will review and approve or push back on your request