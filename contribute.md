# What is this?  
We're sharing code to help create interoperable payments platforms that can be deployed on a national scale. The idea is to make it easier for financial providers to deliver digital financial services to new customers in new markets, especially in the developing world. See our [README.md](https://github.com/mojaloop/mojaloop/blob/master/README.md) for an overview, or visit [mojaloop.io](http://mojaloop.io) for context and information.

# How do I contribute?
## Local Development Setup
Steps to setup your local enviroment to contibute to the Mojaloop project:
1) Central Ledger Setup: To setup the Mojaloop Central Ledger on your local machine follow the instructions detailed in the [onboarding.md](https://github.com/mojaloop/central-ledger/blob/develop-PI3/Onboarding.md).

2) Kubernetes Setup: To setup Kubernetes to run the Central Ledger follow the setup instructions detailed in the [kubernetes.md](https://github.com/mojaloop/central-ledger/blob/develop-PI3/KUBERNETES.md).

# What work is needed?
Work is tracked as issues in GitHub. You'll see issues there that are open and marked as bugs, stories, or epics. An epic is larger work that contains multiple stories. Anything that is in the backlog and not assigned to someone are things we could use help with. Stories that have owners are in someone's backlog already, though you can always ask about them in the issue or on Slack. 

There's a [roadmap](https://github.com/mojaloop/mojaloop/blob/master/contribute/Roadmap.md) that shows larger work that people could do or are working on. It has some main initiatives and epics and the order, but lacks dates as this work is community driven. Work is broken down from there into issues in GitHub.

In general, we are looking for example implementations and bug fixes, and project enhancements. 

## Where do I get help?
Join the [Mojaloop #General Channel](https://mojaloop-slack.herokuapp.com/) to connect with other developers.

Also checkout the [FAQ](https://github.com/mojaloop/mojaloop/blob/master/FAQ.md)

## Where to I send bugs, questions, and feedback?
For bugs, see [Reporting bugs](https://github.com/mojaloop/mojaloop/blob/master/contribute/Reporting-Bugs.md). 


## Pull Request Process
It's a good idea to ask about major changes on [Slack](https://mojaloop.slack.com). Submit pull requests which include both the change and the reason for the change. Pull requests will be denied if they violate the [Level One Principles](https://leveloneproject.org/wp-content/uploads/2016/03/L1P_Level-One-Principles-and-Perspective.pdf)


## Style guides and templates
- [Documentation standards](https://github.com/mojaloop/mojaloop/blob/master/contribute/Documentation-and-Template-Standards.md)
- [Documentation style guide](https://github.com/mojaloop/mojaloop/blob/master/contribute/Documentation-Style-Guide.md)
- [Code Style](https://github.com/mojaloop/mojaloop/blob/master/contribute/Code-Style.md)
- [Code Quality Metrics](https://github.com/mojaloop/mojaloop/blob/master/contribute/Code-Quality-Metrics.md)


## Code of conduct
We use a [standard developer code of conduct](https://www.contributor-covenant.org/version/1/4/code-of-conduct.html)

## Licensing
See [License](https://github.com/mojaloop/mojaloop/blob/master/contribute/License.md) policy

## External Developer Tools 
(See [Tools Choices](https://github.com/mojaloop/Docs/wiki/Tools,-technology,-and-process-choices) for a longer list that includes the reasoning behind each)
* Shipping docs and code are in GitHub at https://github.com/Mojaloop.
* [GitHub Wiki search bar](https://chrome.google.com/webstore/detail/wiki-search-for-github/gdifdhnjmjaidbajhapmbcbnoocoeooc) This is a Chrome extension that adds a search for the GitHub Wiki. Not a required tool, but useful.
* Continuous Integration is via [CircleCI](https://circleci.com/gh/Leveloneproject)
* Hosting is via AWS, using and AWS VPC. See [test machine info](https://github.com/mojaloop/Docs/blob/master/AWS/Infrastructure/machines.md)
* Docker is used for packaging and deployment and hosts the registry of docker packages. Typically using an [Alpine Linux base image](https://alpinelinux.org/)
* JFrog hosts our package repositories for Docker, Maven, and NodeJS. These should be made public soon.

## What version?
Naturally, we use [semantic versioning](http://semver.org/), and each repo has it's own version.
Update the version appropriately when you submit a pull request. 

Example: git tag v0.4.0 # update the version.

## Additional Information
For additional information please review the [frequently asked questions](/FAQ.md).
