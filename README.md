# Mojaloop Overview  
Digital and mobile technologies make it possible to reach new customers in developing markets with innovative, low-cost financial services. The lack of a shared platform, though, means that financial providers have to build everything on their own. This raises costs and keeps the digital financial industry from growing and innovating as fast as it could.  

Mojaloop is open-source software for creating digital payments platforms that connect all customers, merchants, banks, and other financial providers in a country's economy. Rather than a financial product or application in itself, Mojaloop establishes a blueprint for technology that bridges all the financial products and applications in any given market.  

The intention is for financial institutions and commercial providers to use the open-source software to help build digital, interoperable payments platforms that drive financial inclusion on a national scale. Specifically, the platforms will enable seamless, low-cost transactions between individual users, merchants, banks, providers, and even government offices - helping connect poor customers with everyone else in the digital economy.  

Mojaloop grew out of principles set forth by the Financial Services for the Poor team at the Bill & Melinda Gates Foundation. These principles form the cornerstone of the Level One Project, which is the foundation’s initiative for designing and implementing digital financial services and systems to include and benefit the world’s 2 billion unbanked. The code won’t address the gap in digital financial services on its own, but it can help service providers open markets and accelerate progress. 

With support and funding from the Bill & Melinda Gates Foundation, Mojaloop was designed by a team of leading tech and fintech companies: [Ripple](https://github.com/ripple), [Dwolla](https://github.com/dwolla), [ModusBox](http://www.modusbox.com/), [Software Group](http://www.softwaregroup-bg.com/) and [Crosslake Technologies](http://www.crosslaketech.com/). It is available now as an open-source project. Free to be used and adapted by anyone under the [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0). For more information on how Mojaloop ties into the larger initative of finanical inclusion, visit [LevelOneProject.org](https://leveloneproject.org/).

## Why should I contribute to Mojaloop?
Mojaloop makes it easier for financial providers and entrepreneurs to go to market with products and services, especially in developing markets where demand is high and supply is low.  

A nationwide interoperable digital payments platform requires really good code. Your contributions will help ensure that Mojaloop covers all the bases, translates well to real-world scenarios, and meets the many and diverse needs of financial providers and customers.  

## Getting Started
The project is in GitHub and is organized on the basis of component microservices.  As such, there are over twenty different repositories in GitHub that align to the different services.  The _Docs_ repository documents the overall architecture, component design, message flow, and an overview of Mojaloop. Individual repositories in the [Mojaloop GitHub organization](https://github.com/mojaloop/) each describe component-specific details including source and APIs.

The source code can be found in the interop-devops repository [release folder].(https://github.com/mojaloop/interop-devops/releases)

New developers, see the [contributors guide](./contribute.md) for onboarding materials.
For additional infromation please review the [frequently asked questions](/FAQ.md).

For more information please download and review our pdf's:
[Comprehensive documentation](https://github.com/mojaloop/docs/blob/master/Mojaloop_Comprehensive_Documentation.pdf)
or
[Developers guide](https://github.com/mojaloop/docs/blob/master/Mojaloop_Developer_Onboarding.pdf).

## Mojaloop Services
The following architecture diagram shows the Mojaloop services:
![Mojaloop Services](https://github.com/mojaloop/docs/blob/master/Wiki/Basic%20Overview.png)

The basic idea behind Mojaloop is that we need to connect multiple Digital Financial Services Providers (DFSPs) together into a competitive and interoperable network in order to maximize opportunities for poor people to get access to financial services with low or no fees. We don't want a single monopoly power in control of all payments in a country, or a system that shuts out new players. It also doesn't help if there are too many isolated subnetworks. Our model addresses these issues in several key ways:

- A set of central services provides a hub through which money can flow from one DFSP to each other. This is similar to how money moves through a central bank or clearing house in developed countries. Besides a central ledger, central services can provide identity lookup, fraud management, and enforce scheme rules.
- A standard set of interfaces a DFSP can implement to connect to the system, and example code that shows how to use the system. A DFSP that wants to connect up can adapt our example code or implement the standard interfaces into their own software. The goal is for it to be as straightforward as possible for a DFSP to connect to the interoperable network.
- Complete working open-source implementations of both sides of the interfaces - an example DFSP that can send and receive payments and the client that an existing DFSP could host to connect to the network.


## Related Projects
The [Interledger Protocol Suite](https://interledger.org/) (ILP) is an open and secure standard that enables DFSPs to settle payments with minimal _counter-party risk_ (the risk you incur when someone else is holding your money). With ILP, you can transact across different systems with no chance that someone in the middle disappears with your money. Mojaloop uses the Interledger Protocol Suite for the clearing layer. For an overview of how it works, see the [Clearing Architecture Documentation](https://github.com/mojaloop/Docs/blob/master/ILP/README.md).
