# **Paymoja Design Decisions:**

## Bulk Payments
The user number will be used for identification purposes; 2nd verification form is required for confirmation.
Bulk payments will actually be handled the same way as we do individual payments; We will figure out a way to throttle/meter the payments (either via Mule or by the DFSP)  We will not use the ILP to do batching.
We will implement the simplest way possible and then identify where the loops are possible and the potential benefits of efficiency.

## Cash In / Cash Out
The Network times out after 75 seconds and users are dropped/ need to determine the use case.  We don’t want users to use other people's pins.  Fees are paid by DFSP not center and stored in a second account for transparency  (Shows the mini statement).

## Central Directory
Need to come up with some decorating scheme to define which you get to the generic thing to the user specific thing -- define a protocol. Takes multiple possible IDS - Returns dfsp server endpoints and standard UID
Come up with decorating schema to go from generic to specific.  The SPSP server asks the DFSP logic for the account, which may be returned as a hash/indirection 

## Error Cases
Need to look at Packet flow vs Inter-component flow errors differently.  Teams need to help specify these implementations and define the error messages (Ripple to lead).

## Fees
Sender: local fees handled by the DFSP
Fees will be aggregated and flow through the connectors
Realtime - show charges presented to the customer only show in flight charges (other aggregated charges will be displayed at another time.  Change the ILP protocol to send multiple changes and some will be used for fees (ledger is a generic tool - and needs to be flexible)  The team only needs to worry about fees that directly impact the customers (this does not go through the connector - but from the DFSP)
For phase one we care about the retail fees that the payee needs to pay (especially if this is not a closed loop system.

## Fraud Management
Paymoja has a shared fraud detection system and will document best practices for DFSPs.  

## Paymoja Decimal Type
When dealing with ISO20022 systems without rewriting amounts, we should limit the amount to a format that matches closely the XML Schema definition and doesn't allow for exponents at that can lead to potential loss of precision when talking to those external systems. For now for this project we should use the decimal type based on the XML Schema.

## Pending transaction workflow
Model the vouchers as a closed systems (up to the DFSP to settle).  Vouchers would flow through the fabric but the merchant's DFSP has to deal with the settlement.  NFC out of scope for 0.5.  Utilize ripple invoicing tech.

## Reliable Notifications
Use Web Sockets // If you want an additional notification mechanism - any reliable one can be implemented in addition to this.  Ledgers do not need to mess with notifications (they would do it on the backside so they can make their own decisions).

## Refunds
Refunds should be handled by the system and there should be meta-data to link to the original transaction.  Gates getting more business requirements for reversals.  

## Tier Limits
Customer that is paying the invoice needs to be informed with error messages.  Both limits need to be respected with scheme rules. Merchant and customer can both reject the invoice. No other special cases.  IST tier limits will focus on the tiers at the DFSP.

## No Reconciliation 
Because the Paymoja is designed to enable many very small transactions in a very reliable way at low cost, we don't build in manual reconciliation into the system as this would make the system more expensive. The system is specifically designed to minimize counterparty risk to prevent the need for reconciliation. It is possible to perform reconciliation though a business process that compares DFSP and the Central ledger, but that is out of scope.

# **Paymoja Process Decisions**

## GitHub
Create one story every time there is integration work. Create bugs for any issues.  Ensure all stories are tracked throughout the pipeline to ensure reliable metrics.

## Code Reviews
Code Reviews are not required outside the team unless there is integration work
All APIs should be documented, using the standard documentation and if changes occur all teams need to be notified

## Versioning 
Versioning of the API vs. versioning of a retrieved article - POR is staying with version string

## URLs
URLs can not be stored in a DB

## RAML vs. Swagger
Allow teams to use Swagger v2.0 so they can test, document, and share their work without the RAML tools. ModusBox will use RAML and convert Swagger programmatically to RAML v0.8 for production.  Public facing documentation in Swagger - (latest one is open api).  All components will be accessible over public internet by default.  Use Open API for public facing APIs.  See [Tools Decisions](Tools,-technology,-and-process-choices)

## RDS and Postgres use
Because our customers can't depend on AWS, we can't take a dependency on AWS for services, likewise RDS costs go up with usage unlike hosted services, so we are are not using RDS.

We'll be using Postgres as our backend DB, but should minimized dependencies on Postgres to be as generic to SQL as possible. There can be multiple schemas in the server, but not across domains. There can be a single Postgres server in each domain (each DFSP and the Central domain have one). 

The Postgres server should NOT be in a Docker container as it doesn't scale or update properly. We'll needs scripts to backup and restore the DB and to reset the test accounts. Changes to the current configuration will occur over the next several sprints as lower priority backlog items.

