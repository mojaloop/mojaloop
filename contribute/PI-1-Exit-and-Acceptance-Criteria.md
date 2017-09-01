Purpose: This document describes the specific exit and acceptance criteria for planning increment #1 of the Paymoja Project.

## Limiting Assumptions
* 	PI-1 limited to “Send money to anyone anywhere”

For PI-1 we are limiting the scenario to just sending money from one person to another. Other epics and stories may be created, but they will go straight to the backlog, we're not working on them right now. 
* 	Assumed single currency for this PI.

Although we have to allow for currency exchange or vouchers later, for now we are assuming a single currency for both the money transferred and the fees.
*       Assumed two DFSPs are involved within the same country and language
*       Settlement and Clearance are postponed, though there has to be enough info to do some form of rebalancing.
*       The sending end user knows the receiver’s user number. There is no name, email, phone, or other lookup from the directory.
*       We are also postponing invoices, where the receiver sends their user number and an amount to the sender. 
*       URL and User Number can indicate the destination DFSP

As per [issue 54](https://github.com/LevelOneProject/Docs/issues/54), we are postponing the separation of the DFSP from the routing. For now the URL and user number can contain information that identifies he destination DFSP.
*       Performance 

The entire end-to-end transfer must fit with a single 30 second USSD session.
The Central ledger must handle 100 complete transfers / second
*       Threat, Fault, and Health modeling will be delayed.

We need the basic data flow diagrams before we can do these, so they are delayed till the next PI. 
*       Our DFSP must be separable

Because financial institutions will have their own DFSP code, the non-DFSP components and services of Paymoja must be able to connect through a simple set of interfaces on a proxy API to a real DFSP. We should be able to choose which services we attach, for example, if they don't need/want bulk payment, we don't have to attach it. 

* Design expecting On-premise. 

Because of poor infrastructure support by IaaS and PaaS providers and also national security issues, many countries are expected to require services to run on-premise and in-country. We can't rely on services specific to AWS or Azure for scale or resilience.

## Epics
* 	Understanding of high level Epic
*	Epics broken down into User Stories
*	Epics entered and assigned
*	Acceptances tests identified in Epics

## Stories
*	Stories needed for epics are added to GitHub and marked as “Story”
*	Stories have owners and estimates
*	Acceptance Criteria outlined in stories
*	Risk identified in Stories
*	Dependencies identified in Stories
*	Stories reviewed by teams with dependencies and signed off by Crosslake

## Architecture Documentation Design
*	Architecture for all associated stories is well defined/understood 
*	Overall Diagrams and interfaces are documented and uploaded to GitHub.
*	Data flow diagram for sending money (including account numbers and routing resolution)
	       See [Architecture Documentation Design](./Architecture-Documentation-Guidelines.md) on the GitHub wiki for additional details.

## Terminology and Glossary v1.0 completed
*       Updates to the Paymoja glossary are commonly understood
*       Any additional terms/changes in terms have been voted on and approved (CL to add them to the glossary).

## Issues/Bugs
*       No open/pending severity 1 defects or issues
