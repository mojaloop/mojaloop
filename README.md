_Note: The name of the code will soon be updated to "Mojaloop." The code itself will remain the same._

# Level One Project Overview  
Digital and mobile technologies make it possible to reach new customers in developing markets with innovative, low-cost financial services. The lack of a shared platform, though, means that financial providers have to build everything on their own. This raises costs and keeps the digital financial industry from growing and innovating as fast as it could.  

Level One Project is open-source software for creating digital payments platforms that connect all customers, merchants, banks, and other financial providers in a country’s economy. Rather than a financial product or application in itself, Level One Project establishes a blueprint for technology that bridges all the financial products and applications in any given market.  

The intention is for financial institutions and commercial providers to use the open-source software to help build digital, interoperable payments platforms that drive financial inclusion on a national scale. Specifically, the platforms will enable seamless, low-cost transactions between individual users, merchants, banks, providers, and even government offices—helping connect poor customers with everyone else in the digital economy.  

Level One Project grew out of principles set forth by the Financial Services for the Poor team at the Bill & Melinda Gates Foundation to extend digital financial services to the world's two billion unbanked people. The code won’t address the gap in digital financial services on its own, but we believe it is a strong foundation for opening the market and accelerating progress.  

With support and funding from the Bill & Melinda Gates Foundation, Level One Project was designed by a team of leading tech and fintech companies: [Ripple](https://github.com/ripple), [Dwolla](https://github.com/dwolla), [ModusBox](http://www.modusbox.com/), [Software Group](http://www.softwaregroup-bg.com/) and [Crosslake Technologies](http://www.crosslaketech.com/). It is available now as an open-source project—free to be used and adapted by anyone under the [insert name of new license and link to file here]. For more information on Level One Project, visit [LevelOneProject.org](leveloneproject.org).

## Why should I contribute to Level One Project?
Level One Project makes it easier for financial providers and entrepreneurs to go to market with products and services, especially in developing markets where demand is high and supply is low.  

A nationwide interoperable digital payments platform requires really good code. Your contributions will help ensure that Level One Project covers all the bases, translates well to real-world scenarios, and meets the many and diverse needs of financial providers and customers.  

## Getting Started
The project is in GitHub and is organized on the basis of component microservices.  As such, there are over twenty different repositories in GitHub that align to the different services.  The _Docs_ repository documents the overall architecture, component design, message flow, and an overview of the Level One software. Individual repositories in the [Level One GitHub organization](https://github.com/LevelOneProject/) each describe component-specific details including source and APIs.

New developers, see the [contributors guide](./contribute.md) for onboarding materials.  For additional infromation please review the [frequently asked questions](/FAQ.md).

## Level One Services
The following architecture diagram shows the Level One services:

![Level One Services](https://github.com/LevelOneProject/Docs/blob/master/Wiki/Basic%20Overview.png)

See the [physical machines](https://github.com/LevelOneProject/Docs/blob/master/AWS/Infrastructure/machines.md) for information about the test and demonstration implementations in Amazon Web Services (AWS).

The basic idea behind the Level One Project is that we need to connect multiple Digital Financial Services Providers (DFSPs) together into a competitive and interoperable network in order to maximize opportunities for poor people to get access to financial services with low or no fees. We don't want a single monopoly power in control of all payments in a country, or a system that shuts out new players. It also doesn't help if there are too many isolated subnetworks. Our model addresses these issues in several key ways:

- A set of central services provides a hub through which money can flow from one DFSP to each other. This is similar to how money moves through a central bank or clearing house in developed countries. Besides a central ledger, central services can provide identity lookup, fraud management, and enforce scheme rules.
- A standard set of interfaces a DFSP can implement to connect to the system, and example code that shows how to use the system. A DFSP that wants to connect up can adapt our example code or implement the standard interfaces into their own software. The goal is for it to be as straightforward as possible for a DFSP to connect to the interoperable network.
- Complete working open-source implementations of both sides of the interfaces - an example DFSP that can send and receive payments and the client that an existing DFSP could host to connect to the network.


## Related Projects
The [Interledger Protocol Suite](https://interledger.org/) (ILP) is an open and secure standard that enables DFSPs to settle payments with minimal _counter-party risk_ (the risk you incur when someone else is holding your money). With ILP, you can transact across different systems with no chance that someone in the middle disappears with your money. The Level One Project uses the Interledger Protocol Suite for the clearing layer. For an overview of how it works, see the [Clearing Architecture Documentation](https://github.com/LevelOneProject/Docs/blob/master/ILP/README.md).
