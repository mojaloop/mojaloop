_Use this template for the README file when you create a component or a service_

_This should be created in a sub-folder in the [Docs repo](https://github.com/Mojaloop/Docs), such as an architecture overview, user flow, and resilience modeling._ 


# File Formats

Mojaloop documentation uses GitHub markdown (md) files. Formatting is limited to GitHub compatible MD. 
You can use any editor to create the files including the built-in GitHub editors or an external online tool like
[StackEdit.IO](https://stackedit.io/editor) or a download like [Haroopad](http://pad.haroopress.com/), but be aware that some external tools, like StackEdit.IO, support a superset of GitHub MD and we are limiting the docs to just the GitHub
MD. [Pandoc](http://pandoc.org/) is a good tool for coverting docs to and from MD format.

Files can be viewed, reviewed, commented on, and edited directly in GitHub. One exception are diagrams, which will use the tool [Draw.IO](https://www.draw.io/). Architecture drawings saved as PNG files that are linked in mark down
files. Syntax example: \[Display Text](./images/diagram.png). Diagrams are stored in GitHub their both their a SVG format as well as PNG. PNG is used for display,but SVG is the master format used for editing. Diagrams should be referenced using a relative path like ./wiki/diagram.png, not the full path such as https://github.com/Mojaloop/Docs/blob/master/Wiki/diagram.png. For larger diagrams, put a blank line above them to allow them to be centered properly upon export.


# Template Overview

## Component/Service Name

(Intro blurb - a paragraph or two explaining what this component or service is for and how it fits into the overall Level One Project Project)

It is expected that this template would not be fully complete at the beginning of development. Design details are expected to emerge in an Agile fashion. However, the building blocks such as key components, high-level interactions, protocols, approaches, and general test strategy need to be thought through due to all the moving parts in the project. Specify enough detail such that another engineer can review the approach and provide feedback, but don't be too detailed that the architecture/design is obsolete in the very short term.  Architecture/Design documents are stored as many smaller files rather than one large one. This way individual parts of the design can be worked on separately and in parallel.

In keeping with agile development, documents can be simple diagrams and do not need to be formal UML. Some of the document names below might imply UML, and while that's fine, it is not required. These docs are meant to be living representatives of our understanding. As such, they will likely start out as rough sketches and become more formal over time.


## Contents:

- [Component Diagram](#component-diagram)
- [User Message/Flow Diagrams](#user-message-flow-diagrams)
- [Interfaces](#interfaces)
- [Test Strategy](#test-strategy)
- [Security/Threat Model](#security-threat-model)
- [Resilience Model](#resilience-model)
- [Monitoring/Health Model](#monitoring-health-model)

## Component Diagram

(This shows the sub-components of the service and their relationships. The Level One Project will have at least two levels of design, one overall system level design which shows the big picture, which the main components are and the primary connections. Each service or main component also has a set of design documents, so we can drill from the big picture into
the design of a particular service.  These design documents might exist in the specific repo.)

## User Message/Flow Diagrams

(This set of diagrams shows the positive or "happy" path of the user. Negative and boundary cases are described. A data     flow diagram is also used for threat modeling (see below).)

## Interfaces

(This shows the inputs and outputs and their types. What services/components call this and what does it call?_

Example:
<https://github.com/interledger/rfcs/blob/master/0009-simple-payment-setup-protocol/0009-simple-payment-setup-protocol.md>. 

(All APIs should be documented in Swagger, see [Open API Documentation](https://www.openapis.org/))


## Test Strategy

(This section shows how will it be possible to do functional integration testing of these components? Will we be mocking some components or interfaces?)


## Security/Threat Model

(This contains data flow diagram of the system showing components and calls. Each call is threat modeled using STRIDE. Also see [threat modeling](https://msdn.microsoft.com/en-us/library/ff648644.aspx).)

## Resilience Model
See [RMA](https://github.com/Mojaloop/Docs/blob/master/test/RMA.md)

(For background, see [resilience modeling](http://blogs.microsoft.com/cybertrust/2013/05/31/improve-the-reliability-of-your-service-with-resilience-modeling-analysis/) and the linked [white paper](http://download.microsoft.com/download/F/A/2/FA2A49AB-13AF-44FC-883C-7B8C48D8A042/Resilience-by-design-for-cloud-services.pdf).)

## Monitoring/Health Model
Largely contained in the resilience model. 

(For background, see [Health modeling](https://msdn.microsoft.com/en-us/library/ms954618.aspx).)


