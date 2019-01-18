# Mojaloop Core Related Components
## Document Virtual Catalog

#### What is this document about.
This document is intended to provide the reader with an insight into the core related component repositories and the documentation currently available for Mojaloop. Navigation within the document and the respective repositories are possible by following the hyper-link. This document serves to consolidate all documentation under one "virtual map" of the entire Mojaloop related document suite.

#### Assumptions and related matters.
All references point to the master branch of each repository. The project development team is in the process to ensure all documentation is current and up to date as per the latest project release. Please note that we have not marked outdated documents as such and there are still many stale references.

##### The following Mojaloop core related components repository are part of this document:

- [Docs](#docs)
  - [CentralDirectory](#centraldirectory)
  - [CentralLedger](#centralledger)
  - [CentralRules](#centralrules)
  - [CentralServices](#centralservices)
    - [Designs](#designs)
    - [Mojaloop-architecture-static-demo](#mojaloop-architecture-static-demo)
    - [Mojaloop-deployment](#mojaloop-deployment)
  - [Diagrams](#diagrams)
    - [ArchitecturalDiagrams](#architecturaldiagrams)
    - [DataDiagrams](#datadiagrams)
    - [SequenceDiagrams](#sequencediagrams)
  - [DFSP](#dfsp)
    - [BulkPayment](#bulkpayment)
    - [E2E integration tests proposal](#e2e-integration-tests-proposal)
    - [GSMA MM & L1P DFSP API](#gsma-mm--l1p-dfsp-api)
    - [Invoice API](#invoice-api)
    - [ManageAcccoutHolders](#manageaccountholders)
    - [Pending Transactions Api](#pending-transactions-api)
    - [PendingTransactions](#pendingtransactions)
    - [USSD](#ussd)
  - [DevOps](#devops)
  - [ELK](#elk)
  - [ExportDocs](#exportdocs)
  - [ILP](#ilp)
  - [Interop Services and Mule](#inter-services-and-mule)
  - [Interop](#interop)
  - [Standards](#standards)
  - [Wiki](#wiki)
  - [WorkShops/Presentations](#workshopspresentations)
  - [Metrics-images](#metrics-images)
  - [Test](#test)
    - [End-to-end](#end-to-end)
    - [Ilp-integration](#ilp-integration)
    - [Performance](#performance)
- [Helm](#helm)
- [Interop-common](#interop-common)
- [Interop-devops](#interop-devops)
- [Interop-domain](#interop-domain)
- [Interop-parent](#interop-parent)
- [Mojaloop](#mojaloop)
  - [Contribute](#contribute)
- [Mojaloop.github.io](#mojaloopgithubio)
- [Mojaloop-specifications](#mojaloop-specifications)
- [Postman](#postman)
- [Project](#project)
- [Test-scripts](#test-scripts)


## Repository

### Docs
 Click on [docs](https://github.com/mojaloop/docs) to navigate to the _docs_ repository.
 ##### Cross-repo documentation, end to end scenarios, and architecture.
  
  #### CentralDirectory
  Click on [CentralDirectory](https://github.com/mojaloop/docs/tree/master/CentralDirectory) to navigate to _CentralDirectory_ directory within the _docs_ repository.
  ###### Contains the public documents and high block diagrams for the Central Directory.
  |Artefact|Artefact Description|
  |---|---|
  |[README.md](https://github.com/mojaloop/docs/blob/master/CentralDirectory/README.md)|Provides an overview by covering the following:<ul><li>Component Architecture</li><li>End User Lookup</li><li>Directory Endpoints</li><li>Endpoints</li><li>Data Structures</li><li>Error information</li></ul>|
  |[central_directory_endpoints.md](https://github.com/mojaloop/docs/blob/master/CentralDirectory/central_directory_endpoints.md)|Provides an overview of the Central Ledger API by covering the following:<ul><li>Data Structures</li><li>Endpoints</li><li>Error Information</li></ul>|

  #### CentralLedger
  Click on [CentralLedger](https://github.com/mojaloop/docs/tree/master/CentralLedger) to navigate to _CentralLedger_ directory within the _docs_ repository.
  ###### Contains the public documents and high block diagrams for the Central Ledger.
  |Artefact|Artefact Description|
  |---|---|   
  |[README.md](https://github.com/mojaloop/docs/blob/master/CentralLedger/README.md)|Provides an overview of Central Ledger by covering the following:<ul><li>Component Architecture</li><li>Transfer/Fulfillment Flow</li><li>Settlement Flow</li><li>Endpoints</li></ul>|
  |[central_ledger_endpoints.md](https://github.com/mojaloop/docs/blob/master/CentralLedger/central_ledger_endpoints.md)|Provides an overview of the Central Ledger API by covering the following:<ul><li>[Data Structures](https://github.com/mojaloop/docs/blob/master/CentralLedger/central_ledger_endpoints.md#data_structures)</li><li>[Endpoints](https://github.com/mojaloop/docs/blob/master/CentralLedger/central_ledger_endpoints.md#endpoints)</li><ul><li>[Transfer Endpoints](https://github.com/mojaloop/docs/blob/master/CentralLedger/central_ledger_endpoints.md#transfer_endpoints)</li><li>[Account Endpoints](https://github.com/mojaloop/docs/blob/master/CentralLedger/central_ledger_endpoints.md#transfer_endpoints)</ul></li><li>[Other Endpoints](https://github.com/mojaloop/docs/blob/master/CentralLedger/central_ledger_endpoints.md#account_endpoints)</li><li>[Error Information](https://github.com/mojaloop/docs/blob/master/CentralLedger/central_ledger_endpoints.md#error_information)</ul></li>|

  #### CentralRules 
  Click on [CentralRules](https://github.com/mojaloop/docs/tree/master/CentralRules) to navigate to _CentralRules_ directory within the _docs_ repository.
  ###### Contains the public documents and high block diagrams for the Central Rules.
  |Artefact|Artefact Description|
  |---|---|   
  |[LICENSE](https://github.com/mojaloop/docs/blob/master/CentralRules/LICENSE)|Project Licensing information.
  |[README.md](https://github.com/mojaloop/docs/blob/master/CentralRules/README.md)|Provides an overview by covering the following:<ul><li>Component Architecture</li><li>Check Transfer Eligibility Flow</li><li>Endpoints</li></ul>|
  |[central_rules_endpoints.md](https://github.com/mojaloop/docs/blob/master/CentralRules/central_rules_endpoints.md)|The Central Rules API determines whether a transfer to an End User is permitted.|

  #### CentralServices
  Click on [CentralServices](https://github.com/mojaloop/docs/tree/master/CentralServices) to navigate to _CentralServices_ directory within the _docs_ repository.
  ###### Contains the public documents and high block diagrams for the Central Services.

   ##### Designs
   Click on [Designs](https://github.com/mojaloop/docs/tree/master/CentralServices/Designs) to navigate to _Designs_ sub directory in the _CentralServices_ directory within the docs repository.
   ###### Contains design documentation for Mojaloop.
   |Artefact|Artefact Description|
   |---|---|   
   |[des-timeout-1.0.md](https://github.com/mojaloop/docs/blob/master/CentralServices/Designs/des-timeout-1.0.md)|The Document explains the Design Timeout DAO Layer.|

   ##### Mojaloop-architecture-static-demo
   Click on [mojaloop-architecture-static-demo](https://github.com/mojaloop/docs/tree/master/CentralServices/mojaloop-architecture-static-demo) to navigate to _mojaloop-architecture-static_demo_ sub directory in the _CentralServices_ directory within the _docs_ repository.
   ###### Contains the architecture static demonstration documentation for Mojaloop.

   ##### Mojaloop-deployment
   Click on [mojaloop-deployment](https://github.com/mojaloop/docs/tree/master/CentralServices/mojaloop-deployment) to navigate to _mojaloop-deployment_ sub directory in the _CentralServices_ directory within the _docs_ repository.
   ###### The current Mojaloop deployment and setup.
   |Artefact|Artefact Description|
   |---|---|
   |[Mojaloop_Phase2_Wrap-up_Deployment-Day3_V2.0-published.pdf](https://github.com/mojaloop/docs/blob/master/CentralServices/mojaloop-deployment/Mojaloop_Phase2_Wrap-up_Deployment-Day3_V2.0-published.pdf)|Step by step guide showing the deployment process as used during the Phase2 Mojaloop demonstrated.|

  #### Diagrams 
  Click on [Diagrams](https://github.com/mojaloop/docs/tree/master/Diagrams) to navigate to _Diagrams_ directory within the _docs_ repository.
  ###### Contains the design diagrams for Mojaloop.

   ##### ArchitecturalDiagrams
   Click on [ArchitecturalDiagrams](https://github.com/mojaloop/docs/tree/master/Diagrams/ArchitecturalDiagrams) to navigate _ArchitecturalDiagrams_ sub directory in the _Diagrams_ directory within the _docs_ repository.
   ###### Contains the architectural diagrams for Mojaloop.
   |Artefact|Artefact Description|
   |---|---|
   |[20180830-Mojaloop-End_to_End-PI3.pdf](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/20180830-Mojaloop-End_to_End-PI3.pdf)|Mojaloop End-To-End architectural diagram end of PI3.|
   |[20180830-Mojaloop-PI3_Arch.pdf](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/20180830-Mojaloop-PI3_Arch.pdf)|Component Architectural diagram.|
   |[Arch-Flows-End-to-End-mini.png](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/Arch-Flows-End-to-End-mini.png)|Compact Architectural flow sequence diagram.|
   |[Arch-Flows-End-to-End.png](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/Arch-Flows-End-to-End.png)|Architectural flow sequence diagram.|
   |[Arch-Flows-End_to_End-Overview-Draft.png](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/Arch-Flows-End_to_End-Overview-Draft.png)|Architectural Flows End-to-End Overview (draft).|
   |[Arch-Flows-End_to_End-Overview-Two-APIs.png](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/Arch-Flows-End_to_End-Overview-Two-APIs.png)|Architectural Flows End-To-End Overview Two APIs.|
   |[Arch-Flows-Transfers-Complete.png](https://github.com/mojaloop/docs/blob/develop/Diagrams/ArchitecturalDiagrams/Arch-Flows-Transfers-Complete.png)|Architectural Flows Transfers Complete.|
   |[Arch-Flows-Transfers-golden-path.png](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/Arch-Flows-Transfers-golden-path.png)|Architectural Flows Transfers golden path.|
   |[Arch-Flows.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/Arch-Flows.svg)|Architectural Flows.|
   |[Arch_Flows.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/Arch_Flows.svg)|Compact Architectural Flows.|
   |[Central-services.png](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/central-services.png)|Central Services diagram.|
   |[end-to-end-flow.png](https://github.com/mojaloop/docs/blob/master/Diagrams/ArchitecturalDiagrams/end-to-end-flow.png)|End to end flow diagram.|

   ##### DataDiagrams
   Click on [DataDiagrams](https://github.com/mojaloop/docs/tree/master/Diagrams/DataDiagrams) to navigate _DataDiagrams_ sub directory in the _Diagrams_ directory within the _docs_ repository.
   ###### Contains the database data definition language (ddl) and schema for Mojaloop.
   |Artefact|Artefact Description|
   |---|---|
   |[central-ledger-schema.png](https://github.com/mojaloop/docs/blob/master/Diagrams/DataDiagrams/central-ledger-schema.png)|Central Ledger database schema diagram.|

   ##### SequenceDiagrams
   Click on [SequenceDiagrams](https://github.com/mojaloop/docs/tree/master/Diagrams/SequenceDiagrams) to navigate _SequenceDiagrams_ sub directory in the _Diagrams_ directory within the _docs_ repository.
   ###### Contains the sequence diagrams for the Mojaloop processes.
   ###### _Events:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-event-9.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-event-9.1.0.svg)</li></ul>|<ul>9.1.0. Event Handler Placeholder</ul>|
   ###### _Fulfil:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-fulfil-2.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-fulfil-2.1.0.svg)</li><li>[seq-fulfil-2.1.1.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-fulfil-2.1.1.svg)</li><li>[seq-reject-2.2.1.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-reject-2.2.1.svg)</li><li>[seq-reject-2.2.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-reject-2.2.0.svg)</ul></li>|<ul><li>2.1.0. DFSP2 sends a Fulfil Success Transfer request</li><li>2.1.1. Fulfil Handler Consume (Success)</li><li>2.1.1. Fulfil Handler Consume (Success)</li><li>2.2.0. DFSP2 sends a Fulfil Reject Transfer request</ul></li>|
   ###### _Notification:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-prepare-1.1.4.a.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.4.a.svg)</li><li>[seq-prepare-1.1.4.b.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.4.b.svg)</li><li>[seq-notification-reject-5.1.1.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-notification-reject-5.1.1.svg)</ul></li>|<ul><li>1.1.4.a. Send notification to Participant (Payer/Payee) (single message)</li><li>1.1.4.b. Send notification to Participant (Payer/Payee) (batch messages)</li><li>5.1.1. Notification Handler for Rejections</ul></li>|
   ###### _Participant:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-get-participant-limit-1.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-get-participant-limit-1.1.0.svg)</li><li>[seq-manage-participant-limit-1.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-manage-participant-limit-1.1.0.svg)</li><li>[seq-callback-add-3.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-callback-add-3.1.0.svg)</li><li>[seq-callback-3.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-callback-3.1.0.svg)</li><li>[seq-participants-positions-query-4.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-participants-positions-query-4.1.0.svg)</ul></li>|<ul><li>1.0.0 Get Participant Limit Details</li><li>2.06 Design an API to manage NET DEBIT CAP #330</li><li>3.1.0 Add Participant Callback Details</li><li>3.1.0 Get Participant Callback Details</li><li>4.1.0 Get Participant Position Details</li></ul>|
   ###### _Position:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-participant-limits-1.0.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-participant-limits-1.0.0.svg)</li><li>[seq-prepare-1.1.2.a.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.2.a.svg)</li><li>[seq-prepare-1.1.2.b.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.2.b.svg)</li><li>[seq-position-1.3.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-position-1.3.0.svg)</li><li>[seq-position-1.3.1-prepare.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-position-1.3.1-prepare.svg)</li><li>[seq-position-1.3.2-fulfil.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-position-1.3.2-fulfil.svg)</li><li>[seq-position-1.3.3-abort.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-position-1.3.3-abort.svg)</li><li>[seq-reject-2.2.2.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-reject-2.2.2.svg)</li><li>[seq-participants-positions-query-all-4.2.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-participants-positions-query-all-4.2.0.svg)</li><li>[use-case-position-handler.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/use-case-position-handler.svg)</li></ul>|<ul><li>1.0.0 Create initial position and limits for participant</li><li>1.1.2.a. Position Handler Consume (single message)</li><li>1.1.2.b. Position Handler Consume (batch messages)</li><li>1.3.0 Position Handler Consume (single message)</li><li>1.3.1 Prepare Position Handler Consume</li><li>1.3.2 Fulfil Position Handler Consume</li><li>1.3.3 Abort Position Handler Consume</li><li>2.2.2. Position Handler Consume (Reject)</li><li>4.2.0 Get Positions of all Participants</li><li>uc Position Handler</li></ul>|
   ###### _Prepare:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-prepare-1.1.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.0.svg)</li><li>[seq-prepare-1.1.1.a.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.1.a.svg)</li><li>[seq-prepare-1.1.1.b.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.1.b.svg)</li></ul>|<ul><li>1.1.0. DFSP1 sends a Prepare Transfer request to DFSP2</li><li>1.1.1.a. Prepare Handler Consume (single message)</li><li>1.1.1.b. Prepare Handler Consume (batch messages)</li></ul>|
   ###### _Transfer:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-prepare-1.1.3.a.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.3.a.svg)</li><li>[seq-prepare-1.1.3.b.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-prepare-1.1.3.b.svg)</li><li>[seq-fulfil-2.1.3.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-fulfil-2.1.3.svg)</li><li>[seq-reject-2.2.3.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-reject-2.2.3.svg)</li><li>[seq-timeout-2.3.0.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-timeout-2.3.0.svg)</li><li>[seq-timeout-2.3.1.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-timeout-2.3.1.svg)</li><li>[seq-timeout-2.3.3.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-timeout-2.3.3.svg)</li></ul>|<ul><li>1.1.3.a. Transfer Handler Consume (single message)</li><li>1.1.3.b. Transfer Handler Consume (batch messages)</li><li>2.1.3. Transfer Handler Consume (Success)</li><li>2.2.3. Transfer Handler Consume (Reject)</li><li>2.3.0. Transfer Timeout</li><li>2.3.1. Timeout Handler Consume</li><li>2.3.3. Transfer Handler Consume (Timeout)</li></ul>|
   ###### _Security:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-signature-validation.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-signature-validation.svg)</li></ul>|<ul><li>To be allocated when bug #70 is completed</li></ul>|
   ###### _Settlement:_
   |Artefact|Artefact Description|
   |---|---|
   |<ul><li>[seq-setwindow-6.1.1.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-setwindow-6.1.1.svg)</li><li>[seq-setwindow-6.1.2.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-setwindow-6.1.2.svg)</li><li>[seq-setwindow-6.1.3.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-setwindow-6.1.3.svg)</li><li>[seq-settlement-6.2.1.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-settlement-6.2.1.svg)</li><li>[seq-settlement-6.2.2.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-settlement-6.2.2.svg)</li><li>[seq-settlement-6.2.3.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-settlement-6.2.3.svg)</li><li>[seq-settlement-6.2.4.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-settlement-6.2.4.svg)</li><li>[seq-settlement-6.2.5.svg](https://github.com/mojaloop/docs/blob/master/Diagrams/SequenceDiagrams/seq-settlement-6.2.5.svg)</li></ul>|<ul><li>6.1.1. Request Settlement Window By Id (getSettlementWindowById)</li><li>6.1.2. Close Settlement Window (closeSettlementWindow)</li><li>6.1.3. Get Settlement Windows By Parameters (getSettlementWindowsByParams)</li><li>6.2.1. Trigger Settlement Event (createSettlement)</li><li>6.2.2. Query Settlements by Parameters</li><li>6.2.3. Get Settlement By Settlement, Participant and Account (getSettlementBySettlementParticipantAccount)</li><li>6.2.4. Get Settlement By Id (getSettlementById)</li><li>6.2.5. Acknowledgement of Settlement Transfer (updateSettlementById)</li></ul>|

  #### DFSP
  Click on [DFSP](https://github.com/mojaloop/docs/tree/master/DFSP) to navigate to _DFSP_ directory within the _docs_ repository.
  ###### Explains the DFSP Microservices, Component Diagram, Flow Diagram, Default Ports and Development Environment Setup.
  |Artefact|Artefact Description|
  |---|---|
  |[README.md](https://github.com/mojaloop/docs/blob/master/DFSP/README.md)|Overview of the DFSP Microservices and DFSP functionality:<ul><li>[Component Diagram](https://github.com/mojaloop/docs/tree/master/DFSP#component-diagram)</li><li>[Flow Diagrams](https://github.com/mojaloop/docs/tree/master/DFSP#flow-diagrams)</li><li>[Default Ports](https://github.com/mojaloop/docs/tree/master/DFSP#default-ports)</li><li>[Development Environment Setup](https://github.com/mojaloop/docs/tree/master/DFSP#development-environment-setup)</li>|
  |[account.md](https://github.com/mojaloop/docs/blob/master/DFSP/account.md)|Describes the account service API and information about relations between users and their accounts.|
  |[development.md](https://github.com/mojaloop/docs/blob/master/DFSP/development.md)|Defines the various steps in setting up the development environment.|
  |[directory.md](https://github.com/mojaloop/docs/blob/master/DFSP/directory.md)|Explains the use of the directory API service.|
  |[identity.md](https://github.com/mojaloop/docs/blob/master/DFSP/identity.md)|Explains the Identity Service API as used for managing identity related data, such as sessions, images, PINs, and so on. This service contains information about all the available actions and the roles that can perform them.|
  |[notification.md](https://github.com/mojaloop/docs/blob/master/DFSP/notification.md)|Provides an overview of the Notification service API. The service chooses the appropriate channels and devices for the notification.|
  |[rule.md](https://github.com/mojaloop/docs/blob/master/DFSP/rule.md)|Provides an overview of Rule service API. It contains methods related to fees, limits and other rules.|
  |[subscription.md](https://github.com/mojaloop/docs/blob/master/DFSP/subscription.md)|Provides an overview of the Subscription service API and it's used for mapping between users and phone numbers.|
  |[transfer.md](https://github.com/mojaloop/docs/blob/master/DFSP/transfer.md)|Provides an overview of the Transfer services API, invoices and invoice notifications.|

   ##### BulkPayment
   Click on [BulkPayment](https://github.com/mojaloop/docs/tree/master/DFSP/BulkPayment) to navigate to the _BulkPayment_ sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/DFSP/BulkPayment/README.md)|Provides an overview of the bulk payment process.|

   ##### E2E integration tests proposal
   Click on [E2E integration tests proposal](https://github.com/mojaloop/docs/tree/master/DFSP/E2E%20integration%20tests%20proposal) to navigate to _E2E integration tests proposal_ sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/DFSP/E2E%20integration%20tests%20proposal/README.md)|Demonstrates an E2E integration testing proposal.|

   ##### GSMA MM & L1P DFSP API
   Click on [GSMA MM & L1P DFSP API](https://github.com/mojaloop/docs/tree/master/DFSP/GSMA%20MM%20%26%20L1P%20DFSP%20API) to navigate to _GSMA MM & L1P DFSP API_ tests proposal sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[ReadMe.md](https://github.com/mojaloop/docs/blob/master/DFSP/GSMA%20MM%20%26%20L1P%20DFSP%20API/ReadMe.md)|The document offers a technical comparison between the Mobile Money API defined by GSMA and DFSP Over the Top API.|

   ##### Invoice API
   Click on [Invoice API](https://github.com/mojaloop/docs/tree/master/DFSP/Invoice%20API) to navigate to _Invoice API_ sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/DFSP/Invoice%20API/README.md)|The document covers the flow of the following use cases:<ul><li>Creation and payment of a pending invoice associated with a payer,</li><li>Creation and payment of a pending invoice, not associated with a payer,</li><li>Support for merchant push payment initiated by the customer.</li></ul>Invoice API Principles:<ul><li>Restful approach to API design,<li>Based on JSON, no other content types are supported.</li></ul>|

   ##### ManageAccountHolders
   Click on [ManageAcccoutHolders](https://github.com/mojaloop/docs/tree/master/DFSP/ManageAcccoutHolders) to navigate to _ManageAccountHolders_ sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[ReadMe.md](https://github.com/mojaloop/docs/blob/master/DFSP/ManageAcccoutHolders/ReadMe.md)|The document describes the different options of managing multiple account holders within a DFSP system.

   ##### Pending Transactions API
   Click on [Pending Transactions Api](https://github.com/mojaloop/docs/tree/master/DFSP/Pending%20Transactions%20Api) to navigate to _Pending Transactions API_ sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/DFSP/Pending%20Transactions%20Api/README.md)|Provides insight into the Pending Transfer API that exposes the DFSP functionalities for transfers processing, customer and account management.

   ##### PendingTransactions
   Click on [PendingTransactions](https://github.com/mojaloop/docs/tree/master/DFSP/PendingTransactions) to navigate to _PendingTransactions_ sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/develop/DFSP/PendingTransactions/README.md)|This document covers the following processes within the Pending Transaction process within the L1P service;<ul><li>Get sender details</li><li>Quote source/destination</li><li>Invoice Creation</li><li>Get invoice details</li><li>Invoice payments.</ul></li>|

   ##### USSD
   Click on |[USSD](https://github.com/mojaloop/docs/tree/master/DFSP/USSD) to navigate to _USSD_ sub directory in the _DFSP_ directory within the _docs_ repository.

   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/DFSP/PendingTransactions/README.md)|This document explains purpose of USSD simulator and how to simulate a real USSD interface over HTTP.|

  #### DevOps
  Click on [DevOps](https://github.com/mojaloop/docs/tree/master/DevOps) to navigate to _DevOps_ directory within the _docs_ repository.
  ###### Describes the current setup and use of CI (Continuous Integration) & CD (Continuous Deployment) within Mojaloop.
   |Artefact|Artefact Description|
   |---|---|
   |[CI_and_CD_requirements.md](https://github.com/mojaloop/docs/blob/master/DevOps/CI_and_CD_requirements.md)|Describes the current CI (Continuous Integration) & CD (Continuous Deployment) Requirements and workflow:<ul><li>Continuous Integration Pipeline,</li><li>Continuous Deployment Pipeline.</li></ul>|
   |[CircleCi.md](https://github.com/mojaloop/docs/blob/master/DevOps/CircleCi.md)|Descripts CircleCI Mojaloop Configuration setup and build the project.|

  #### ELK
  Click on [ELK](https://github.com/mojaloop/docs/tree/master/ELK) to navigate to _ELK_ directory within the _docs_ repository.
  ###### "ELK" is the acronym for three open source projects: Elasticsearch and Kibana are currently used by Mojaloop.
   |Artefact|Artefact Description|
   |---|---|
   |[ELKSetup.md](https://github.com/mojaloop/docs/blob/master/ELK/ELKSetup.md)|Guide the reader through the steps to perform ELK 5.X Stack Installation in AWS EC2 Instance RHEL.|
   |[kibana-user-guide.md](https://github.com/mojaloop/docs/blob/master/ELK/kibana-user-guide.md)|Describes how to use Kibana, its dashboards and query language for L1P tracing and debugging purposes.|

  #### ExportDocs
  Click on [ExportDocs](https://github.com/mojaloop/docs/tree/master/ExportDocs) to navigate to _ExportDocs_ directory within the _docs_ repository.
  ###### Contains guidelines to convert documents into PDF format for offline sharing.
   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/ExportDocs/README.md)|Guide the reader to use a tool called [Dactyl](https://github.com/ripple/dactyl) to convert files to from markdown (md) format to PDF format. The PDF format is the exported format we use to share offline documentation.|

  #### ILP
  Click on [ILP](https://github.com/mojaloop/docs/tree/master/ILP) to navigate to _ILP_ directory within the _docs_ repository.
  ###### Contains content to describe the Interledger project and use within Mojaloop.
   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/ILP/README.md)|Defines the Interledger project and the suite of protocols used within Mojaloop. The following content are discussed:<ul><li>[Why Interledger](https://github.com/mojaloop/docs/tree/master/ILP#why-interledger)</li><li>[Core Concepts](https://github.com/mojaloop/docs/tree/master/ILP#core-concepts)</li><li>[Protocol Layers](https://github.com/mojaloop/docs/tree/master/ILP#protocol-layers)</li><li>[Addresses and Routing](https://github.com/mojaloop/docs/tree/master/ILP#addresses-and-routing)</li><li>[Data Formats](https://github.com/mojaloop/docs/tree/master/ILP#data-formats)</li><li>[Software Components](https://github.com/mojaloop/docs/tree/master/ILP#software-components)</li></ul>|

  #### Inter Services and Mule
  Click on [Interop Services and Mule](https://github.com/mojaloop/docs/tree/master/Interop%20Services%20and%20Mule) to navigate to _Interop Services and Mule_ directory within the _docs_ repository.
  ###### Content for Interop Services running on Mule service.
   |Artefact|Artefact Description|
   |---|---|
   |[Configuring HAProxy.md](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/Configuring%20HAProxy.md)|This Document explains about Installing and configuring HAProxy on AWS EC2 Instance.|
   |[README.md](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md)|Describes the various interop service APIs act as proxies and/or provide features such as validation, authentication and data transformation. The several repositories that support non-functional requirements such as Performance, Logging, Metrics and Deployment that are discussed below as well. Contents consist of:<ul><li>[Overview](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#overview)</li><li>[Architecture](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#architecture)</li><li>[Interfaces](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#interfaces)</li><li>[Testing](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#testing)</li><li>[Security](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#security)</li><li>[Resilience](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#resilience)</li><li>[Performance](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#performance)</li><li>[Logging](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#logging)</li><li>[Deployment](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/README.md#deployment)</li></ul>|
   |[docker.md](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/docker.md)|Steps through the process to build a Mule Docker image.|
   |[logging-guidelines.md](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/logging-guidelines.md)|This document provides Mojaloop services logging guidelines in order to provide end-end traceability of interactions, aid in troubleshooting and publish metrics to the backend.|
   |[studio-and-mule-runtime-setup.md](https://github.com/mojaloop/docs/blob/master/Interop%20Services%20and%20Mule/studio-and-mule-runtime-setup.md)|The installation and setup process as a Mule developer.|

  #### Interop
  Click on [Interop](https://github.com/mojaloop/docs/tree/master/Interop) to navigate to _Interop_ directory within the _docs_ repository.
  ###### Contains a document that describes an outline design to support transfers of funds between parties.
   |Artefact|Artefact Description|
   |---|---|
   |[transfers-between-mojaloop-implementations.md](https://github.com/mojaloop/docs/blob/master/Interop/transfers-between-mojaloop-implementations.md)|This document describes an outline design to support transfers of funds between parties who are customers of DFSPs which belong to different Mojaloop implementations.|

  #### Standards
  Click on [Standards](https://github.com/mojaloop/docs/tree/master/Standards) to navigate to the _Standards_ directory within the _docs_ repository.
  ###### Contains documentation that clarify a set of standards for Mojaloop.
   |Artefact|Artefact Description|
   |---|---|
   |[Creating_new_Features.md](https://github.com/mojaloop/docs/blob/master/Standards/Creating_new_Features.md)|Guidelines on creating a new feature within Mojaloop.|
   |[Standard_Headers.md](https://github.com/mojaloop/docs/blob/master/Standards/Standard_Headers.md)|Provides the standard header template to be used for Mojaloop.|
   |[Template_Bug.md](https://github.com/mojaloop/docs/blob/master/Standards/Template_Bug.md)|Template to be used when reporting bug.|
   |[Template_Story.md](https://github.com/mojaloop/docs/blob/master/Standards/Template_Story.md)|Template to be used when creating a story for Mojaloop.|

  #### Wiki
  Click on |[Wiki](https://github.com/mojaloop/docs/tree/master/Wiki) to navigate to the _Wiki_ directory within the _docs_ repository.
  ###### Supporting images to support this feature.

  #### Workshops/Presentations
  Click on [WorkShops/Presentations](https://github.com/mojaloop/docs/tree/master/WorkShops/Presentations) to navigate to the _Workshops/Presentations_ directory within the _docs_ repository.
  ###### Contains presentations from workshops for Mojaloop.

  #### Metrics-images
  Click on [metrics-images](https://github.com/mojaloop/docs/tree/master/metrics-images) to navigate to the _metrics-images_ directory within the _docs_ repository.
  ###### Contains performance metrics images for Mojaloop.

  #### Test
  Click on [Test](https://github.com/mojaloop/docs/tree/master/Test) to navigate to the _Test_ directory within the _docs_ repository.
  ###### Contains the tests describe that describe the expected behavior of the various services separate from the interfaces.|
   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/Test/README.md)|Short description of the repository content.|
   |[RMA.md](https://github.com/mojaloop/docs/blob/master/Test/RMA.md)|Overview of Resilience Modeling and Analysis.|
   |[account management tests.md](https://github.com/mojaloop/docs/blob/master/Test/account%20management%20tests.md)|Describes the account management tests as a internal to the DFSP service.|
   |[bulk payments.md](https://github.com/mojaloop/docs/blob/master/Test/bulk%20payments.md)|Overview of the bulk payment is made through the DFSP admin UI.|
    |[customer management tests.md](https://github.com/mojaloop/docs/blob/master/Test/customer%20management%20tests.md)|Overview of the customer management tests.|
   |[dfsp management tests.md](https://github.com/mojaloop/docs/blob/master/Test/dfsp%20management%20tests.md)|Overview of the done to manage a DFSP.|
   |[fees tests.md](https://github.com/mojaloop/docs/blob/master/Test/fees%20tests.md)|The test combinations in the test matrix to test fees.|
   |[forensic logging tests.md](https://github.com/mojaloop/docs/blob/master/Test/forensic%20logging%20tests.md)|Describes the requirements and how to test Forensic Logging.|
   |[pending transaction tests.md](https://github.com/mojaloop/docs/blob/master/Test/pending%20transaction%20tests.md)|Overview of the pending transaction test process.|
   |[send money tests.md](https://github.com/mojaloop/docs/blob/master/Test/send%20money%20tests.md)|Test processes related to sending money between destinations and customers.|

   ##### End-to-end
   Click on [end-to-end](https://github.com/mojaloop/docs/tree/master/Test/end-to-end) to navigate to the _end-to-end_ sub directory in the _Test_ directory within the _docs_ repository.
   ##### Functional end-to-end test.
   |Artefact|Artefact Description|
   |---|---|
   |[readme.md](https://github.com/mojaloop/docs/blob/master/Test/end-to-end/readme.md)|Describes the functional end-to-end test.|

   ##### Ilp-integration
   Click on [ilp-integration](https://github.com/mojaloop/docs/tree/master/Test/ilp-integration) to navigate to the _ilp-integration_ sub directory in the _Test_ directory within the _docs_ repository.
   ###### Contains the initial performance and functional tests for Mojaloop assets.
   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/docs/blob/master/Test/ilp-integration/README.md)|Shows initial attempt at providing performance and functional tests for Mojaloop assets.|

   ##### Performance
   Click on [performance](https://github.com/mojaloop/docs/tree/master/Test/performance) to navigate to the _performance_ sub directory in the _Test_ directory within the _docs_ repository.
   ###### L1P Performance testing framework.
   |Artefact|Artefact Description|
   |---|---|
   |[Performance Testing Summary.pdf](https://github.com/mojaloop/docs/blob/develop/Test/performance/Performance%20Testing%20Summary.pdf)|Provides insight into the L1P Performance Testing Framework.|


### Helm
  Click on [helm](https://github.com/mojaloop/helm) to navigate to the _helm_ repository.
  ##### A collection of _chart_ files that describe a related set of Kubernetes resources. The _charts_ are packaged into versioned archives to be deployed.
  |Artefact|Artefact Description|
  |---|---|
  |[README.md](https://github.com/mojaloop/helm/blob/master/README.md)|A guide in assisting with the following:<ul><li>Deployment from Repo</li><li>Upgrading Deployments from Repo</li><li>Update Chart Dependencies for Source</li><li>Deployment from Source</li><li>Upgrading Deployments from Source</li><li>Testing Deployments</li><li>Removing Deployments</li><li>Debugging Charts</li><li>Helper scripts for deploying Ingress, deploying Central and Package charts.</li></ul>

### Interop-common
  Click on [Interop-common](https://github.com/mojaloop/interop-common) to navigate to the _Interop-common_ repository.
  ##### This is a common project package as a library for all interop projects such as interop-domain, interop-dfsp-directory, interop-ilp-ledger and interop-scheme-adapter.
  |Artefact|Artefact Description|
  |---|---|
  |[LICENSE.md](https://github.com/mojaloop/interop-common/blob/master/LICENSE.md)|Project Licensing information.|
  |[README.md](https://github.com/mojaloop/interop-common/blob/master/README.md)|Steps through the following related contents:<ul><li>[Deployment]()</li><li>[Configuration]()</li><li>[API]()</li><li>[Logging]()</li><li>[Tests]()</li></ul>|

### Interop-devops
  Click on [Interop-devops](https://github.com/mojaloop/interop-devops) to navigate to the _Interop-devops_ repository.
  ##### Describes the various scenarios of deploying L1P system, currently in a local setting.
  |Artefact|Artefact Description|
  |---|---|
  |[Endpoint_details.md](https://github.com/mojaloop/interop-devops/blob/master/Endpoint_details.md)|Local L1P Instance Information.|
  |[LICENSE.md](https://github.com/mojaloop/interop-devops/blob/master/LICENSE.md)|Project Licensing information.|
  |[README.md](https://github.com/mojaloop/interop-devops/blob/master/README.md)|Guide the reader through the various scenarios of deploying an local L1P system by stepping through the following topics:<ul><li>[Deployment](https://github.com/mojaloop/interop-devops/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/interop-devops/blob/master/README.md#configuration)</li><li>[API](https://github.com/mojaloop/interop-devops/blob/master/README.md#api)</li><li>[Logging](https://github.com/mojaloop/interop-devops/blob/master/README.md#logging)</li><li>[Tests](https://github.com/mojaloop/interop-devops/blob/master/README.md#tests)</li></ul>|
  |[README_EC2.md](https://github.com/mojaloop/interop-devops/blob/master/README_EC2.md)|Guide the reader through the various scenarios of deploying a Amazon EC2 environment for L1P system by stepping through the following topics:<ul><li>[Deployment](https://github.com/mojaloop/interop-devops/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/interop-devops/blob/master/README.md#configuration)</li><li>[API](https://github.com/mojaloop/interop-devops/blob/master/README.md#api)</li><li>[Logging](https://github.com/mojaloop/interop-devops/blob/master/README.md#logging)</li><li>[Tests](https://github.com/mojaloop/interop-devops/blob/master/README.md#tests)</li></ul>|

### Interop-domain
  Click on [Interop-domain](https://github.com/mojaloop/interop-domain) to navigate to the _Interop-domain_ repository.
  ##### Domain project for interop projects. This repo contains a project that contains shared properties, configurations and metrics.
  |Artefact|Artefact Description|
  |---|---|
  |[LICENSE.md](https://github.com/mojaloop/interop-domain/blob/master/LICENSE.md)|Project Licensing information.|
  |[README.md](https://github.com/mojaloop/interop-domain/blob/master/README.md)|Steps through the following related contents:<ul><li>[Deployment](https://github.com/mojaloop/interop-domain/tree/master#deployment)</li><li>[Configuration](https://github.com/mojaloop/interop-domain/tree/master#configuration)</li><li>[API](https://github.com/mojaloop/interop-domain/tree/master#api)</li><li>[Logging](https://github.com/mojaloop/interop-domain/tree/master#logging)</li><li>[Tests](https://github.com/mojaloop/interop-domain/tree/master#tests)</li></ul>|

### Interop-parent
  Click on [Interop-parent](https://github.com/mojaloop/interop-parent) to navigate to the _Interop-parent_ repository.
  ##### Contains a POM file that contains all the dependencies required for all the interop related projects.
  |Artefact|Artefact Description|
  |---|---|
  |[LICENSE.md](https://github.com/mojaloop/interop-parent/blob/master/LICENSE.md)|Project Licensing information.|
  |[README.md](https://github.com/mojaloop/interop-parent/blob/master/README.md)|Steps through the following related contents:<ul><li>[Deployment](https://github.com/mojaloop/interop-parent#deployment)</li><li>[Configuration](https://github.com/mojaloop/interop-parent#configuration)</li></ul>|

### Mojaloop
  Click on [Mojaloop](https://github.com/mojaloop/mojaloop) to navigate to the _Mojaloop_ repository.
  ##### Provides an overview of the project and navigates the reader Starting point for on-boarding and contribution documentation for Mojaloop.
   ##### Contribute
   Click on [contribute](https://github.com/mojaloop/mojaloop/tree/master/contribute) to go to the _contribute_ sub directory in the _mojaloop_ repository.
   ##### Contains helpful artefacts about Mojaloop. Also provides guidelines how to contribute to the project as a community member.|
   |Artefact|Artefact Description|
   |---|---|
   |[Architecture-Documentation-Guidelines.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Architecture-Documentation-Guidelines.md)|Guidelines for creating project documentation.|
   |[Branching-Strategy.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Branching-Strategy.md)|Explain the GitHub branching strategy the Mojaloop project is following and how to comply to the strategy.|
   |[Build-and-Publish-NodeJS.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Build-and-Publish-NodeJS.md)|Guide the reader how to Publish to the Private Repo and Install from the Private Repo.|
   |[Code-Quality-Metrics.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Code-Quality-Metrics.md)|The quality metrics and what is expected are published within this document.|
   |[Code-Style.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Code-Style.md)|The coding standards and guidelines.|
   |[Decision-Items.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Decision-Items.md)|Provides information with regards to the Mojaloop project design decisions.|
   |[Documentation-Style-Guide.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Documentation-Style-Guide.md)|Provides the style guide standards to be followed for documentation on the Mojaloop.|
   |[Documentation-and-Template-Standards.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Documentation-and-Template-Standards.md)|Provides the standards to be followed for documents and templates.|
   |[GitHub-Labels.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/GitHub-Labels.md)|Explain the current GitHub label in use by the Mojaloop.|
   |[License.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/License.md)|Project Licensing information.|
   |[Moving-issues-from-docs-to-another-repo.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Moving-issues-from-docs-to-another-repo.md)|Guidelines to move documentation from one repo to another.|
   |[Pipeline.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Pipeline.md)|Explain the project pipelines used within GitHub.|
   |[Pragmatic-REST-Guidelines.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Pragmatic-REST-Guidelines.md)|Provides insight into the use of design pattern adopted for the Mojaloop API services.|
   |[README-Template.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/README-Template.md)|A sample template for the README file when you create a repository for a new (micro)service or application under the Mojaloop organization.|
   |[Readme.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Readme.md)|Provides the reader with the Mojaloop onboarding information, issue tracking and project management guidelines. These are divided into appropriate sections with links to the relevant documentation:<ul>Mojaloop Onboarding Information;<ul><li>Mojaloop Deployment and Setup Guide</li><li>Documentation</li><li>Tool and Design Choices</li></ul></ul><ul>Issue Tracking and Project Management;<ul><li>Development Information</li><li>Testing Information</li><li>Other Information</li></ul></ul>|
   |[Reporting-Bugs.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Reporting-Bugs.md)|Guidelines on how to submit a bug report for Mojaloop.|
   |[Repos-and-versioning.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Repos-and-versioning.md)|Explains the use , naming and versioning of GitHub repos.|
   |[Roadmap.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Roadmap.md)|Provides the current Roadmap for the Mojaloop.|
   |[Scenarios-and-Epics.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Scenarios-and-Epics.md)|Defines Scenarios and Epics and the use of them within the Mojaloop project.|
   |[Structure-of-the-Documentation.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Structure-of-the-Documentation.md)|Defines the structure of Mojaloop documentation.|
   |[Terminology.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Terminology.md)|Defines the preferred terms and definitions for Mojaloop.|
   |[Testing-strategy.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Testing-strategy.md)|Defines the testing strategy employed by Mojaloop.|
   |[Tools-technology-and-process-choices.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Tools-technology-and-process-choices.md)|This document describes the reasoning behind certain tools, technology and process choices for Mojaloop.|
   |[Writing-Code.md](https://github.com/mojaloop/mojaloop/blob/master/contribute/Writing-Code.md)|A guideline for writing code within Mojaloop.|

### Mojaloop.github.io
  Click on [Mojaloop.github.io](https://github.com/mojaloop/mojaloop.github.io) to navigate to the _Mojaloop.github.io_ repository.
  ##### Host environment for the GitHub website pages.
  |Artefact|Artefact Description|
  |---|---|
  |[LICENSE.md](https://github.com/mojaloop/mojaloop.github.io/blob/master/LICENSE.md)|Project Licensing information.|

### Mojaloop-specifications
  Click on [Mojaloop-specifications](https://github.com/mojaloop/Mojaloop-specifications) to navigate to the _Mojaloop specifications_ repository.
  ##### Contains the specification document set of the Open API for FSP Interoperability Specification.
   |Artefact|Artefact Description|
   |---|---|
   |[API Definition v1.0.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/API%20Definition%20v1.0.pdf)|API definition.|
   |[Encryption.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/Encryption.pdf)|API encryption Specification.|
   |[Generic Transaction Patterns.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/Generic%20Transaction%20Patterns.pdf)|Introduces the four generic transaction patterns that are supported in a logical version of the Interoperability API. All logical services that are part of the API are presented on a high-level.|
   |[Glossary.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/Glossary.pdf)|Glossary for the Open API for FSP Interoperability Specification.|
   |[JSON Binding Rules.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/JSON%20Binding%20Rules.pdf)|This document express the data model used by the Open API for FSP Interoperability in the form of JSON Schema binding rules, along with the validation rules for their corresponding instances.|
   |[LICENSE.md](https://github.com/mojaloop/mojaloop-specification/blob/master/LICENSE.md)|Project Licensing information.|
   |[Logical Data Model.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/Logical%20Data%20Model.pdf)|Specifies the logical data model used by the Open API for FSP Interoperability:<ul><li>listing the elements used by each service,</li><li>describes the data model in terms of basic elements, simple data types and complex data types.</li></ul>|
   |[PKI Best Practices.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/PKI%20Best%20Practices.pdf)|Explains the Public Key Infrastructure (PKI) best practices to apply in an Open API for FSP Interoperability deployment.|
   |[README.md](https://github.com/mojaloop/mojaloop-specification/blob/master/README.md)|Lists and categorize documents contained in this repository.<ul>General Documents<ul><li>[Glossary](https://github.com/mojaloop/mojaloop-specification/tree/master#glossary)</li></ul></ul><ul>Logical Documents<ul><li>[Logical Data Model](https://github.com/mojaloop/mojaloop-specification/tree/master#logical-data-model)</li><li>[Generic Transaction Patterns](https://github.com/mojaloop/mojaloop-specification/tree/develop#generic-transaction-patterns)</li><li>[Use Cases](https://github.com/mojaloop/mojaloop-specification/tree/develop#use-cases)</li></ul></ul><ul>Asynchronous REST Binding Documents<ul><li>[API Definition](https://github.com/mojaloop/mojaloop-specification/tree/develop#api-definition)</li><li>[JSON Binding Rules](https://github.com/mojaloop/mojaloop-specification/tree/develop#json-binding-rules)</li><li>[Scheme Rules](https://github.com/mojaloop/mojaloop-specification/tree/develop#scheme-rules)</li></ul></ul><ul>Data Integrity, Confidentiality, and Non-Repudiation<ul><li>[PKI Best Practices](https://github.com/mojaloop/mojaloop-specification/tree/develop#pki-best-practices)</li><li>[Signature](https://github.com/mojaloop/mojaloop-specification/tree/develop#signature)</li><li>[Encryption](https://github.com/mojaloop/mojaloop-specification/tree/develop#encryption)</li></ul></ul>|
   |[Scheme Rules.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/Scheme%20Rules.pdf)|Defines scheme rules for Open API for FSP Interoperability in three categories:<ul><li>Business Scheme Rules,</li><li>API implementation Scheme Rules,</li><li>Security and Non-Functional Scheme Rules.</li></ul>|
   |[Signature.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/Signature.pdf)|Details the security methods to be implemented for the Open API for FSP Interoperability to ensure integrity and non-repudiation between the API client and the API server.|
   |[Use Cases.pdf](https://github.com/mojaloop/mojaloop-specification/blob/master/Use%20Cases.pdf)|This document is to define a set of use cases that can be implemented using the API.|

### Postman
 Click on [Postman](https://github.com/mojaloop/Postman) to navigate to the _Postman_ repository.
 ##### Postman collection and Environments.
 |Artefact|Artefact Description|
 |---|---|
 |[LICENSE.md]()|Project Licensing information.|
 |[README.md]()|Provide the following up to date information:<ul><li>Version of Postman Collection,</li><li>Supported Mojaloop Versions,</li><li>Import the following Postman Collection to be imported into your Client - local development and K8s cluster on docker container.</li></ul>|

### Project
  Click on [project](https://github.com/mojaloop/project) to navigate to the _project_ repository.
  ##### Repo to track product development issues for the Mojaloop project.
  |Artefact|Artefact Description|
  |---|---|
  |[README.md](https://github.com/mojaloop/project/blob/master/README.md)|Information related to the project.|

### Test-scripts
 Click on [Test-scripts](https://github.com/mojaloop/Test-scripts) to navigate to the _Test-scripts_ repository.
 ##### Contains the scripts and code-base for functional tests, contract tests, Jmeter tests used for performance and related logs.
 |Artefact|Artefact Description|
 |---|---|
 |[LICENSE.md](https://github.com/mojaloop/test-scripts/blob/master/LICENSE.md)|Project Licensing information.|
 |[README.md](https://github.com/mojaloop/test-scripts/blob/master/README.md)|Explains the purpose and navigates through the repository:<ul><li>[Deployment](https://github.com/mojaloop/test-scripts/tree/master#deployment)</li><li>[Configuration](https://github.com/mojaloop/test-scripts/tree/master#configuration)</li><li>[API](https://github.com/mojaloop/test-scripts/tree/master#api)</li><li>[Logging](https://github.com/mojaloop/test-scripts/tree/master#logging)</li><li>[Tests](https://github.com/mojaloop/test-scripts/tree/master#tests)</li></ul>
