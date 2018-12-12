# Mojaloop Core Components
## Document Virtual Catalog

#### What is this document about.
This document is intended to provide the reader with an insight into the core component repositories and the documentation currently available for Mojaloop. Navigation within the document and the respective repositories are possible by following the hyper-link. This document serves to consolidate all documentation under one "virtual map" of the entire Mojaloop document suite.

#### Assumptions and related matters.
All references point to the master branch of each repository. The project development team is in the process to ensure all documentation is current and up to date as per the latest project release. Please note that we have not marked outdated documents as such and there are still many stale references.

##### The following Mojaloop core components repository are part of this document:
- [central-directory](#central-directory)
- [central-end-user-registry](#central-end-user-registry)
- [central-event-processor](#central-event-processor)
  - [docs](#docs)
    - [database](#database)
    - [images](#images)
- [central-kms](#central-kms)
- [central-ledger](#central-ledger)
- [central-services-auth](#central-services-auth)
- [central-services-database](#central-services-database)
- [central-services-error-handling](#central-services-error-handling)
- [central-services-shared](#central-services-shared)
- [central-settlement](#central-settlement)
- [email-notifier](#email-notifier)
- [forensic-logging-sidecar](#forensic-logging-sidecar)
- [interop-switch](#interop-switch)
- [mock-pathfinder](#mock-pathfinder)
- [ml-api-adapter](#ml-api-adapter)
- [ntpd](#ntpd)

## Repository

### central-directory
  Click on [central-directory](https://github.com/mojaloop/central-directory) to navigate to the central directory repository.  
  ##### A series of services that allows DFSPs to register and retrieve scheme identifiers. The scheme identifier can be leveraged by DFSPs for end-user discovery.
   |Artefact|Artefact Description|
   |---|---|
   |[API.md](https://github.com/mojaloop/central-directory/tree/master.API.md)|Provides the definition of the API including the different central directory endpoints.|
   |[KUBERNETES.md](https://github.com/mojaloop/central-directory/tree/master/KUBERNETES.md)|Guide to install and run central-directory on Kubernetes.|
   |[LICENSE.md](https://github.com/mojaloop/central-directory/tree/master/KUBERNETES.md)|Project Licensing information.|
   |[Onboarding.md](https://github.com/mojaloop/central-directory/tree/master/KUBERNETES.md)|In this document we'll guide developers through the setup for the Central Directory. It consists of the following sections:<ul><li>[Software List](https://github.com/mojaloop/central-directory/blob/develop/Onboarding.md#software-list)</li><li>[Setup](https://github.com/mojaloop/central-directory/blob/develop/Onboarding.md#setup)</li><li>[Errors On Setup](https://github.com/mojaloop/central-directory/blob/develop/Onboarding.md#errors-on-setup)</li></ul>|
   |[README.md](https://github.com/mojaloop/central-directory/tree/master/README.md)|Provides an overview of services. The following documentation represents the services, APIs and endpoints responsible for registering a DFSP, adding an end user, and retrieving an end user.<ul><li>[Deployment](https://github.com/mojaloop/central-directory/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/central-directory/blob/master/README.md#configuration)</li><li>[API](https://github.com/mojaloop/central-directory/blob/master/README.md#api)</li><li>[Authentication](https://github.com/mojaloop/central-directory/blob/master/README.md#api)</li><li>[Logging](https://github.com/mojaloop/central-directory/blob/master/README.md#api)</li><li>[Tests](https://github.com/mojaloop/central-directory/blob/master/README.md#tests)</li></ul>|
   |[UserRetrievalGuide.md](https://github.com/mojaloop/central-directory/tree/master/UserRetrievalGuide.md)|In this guide, we'll walk through the different steps of successfully retrieving a user from the Central Directory.<ul><li>[Registering a user with the Central End User Registry](https://github.com/mojaloop/central-directory/blob/master/UserRetrievalGuide.md#step-1-register-a-user-with-the-central-end-user-registry)</li><li>[Registering a DFSP with the Central Directory](https://github.com/mojaloop/central-directory/blob/master/UserRetrievalGuide.md#step-2-register-a-dfsp-with-the-central-directory)</li><li>[Looking up a user in the Central Directory](https://github.com/mojaloop/central-directory/blob/master/UserRetrievalGuide.md#step-3-look-up-a-user-in-the-central-directory)</li><li>[Next Steps](https://github.com/mojaloop/central-directory/blob/master/UserRetrievalGuide.md#next-steps)</li></ul>|

### central-end-user-registry
  Click on [central-end-user-registry](https://github.com/mojaloop/central-end-user-registry) to navigate to the central end user registry repository.  
  ##### Fake end user registry and number generator.
   |Artefact|Artefact Description|
   |---|---|
   |[API.md](https://github.com/mojaloop/central-end-user-registry/blob/master/API.md)|Provides information regarding the different Central End User Registry endpoints.|
   |[KUBERNETES.md](https://github.com/mojaloop/central-end-user-registry/blob/master/KUBERNETES.md)|Guide to install and run central-end-user-registry on Kubernetes.|
   |[LICENSE.md](https://github.com/mojaloop/central-end-user-registry/blob/master/LICENSE.md)|Project Licensing information.|
   |[Onboarding.md](https://github.com/mojaloop/central-end-user-registry/blob/master/Onboarding.md)|In this document we'll guide developers through the setup for the Central End User Registry. It consists of three sections:<ul><li>[Software List](https://github.com/mojaloop/central-end-user-registry/blob/master/Onboarding.md#software-list)</li><li>[Setup](https://github.com/mojaloop/central-end-user-registry/blob/master/Onboarding.md#setup)</li><li>[Errors On Setup](https://github.com/mojaloop/central-end-user-registry/blob/master/Onboarding.md#setup)</li></ul>|
   |[README.md](https://github.com/mojaloop/central-end-user-registry/blob/master/README.md)|Provides an overview of services. The following documentation represents the services, APIs and endpoints responsible for various end user registry functions:<ul><li>[Deployment](https://github.com/mojaloop/central-end-user-registry/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/central-end-user-registry/blob/master/README.md#deployment)</li><li>[API](https://github.com/mojaloop/central-end-user-registry/blob/master/README.md#api)</li><li>[Logging](https://github.com/mojaloop/central-end-user-registry/blob/master/README.md#logging)</li><li>[Tests](https://github.com/mojaloop/central-end-user-registry/blob/master/README.md#tests)</li></ul>|

### central-event-processor
  Click on [central-event-processor](https://github.com/mojaloop/docs/tree/master/Central-event-processor) to navigate to central event processor repository.
  ##### Standalone service that process events based on set of rules. Currently used to monitor the notification topic and create various notifications (e.g. email, etc).
   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/central-event-processor/blob/master/README.md)|Provides an overview of the event processor and notification service.|
   |[LICENSE.md](https://github.com/mojaloop/central-event-processor/blob/master/LICENSE.md)|Project Licensing information.

  #### docs
  Click on [docs](https://github.com/mojaloop/central-event-processor/tree/master/docs) to navigate to docs directory within the central event processor repository.
  ###### Contains the public documents and high block diagrams for the Central Event Processor service.  
   ##### Database
   Click on [database](https://github.com/mojaloop/central-event-processor/tree/master/docs/database) to navigate to database directory within the docs directory within the central event processor repository.
   ###### Contains the public document for the Central Event Processor database design.
   |Artefact|Artefact Description|
   |---|---|
   |[Mojaloop_central-notifications_Db_ver1.0.html](https://github.com/mojaloop/central-event-processor/blob/master/docs/database/Mojaloop_central-notifications_Db_ver1.0.html)|Provides an overview of the Central Event Processor notifications service database design.|
   ##### images
   Click on [images](https://github.com/mojaloop/central-event-processor/tree/master/docs/images) to navigate to images directory within the docs directory within the central event processor repository.
   ###### Contains the public documents and high level block diagrams for the Central Event Processor and processes.
   |Artefact|Artefact Description|
   |---|---|
   |[1.png](https://github.com/mojaloop/central-event-processor/blob/master/docs/images/1.png)|Rest API calls for this Central Notifications serves.|
   |[2.png](https://github.com/mojaloop/central-event-processor/blob/master/docs/images/2.png)|Notification System general process overview.|
   |[3.png](https://github.com/mojaloop/central-event-processor/blob/master/docs/images/3.png)|Limit adjustment rule validation.|
   |[4.png](https://github.com/mojaloop/central-event-processor/blob/master/docs/images/4.png)|Limit position breach.|
   |[5.png](https://github.com/mojaloop/central-event-processor/blob/master/docs/images/5.png)|Action flow.|
   |[6.png](https://github.com/mojaloop/central-event-processor/blob/master/docs/images/6.png)|Notifier service.|

### central-kms
  Click on [central-kms](https://github.com/mojaloop/central-kms) to navigate to the central kms repository.  
  ##### Central Key Management Service facilitates forensic logging functionality for central services.
   |Artefact|Artefact Description|
   |---|---|
   |[KUBERNETES.md](https://github.com/mojaloop/central-kms/blob/master/KUBERNETES.md)|Guide to install and run central-kms on Kubernetes.|
   |[LICENSE.md](https://github.com/mojaloop/central-kms/blob/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/central-kms/blob/master/LICENSE.md)|Provides an overview of services. The following document represents the services, APIs and endpoints responsible for various logging functions:<ul><li>[Configuration](https://github.com/mojaloop/central-kms/blob/master/README.md#configuration)</li><li>[API](https://github.com/mojaloop/central-kms/blob/master/README.md#api)</li><li>[Socket](https://github.com/mojaloop/central-kms/blob/master/README.md#socket)</li><li>[Logging](https://github.com/mojaloop/central-kms/blob/master/README.md#logging)</li></ul>|

### central-ledger
  Click on [central-ledger](https://github.com/mojaloop/central-ledger) to navigate to the central ledger repository.
  ##### The central ledger is a series of services that facilitate clearing and settlement of transfers between DFSPs, including the following functions:<ul><li>Brokering real-time messaging for funds clearing,</li><li>Maintaining net positions for a deferred net settlement,</li><li>Propagating scheme-level and off-transfer fees.</li></ul>
   |Artefact|Artefact Description|
   |---|---|
   |[API.md](https://github.com/mojaloop/central-ledger/blob/master/API.md)|Provides the definition of the central ledger API. The API consist of two different consumers:<ul><li>API is used to prepare and execute transfers.</li><li>Admin API is used by the operational hub to manage DFSPs and ensure the health of the system.</li></Ul>|
   |[KUBERNETES.md](https://github.com/mojaloop/central-ledger/blob/master/KUBERNETES.md)|Guide to install and run central-ledger on Kubernetes.|
   |[LICENSE.md](https://github.com/mojaloop/central-ledger/blob/master/LICENSE.md)|
   |[Onboarding.md](https://github.com/mojaloop/central-ledger/blob/master/Onboarding.md)|This document we'll guide developers through the setup of Mojaloop Central Ledger. The following sections are covered:<ul><li>[Software List](https://github.com/mojaloop/central-ledger/blob/master/Onboarding.md#software-list)</li><li>[Setup](https://github.com/mojaloop/central-ledger/blob/master/Onboarding.md#setup)</li>[Errors On Setup](https://github.com/mojaloop/central-ledger/blob/master/Onboarding.md#errors-on-setup)</li></ul>|
   |[README.md](https://github.com/mojaloop/central-ledger/blob/master/README.md)|Provides an overview of Central Ledger services. The following documentation represents the Central Ledger services. APIs and endpoints responsible for various ledger functions:<ul><li>[Deployment](https://github.com/mojaloop/central-ledger/tree/master#deployment)</li><li>[Configuration](https://github.com/mojaloop/central-ledger/tree/master#configuration)</li><li>[API](https://github.com/mojaloop/central-ledger/tree/master#api)</li><li>[Logging](https://github.com/mojaloop/central-ledger/tree/master#logging)</li><li>[Tests](https://github.com/mojaloop/central-ledger/tree/master#tests)</ul></li>|
   |[TransferGuide.md](https://github.com/mojaloop/central-ledger/blob/master/TransferGuide.md)|This guide will walk through the different steps of successfully executing a transfer:<ul><li>[Creating accounts](https://github.com/mojaloop/central-ledger/blob/master/TransferGuide.md#step-1-creating-accounts)</li><li>[Preparing a transfer](https://github.com/mojaloop/central-ledger/blob/master/TransferGuide.md#step-2-preparing-a-transfer)</li><li>[Executing a transfer](https://github.com/mojaloop/central-ledger/blob/master/TransferGuide.md#step-3-executing-a-transfer)</li><li>[Next Steps](https://github.com/mojaloop/central-ledger/blob/master/TransferGuide.md#next-steps)</ul></li>|

### central-services-auth
  Click on [central-services-auth](https://github.com/mojaloop/central-services-auth) to navigate to the central services auth repository.  
  ##### Share authentication and authorization code for central services.
   |Artefact|Artefact Description|
   |---|---|
   |[LICENSE.md](https://github.com/mojaloop/central-services-auth/blob/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/central-services-auth/blob/master/README.md)|Provides information on the authentication requirements by validating a username and password combination.|

### central-services-database
  Click on [central-services-database](https://github.com/mojaloop/central-services-database) to navigate to the central services database repository.
  ##### Shared database code for central services.
   |Artefact|Artefact Description|
   |---|---|
   |[LICENSE.md](https://github.com/mojaloop/central-services-database/blob/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/central-services-database/blob/master/README.md)|High level explanation of the service. (document content to be provided by project team).|

### central-services-error-handling
  Click on [central-services-error-handling](https://github.com/mojaloop/central-services-error-handling) to navigate to the central services error handling repository.  
  ##### Hapi error handling module.
   |Artefact|Artefact Description|
   |---|---|
   |[LICENSE.md](https://github.com/mojaloop/central-services-error-handling/blob/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/central-services-error-handling/blob/master/README.md)|Hapi error handling module.|

  To read more about the hapi module click [here.](hapi.jshttps://hapijs.com/)

  Additional reading - How to use HAPI - [open API](https://github.com/mojaloop/central-services-error-handling/blob/master/how-to-use-hapi-openapi.md)

### central-services-shared
  Click on [central-services-shared](https://github.com/mojaloop/central-services-shared) to navigate to the central services shared repository.  
  ##### Shared code for central services, use the shared Logger class.
   |Artefact|Artefact Description|
   |---|---|
   |[LICENSE.md](https://github.com/mojaloop/central-services-shared/tree/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/central-services-shared/tree/master/README.md)|Provides information on how to use the shared Logger class.|

### central-settlement
  Click on [central-settlement](https://github.com/mojaloop/central-settlement) to navigate to the central settlement repository.
  ##### Service to expose the Mojaloop settlements API.
   |Artefact|Artefact Description|
   |---|---|
   |[API.md](https://github.com/mojaloop/central-settlement/blob/master/API.md)|Document providing the definition, operations and end points for the Settlement Service. (Document content to be provided by project team).|
   |[LICENSE.md](https://github.com/mojaloop/central-settlement/master/LICENSE.md)|Project Licensing information.|
   |[Onboarding.md](https://github.com/mojaloop/central-settlement/blob/master/Onboarding.md)|Document to guide developers through the setup process for Central Settlements. (document content to be provided by project team).|
   |[README.md](https://github.com/mojaloop/central-settlement/blob/master/README.md)|High level explanation of the service. This service is currently still being developed. Content will be updated as project progress.|
   |[TransferGuide.md](https://github.com/mojaloop/central-settlement/blob/master/TransferGuide.md)|Document to guide through the Settlement process.(document content to be provided by project team).|

### email-notifier
  Click on [email-notifier](https://github.com/mojaloop/email-notifier) to navigate to the email notifier repository.
  ##### Stand-alone email service that consumes messages from kafka topic, produced by the central-notifications service. 
   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/email-notifier/blob/master/README.md)|The document will guide you to the following:<ul><li>Central Notification Service</li><li>Configuration required for email notifications.</li></ul>
   |[LICENSE.md](https://github.com/mojaloop/email-notifier/blob/master/LICENSE.md)|Project Licensing information.|

### forensic-logging-sidecar
  Click on [forensic-logging-sidecar](https://github.com/mojaloop/forensic-logging-sidecar) to navigate to the forensic logging sidecar repository.
  ##### The sidecar is a service that acts as an intermediary to facilitate messaging between the services and central kms.
   |Artefact|Artefact Description|
   |---|---|
   |[FLS-review-for-THREAT-modeling.md](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/FLS-review-for-THREAT-modeling.md)|General information regarding tasks performed and observations.|
   |[KUBERNETES.md](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/KUBERNETES.md)|Guide to install and run forensic-logging-sidecar on Kubernetes.|
   |[LICENSE.md](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/README.md)|Provides an overview of the service. The following documentation represents the services and endpoints responsible for various sidecar functions:<ul><li>[Deployment](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/README.md#configuration)</li><li>[Connect And Write](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/README.md#connect-and-write)</li><li>[Logging](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/README.md#logging)</li><li>[Tests](https://github.com/mojaloop/forensic-logging-sidecar/blob/master/README.md#tests)</li></ul>

### interop-switch
  Click on [interop-switch](https://github.com/mojaloop/interop-switch) to navigate to the interop switch repository.
  ##### Implementation of Mojaloop API that provides the main features of lookup, quote.
   |Artefact|Artefact Description|
   |---|---|
   |[LICENSE](https://github.com/mojaloop/interop-switch/blob/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/interop-switch/blob/master/README.md)|Interop-account-lookup - provides the implementation of participants and its associated endpoints in PDP API:<ul><li>[Deployment](https://github.com/mojaloop/interop-switch/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/interop-switch/blob/master/README.md#configuration)</li><li>[API](https://github.com/mojaloop/interop-switch/blob/master/README.md#api)</li><li>[Logging](https://github.com/mojaloop/interop-switch/blob/master/README.md#logging)</li><li>[Tests](https://github.com/mojaloop/interop-switch/blob/master/README.md#tests)</li><li>[Docker](https://github.com/mojaloop/interop-switch/blob/master/README.md#docker)</li></ul>|

### mock-pathfinder
  Click on [mock-pathfinder](https://github.com/mojaloop/mock-pathfinder) to navigate to the mock pathfinder repository.
  ##### Mock PathFinder server for development and testing.
   |Artefact|Artefact Description|
   |---|---|
   |[API.md](https://github.com/mojaloop/mock-pathfinder/blob/master/API.md)|Provide details for the two supported APIs:<ul><li>the Query API over DNS,</li><li>the Provisioning API over SOAP.</li></ul>|
   |[KUBERNETES.md](https://github.com/mojaloop/mock-pathfinder/blob/master/KUBERNETES.md)|Guide to install and run mock-pathfinder on Kubernetes.|
   |[LICENSE.md](https://github.com/mojaloop/mock-pathfinder/blob/master/LICENSE.md)|Project Licensing information.|
   |[README.md](https://github.com/mojaloop/mock-pathfinder/blob/master/README.md)|Provides information on the intend service including advising on the use of a local version for testing and development purposes:<ul><li>[Deployment](https://github.com/mojaloop/mock-pathfinder/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/mock-pathfinder/blob/master/README.md#configuration)</li><li>[API](https://github.com/mojaloop/mock-pathfinder/blob/master/README.md#api)</li><li>[Logging](https://github.com/mojaloop/mock-pathfinder/blob/master/README.md#logging)</li><li>[Tests](https://github.com/mojaloop/mock-pathfinder/blob/master/README.md#tests)</li></ul>|

### ml-api-adapter
  Click on [ml-api-adapter](https://github.com/mojaloop/ml-api-adapter) to navigate to the ml-api-adapter repository.
  ##### The ml api adapter facilitate clearing and settlement of transfers between DFSPs, including the following functions:<ul><li>Brokering real-time messaging for funds clearing,</li><li>Maintaining net positions for a deferred net settlement,</li><li>Propagating scheme-level and off-transfer fees.</li></ul>
   |Artefact|Artefact Description|
   |---|---|
   |[API.md]()|Provides the definition of the Mojaloop API.|
   |[LICENSE.md]()|Project Licensing information.|
   |[Onboarding.md]()|This document we'll guide developers through the setup for the Mojaloop API adapter. It consists of three sections:<ul><li>[Software List](https://github.com/mojaloop/ml-api-adapter/blob/master/Onboarding.md#software-list)</li><li>[Setup](https://github.com/mojaloop/ml-api-adapter/blob/master/Onboarding.md#setup)</li><li>[Errors On Setup](https://github.com/mojaloop/ml-api-adapter/blob/master/Onboarding.md#setup)</ul></li>
   |[README.md]()|Provides an overview of services. The following documentation represents the services, APIs and endpoints responsible for various ledger functions:<ul><li>[Deployment](https://github.com/mojaloop/ml-api-adapter/blob/master/README.md#deployment)</li><li>[Configuration](https://github.com/mojaloop/ml-api-adapter/blob/master/README.md#configuration)</li><li>[API](https://github.com/mojaloop/ml-api-adapter/blob/master/README.md#api)</li><li>[Logging](https://github.com/mojaloop/ml-api-adapter/blob/master/README.md#logging)</li><li>[Tests](https://github.com/mojaloop/ml-api-adapter/blob/master/README.md#tests)</ul></li>

### ntpd
  Click on [ntpd](https://github.com/mojaloop/ntpd) to navigate to the ntpd repository.  
  ##### Contains configuration files for building a dockerized ntp daemon using alpine linux.
   |Artefact|Artefact Description|
   |---|---|
   |[README.md](https://github.com/mojaloop/ntpd/blob/master/README.md)|Contains sample command line to start docker container. (Document content to be updated by development team).|

