# Paymoja Documentation and Template Standards

## Document Scopes

To prevent duplication and allow for easy maintenance, the documentation
follows a simple hierarchical pattern:

-   Overview - anything that spans the project

-   Service - specific to a single service

-   Repo - specific to a single component or microservice

More specifics are below.

## Overview Documents

Overview documents include the topics, components and or services that
span the entire Paymoja project. The documents should have their own
readme file and be located in a corresponding sub-folder in [Docs
repo](https://github.com/LevelOneProject/Docs). Examples or topics
and examples that span the entire project are included below:

-   Paymoja Overview
-   Scenarios
-   Scenario Tests
-   Cross-service architecture
-   Test strategy
-   Physical Architecture
-   Overall threat model
-   Overall resilience model

## Services Documentation

Each of the main services also have a section describing them in the Docs repo.  They should follow the template and format specified here in the [Architecture-Documentation-Guidelines](./Architecture-Documentation-Guidelines.md)


-   DFSP
-   Central Services (Overview)
-   Portal

Services docs cover the service architecture, service deployment,
configuration, health model, integration tests, and API docs. If there
are cross-service standards such as logging also include them here.

For the central services, this is information that is true for all
central service. Detail on each service is at the repo level.

## Repo Level Documents

Each time you create a new repo, the readme file should provide standard
information on the specific component/service and also make reference to
the higher level component or service located in the [Docs
repo](https://github.com/LevelOneProject/Docs). Examples or topics
that will be part of a specific repo include:

* Microservices/Components
* USSD Admin
* DFSP USSD
* Central Rules
* Fraud Services
* SPSP Client
* ILP Adapter

For these topics, please use the [README-Template](./README-Template.md)

## API Documentation

* All APIs should be documented in RAML or Swagger, see Architecture-Documentation-Guidelines](Architecture-Documentation-Guidelines.md)
* Use [Central Ledger API](https://github.com/LevelOneProject/central-ledger/blob/master/API.md) as a template.


## Formatting Guidelines

### Section Headings

* Do not number headings - for example, "Prepare and Fulfill", not "C - Prepare and Fulfill"
* Follow standards for specific section types as documented in:
  * [Overview Documents](#overview-documents)
  * [Services Documenatation](services-documentation)
  * [Repo Level Documents](#repo-level-documents)

* Make sure section headings (# _<Heading>_) match the heading to which they correspond in the comprehensive PDF (built from the [dactyl config file](https://github.com/LevelOneProject/Docs/blob/master/ExportDocs/dactyl-config.yml))
* Do not include the word "documentation" in headings

### Retrievability 

* For sections that contain many subsections of endpoints or methods, provide a table of contents at the beginning of the section
* Don't say the word project; use component, microservice, interfaces, etc

### Language

Instead of the word "project," use a specific noun such as component, microservice, or interface.

### Procedures

* Introduce procedures with H3 (###) or H4 (####) headers (not H2 (##)).
* Do not use numbers in procedure section headings.
* Use ordered-list tagging for procedure steps. For example:
1. Step 1
2. Step 2
3. Step 2