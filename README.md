# Getting Started
The Mojaloop project is organized on the basis of component microservices.  As such, there are over twenty different repositories in GitHub that align to the different services.  The following six repositories are pinned to the project:
- The [Mojaloop repository](https://github.com/mojaloop/mojaloop) contains this master readme file along with the following documents to get started.
  * [contributors guide](./contribute.md) for development and installation materials.
  * [requirements guide](./requirements.md) for Mojaloop requirements.
  * [frequently asked questions](/FAQ.md).
- The [interop-devops repository](https://github.com/mojaloop/interop-devops) contains the necessary source code to setup the project.
- The [helm repository](https://github.com/mojaloop/helm) contains the packaging format called charts which is a collection of files that describe a related set of Kubernetes resources for the Mojaloop project. 
- The [docs repository](https://github.com/mojaloop/docs) documents the overall architecture, component design, message flow, and an overview of Mojaloop. 
- The [project repository](https://github.com/mojaloop/project) is the cetnral repostiorty to track product development issues for the Mojaloop project.
- The [mojaloop-specificiation](https://github.com/mojaloop/mojaloop-specification) contains the specification document set of the Open API for Financial Service Provider Interoperability. 

- Individual repositories in the [Mojaloop GitHub organization](https://github.com/mojaloop/) each describe component-specific details including source and APIs.

For the full documentation contained with the markdown files within this project you can view, download and review our pdf's:
[Comprehensive documentation](https://github.com/mojaloop/docs/blob/master/Mojaloop_Comprehensive_Documentation.pdf)
or
[Developers guide](https://github.com/mojaloop/docs/blob/master/Mojaloop_Developer_Onboarding.pdf).

# Mojaloop Overview  

[![Join the chat at https://gitter.im/mojaloop/mojaloop](https://badges.gitter.im/mojaloop/mojaloop.svg)](https://gitter.im/mojaloop/mojaloop?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
Digital and mobile technologies make it possible to reach new customers in developing markets with innovative, low-cost financial services. The lack of a shared platform, though, means that financial providers have to build everything on their own. This raises costs and keeps the digital financial industry from growing and innovating as fast as it could.  

Mojaloop is open-source software for creating digital payments platforms that connect all customers, merchants, banks, and other financial providers in a country's economy. Rather than a financial product or application in itself, Mojaloop establishes a blueprint for technology that bridges all the financial products and applications in any given market.  

The intention is for financial institutions and commercial providers to use the open-source software to help build digital, interoperable payments platforms that drive financial inclusion on a national scale. Specifically, the platforms will enable seamless, low-cost transactions between individual users, merchants, banks, providers, and even government offices - helping connect poor customers with everyone else in the digital economy.  

Mojaloop grew out of principles set forth by the Financial Services for the Poor team at the Bill & Melinda Gates Foundation. These principles form the cornerstone of the Level One Project, which is the foundation’s initiative for designing and implementing digital financial services and systems to include and benefit the world’s 2 billion unbanked. The code won’t address the gap in digital financial services on its own, but it can help service providers open markets and accelerate progress. 

With support and funding from the Bill & Melinda Gates Foundation, Mojaloop was designed by a team of leading tech and fintech companies: [Ripple](https://github.com/ripple), [Dwolla](https://github.com/dwolla), [ModusBox](http://www.modusbox.com/), [Software Group](http://www.softwaregroup-bg.com/) and [Crosslake Technologies](http://www.crosslaketech.com/). It is available now as an open-source project. Free to be used and adapted by anyone under the [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0). For more information on how Mojaloop ties into the larger initative of finanical inclusion, visit [LevelOneProject.org](https://leveloneproject.org/).

## Why should I contribute to Mojaloop?
Mojaloop makes it easier for financial providers and entrepreneurs to go to market with products and services, especially in developing markets where demand is high and supply is low.  

A nationwide interoperable digital payments platform requires really good code. Your contributions will help ensure that Mojaloop covers all the bases, translates well to real-world scenarios, and meets the many and diverse needs of financial providers and customers.  


## Mojaloop Services
The following architecture diagram shows the Mojaloop services:
![Mojaloop Services](https://github.com/mojaloop/docs/blob/master/Wiki/Mojaloop%20Services%20Overview.png)

The basic idea behind Mojaloop is that we need to connect multiple Digital Financial Services Providers (DFSPs) together into a competitive and interoperable network in order to maximize opportunities for poor people to get access to financial services with low or no fees. We don't want a single monopoly power in control of all payments in a country, or a system that shuts out new players. It also doesn't help if there are too many isolated subnetworks. Our model addresses these issues in several key ways:

- A set of central services provides a hub through which money can flow from one DFSP to another. This is similar to how money moves through a central bank or clearing house in developed countries. Besides a central ledger, central services can provide identity lookup, fraud management, and enforce scheme rules.
- A standard set of interfaces a DFSP can implement to connect to the system, and example code that shows how to use the system. A DFSP that wants to connect up can adapt our example code or implement the standard interfaces into their own software. The goal is for it to be as straightforward as possible for a DFSP to connect to the interoperable network.
- Complete working open-source implementations of both sides of the interfaces - an example DFSP that can send and receive payments and the client that an existing DFSP could host to connect to the network.

## What's here and what's not
This is free code provided under an [Apache 2.0 license](https://github.com/mojaloop/mojaloop/blob/master/LICENSE.md). We don't provide production servers to run it on. That's up to you. You are free (and encouraged!) to clone these repositories, participate in the community of developers, and contribute back to the code.

We are not trying to replace any mobile wallet or financial providers. We provide code to link together new and existing financial providers using a common scheme. There are central services for identifying a customer's provider, quoting, fulfillment, deferred net settlement, and shared fraud management. Each provider can take advantage of these services to send and receive money with others on the system and there's no cost to them to onboard new providers. We provide code for a simple example mobile money provider to show how integration can be done, but our example DFSP is not meant to be a production mobile money provider.

## Related Projects
The [Interledger Protocol Suite](https://interledger.org/) (ILP) is an open and secure standard that enables DFSPs to settle payments with minimal _counter-party risk_ (the risk you incur when someone else is holding your money). With ILP, you can transact across different systems with no chance that someone in the middle disappears with your money. Mojaloop uses the Interledger Protocol Suite for the clearing layer. For an overview of how it works, see the [Clearing Architecture Documentation](https://github.com/mojaloop/Docs/blob/master/ILP/README.md).

Repositories for Docker containers, NPM packages, etc. are provided by JFrog

![Artifactory](https://github.com/mojaloop/docs/blob/master/Wiki/Powered-by-artifactory_02.png)
