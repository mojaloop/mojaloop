# Phase 3 Roadmap
Competition for Phase 3 is scheduled for February 2019

## Functional Epics
* Event Logging Framework: Support operational reporting and auditing of processing
* Error Handling Framework: Consistent reporting in line with specification and support operational auditing
* API Gateway: Provide role, policy-based access, security, abstraction, throttling & control, identity management
* Endpoints for P2P, Merchant: Provide endpoints to support P2P and Merchant payments
* Settlements: Complete settlements process to handle failures and reconciliation positions
* Central directory/Account lookup service: Provide native implementation for ALS to confirm the API specification to provide user lookup
* Fraud & Risk Management System: Provide support for a fraud and risk management system
* Forensic Logging: Support forensic logging to support auditing and reporting
* Reporting API: Provide an API for reporting
	
## Operational Epics
* Testing Framework: Provide a framework for automated regression, functional and other testing to ensure quality 
* Performance Improvements: Provide a framework for automated regression, functional and other testing to ensure quality 
* ELK framework & logging: Provide framework or dashboards for Operational support, Debugging and Resolving issues 
* DevOps: Provide flexibility, dynamism in deployments, improve monitoring and reliability mechanisms
* Rules Engine: Provide a framework to enforce, implement Business, Scheme rules

## Non-Functional Epics
* Deprecate Postgres: Avoid usage of multiple databases to improve supportability and maintenance and move to MySQL
* Security & Threat Modeling: Address security vulnerabilities, issues and provide a report on status of the System’s security so that they can be addressed
* Documentation: Update documentation to support adoption by community, for labs, deployment by various partners
* API-Led Design: Refactor central services so that schema validation, paths can be addressed thoroughly (automatically) and decrease maintenance, development effort (for those services don’t already follow this)
	* API-led connectivity is a methodical way to connect data to applications through reusable and purposeful APIs.

# Beyond Phase 3
Below is a list of larger initiatives and epics by area that will help to further develop the Mojaloop project. Some of these have been entered as epics or stories, but most are still in the "concept" phase.

## Functional Epics
* Native Implementation P2P: Implementation of resources to support Payee initiated and other Use Cases from the Specification, along with supporting P2P Use case completely
* Native Implementation Payee: Implementation of resources to support Payee initiated transactions and ones that involve OTPs
* Bulk Payments: Design & Implementation of resources to support Bulk Payments

## Central Services
* Directory Interoperability
* Multi-currency and schemes
* Enforcing Currency configurations
* Fees: UI for configuring fees
* Increase performance 
* Fraud Scores and Reasons
* Role management
* DSP Management
* Stopping/Pausing a DFSP
* boarding protocol
			
## DFSP/Account Management
* Agent Network
* NFCC identity merchant
* Persistent merchant ID
* Onboarding protocol
* Change password
* Password requirements
* Hold/Restart account

## Security
* Central certificate service
* Implement fee quote transfer service in the center
* Prevent user guessing from rogue DFSPs
* Preferred authorizations
	
## Market Deployment
* Integration with major mobile money vendors in Africa (PDP initiative)
	
## CI/CD & Testing
* Implement auto deployment to test environment
* Automatically run acceptance tests in test environment as part of build/deploy
* Automate bulk import tests
* Forensic log test
* Account management test
