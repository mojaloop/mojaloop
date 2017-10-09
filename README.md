# The Level One Project Overview
The Level One Project advocates and promotes financial inclusion for everyone. Today more than 2 billion adults do not have a bank account or access to a formal financial institution.  The Level One Project is aimed at changing this denominator by making banking accessible by everyone via a standard flip phone.  Our project is aimed at building a national digital financial solution that is open to everyone.  Specifically, any person in any location with a phone can open a back account, send money, receive money or get paid for services.  This open system will help the poorest people in the most remote locations to ensure a safe and reliable solution.  

The Level One Project is a sofware implementation of the Level One Project. For more information on the Level One Project, see the https://LevelOneProject.org

Overview documentation is in the [Docs repository](https://github.com/LevelOneProject/Docs/README.md).

## Why should I contribute?
The Level One Project is an initiative started by the Bill and Melinda Gates Foundation to make it easier for developing countries to provide useful digital financial services to the people who live there. To participate in the formal, global economy, everyone needs access to digital financial services so they can transact quickly and safely, across distances long and short.  

This project started with a model and prototype for a financial system that could be implemented in any country.  In addition, this code takes that a step further by implementing a strong reliable messaging using the [Interledger](http://interledger.org) protocol as well as a functioning central hub that financial providers can connect to facilitate common settlement and regulatory compliance.

> In order to expand financial inclusion and ensure a level playing field for everyone, we need your help to enhance this project and help to realize the vision of having a digital financial system in every country around the world.

## Getting Started
The project is in GitHub and is organized on the basis of component microservices.  As such, there are over twenty different repositories in GitHub that align to the different services.  The _Docs_ repository documents the overall architecture, component design, message flow, and an overview of the Level One software. Individual repositories in the [Level One GitHub organization](https://github.com/LevelOneProject/) each describe component-specific details including source and APIs.

New developers, see the [contributors guide](./contribute.md) for onboarding materials.

## Level One Services
The following architecture diagram shows the Level One services:

![Level One Services](https://github.com/LevelOneProject/Docs/blob/master/Wiki/Basic%20Overview.png)

See the [physical machines](https://github.com/LevelOneProject/Docs/blob/master/AWS/Infrastructure/machines.md) for information about the test and demonstration implementations in Amazon Web Services (AWS).

The basic idea behind the Level One Project is that we need to connect multiple Digital Financial Services Providers (DFSPs) together into a competitive and interoperable network in order to maximize opportunities for poor people to get access to financial services with low or no fees. We don't want a single monopoly power in control of all payments in a country, or a system that shuts out new players. It also doesn't help if there are too many isolated subnetworks. Our model addresses these issues in several key ways:

- A set of central services provides a hub through which money can flow from one DFSP to each other. This is similar to how money moves through a central bank or clearing house in developed countries. Besides a central ledger, central services can provide identity lookup, fraud management, and enforce scheme rules.
- A standard set of interfaces a DFSP can implement to connect to the system, and example code that shows how to use the system. A DFSP that wants to connect up can adapt our example code or implement the standard interfaces into their own software. The goal is for it to be as straightforward as possible for a DFSP to connect to the interoperable network.
- Complete working open-source implementations of both sides of the interfaces - an example DFSP that can send and receive payments and the client that an existing DFSP could host to connect to the network.


## Related Projects
The [Interledger Protocol Suite](https://interledger.org/) (ILP) is an open and secure standard that enables DFSPs to settle payments with minimal _counter-party risk_ (the risk you incur when someone else is holding your money). With ILP, you can transact across different systems with no chance that someone in the middle disappears with your money. The Level One Project uses the Interledger Protocol Suite for the clearing layer. For an overview of how it works, see the [Clearing Architecture Documentation](https://github.com/LevelOneProject/Docs/blob/master/ILP).
