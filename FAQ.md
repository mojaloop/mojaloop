# Frequently Asked Questions

_What is Mojaloop?_
Mojaloop is open-source software for building interoperable digital payments platforms on a national scale. It makes it easy for different kinds of providers to link up their services and deploy low-cost financial services in new markets.  

_How does it work?_
Most digital financial providers run on their own networks, which prevents customers who use different services from transacting with each other. Mojaloop functions like a universal switchboard, routing payments securely between all customers, regardless of which network they're on. It consists of three primary layers, each with a specific function: an interoperability layer, which connects bank accounts, mobile money wallets, and merchants in an open loop; a directory service layer, which navigates the different methods that providers use to identify accounts on each side of a transaction; a transactions settlement layer, which makes payments instant and irrevocable; and components which protect against fraud.  

_Who is it for?_
There are many components to the code, and everyone either directly or indirectly working with digital financial transactions-fintech developers, bankers, entrepreneurs, startups-is invited to explore and use whatever parts are useful or appealing. The software as a whole is meant to be implemented on a national scale, and so it will be most applicable to mobile money providers, payments associations, central banks, and country regulators.  

Developers at fintech and financial services companies can use the code in three ways: adapt the code to the financial services standards for a country, use the code to update their own products and services or create new ones, and improve the code by proposing updates and new versions of it for other users.  

For example: 
* A central bank may commission the use of the software by their commercial partners to speed up the deployment of a national payment gateway.
* A major payment processor can use the software to modernize their current offering, to achieve lower transaction costs without major R&D investments.
* A fintech startup can use the code to understand practically how to comply with interoperable payment APIs.
* A bank can use the code to modify their internal systems so that they easily interoperate with other payment providers.

_Why does it exist?_
Providers trying to reach developing markets with innovative, low-cost digital financial services have to build everything on their own. This raises costs and segregates services from each other. Mojaloop can be used as a foundation to help build interoperable platforms, lowering costs for providers and allowing them to integrate their services with others in the market.

_Who's behind it?_
Mojaloop was built in collaboration with a group of leading tech and fintech companies: [Ripple](https://github.com/ripple), [Dwolla](https://github.com/dwolla), [Software Group](http://www.softwaregroup-bg.com/), [ModusBox](http://www.modusbox.com/) and [Crosslake Technologies](http://www.crosslaketech.com/). Mojaloop was created by the Gates Foundation's Mojaloop, which is aimed at leveling the economic playing field by crowding in expertise and resources to build inclusive payment models to benefit the world's poor. It is free to the public as open-source software under the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0).

_What platforms does Mojaloop run on?_
The Mojaloop platform was developed for modern cloud-computing environments. Open-source methods and widely used platforms, like Node.js, serve as the foundation layer for Mojaloop. The microservices are packaged in Docker and can be deployed to local hardware or to cloud computing environments like Amazon Web Services or Azure.

_Is it really open-source?_
Yes. All core modules, documentation and white papers are available under the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0). Mojaloop relies on commonly used open-source software, including Node.js, MuleCE, Java and PostgreSQL. Mojaloop also uses the [Interledger Protocol](https://github.com/interledger) to choreograph secure money transfers. The licenses for all of these platforms and their imported dependencies allow for many viable uses of the software.

_How can I contribute to Mojaloop?_
You can contribute by helping us create new functionality on our roadmap or by helping us improve the platform. For our roadmap, go to the [Roadmap.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Roadmap.md). We recommend starting with the onboarding guide and sample problem. This has been designed by the team to introduce the core ideas of the platform and software, the build methods, and our process for check-ins.
