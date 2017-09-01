# Overview
A **scenario** is a customer facing work item that may be bigger than a single program increment and require work from multiple teams for one team. 
An **Epic** fits within a single PI and can be done by a single team
Scenarios are broken into multiple epics. Epics are broken into user stories. A typical epic contains 3 to 8 stories.

# Description
Both the scenario and epic contain much of the same information that the user stories does, but more of it. The customer, problem and outcomes are better defined. There are almost always multiple outcomes, as they often lead to multiple stories. 

The scenario description follows a two paragraph format:

>        Who is the customer and what is the problem from their point of view?`
>        ** product magic happens here**`
>        What are the measurable outcomes? `

The epic description _DOESN'T_ contain information about _HOW_ the problem should be solved or what technology is used, unless that technology is given in the product definition (such as the cell phone in the example below). 


## Scenario Example: 
Description

> Venya is waiting in line to buy plantains at her local market. She is corralling her elder child with one hand and has her baby in a sling. She often comes to this seller and she knows he has a good price. She also knows that even though she carries no money and he is not on her financial network, she can buy from him. As she approaches the head of the line she juggles the children and pulls out a simple flip phone. She tells him 3 pounds and he tells her the price, which she agrees to. 

> ** product magic happens here**`

> Because she’s been here before she already has the info on where to send the money in her phone. She sees his name come up on her phone when she starts the transaction. She also sees the total fees she has to pay before she sends the money. 
> She’s happy for that validation and that the transaction goes the same way every time, because half of her attention is on the children. She has friends who can’t read and they are able to buy things this way too by following the simple order of the transaction. The only thing either person sees about the other is their user numbers and the names associated with them. They don't exchange phone numbers and that also makes Venya feel more safe. In under 30 seconds, she is able to send the money to the merchant and he verifies that he got it. She tells the elder child to pick up her plantains and makes room for the next person in line.

# Acceptance Criteria
Scenarios, epics, and user stories all have acceptance criteria at different levels of granularity. 
![Tracking Requirements to Results](https://github.com/LevelOneProject/Docs/blob/master/Wiki/Tracking%20requirements%20to%20results.png)

## Example of Acceptance Criteria for the scenario above
### Measurable Outcomes (functional)
* UI follows same predictable flow (minimal branching)
* See destination name before sending
* See total fees before sending
* Works across financial institutions
* Doesn't share phone numbers or other info

### Success Measures (non-functional)
* End to end transfer is less than 30 seconds including time to enter data
* Secure

### Acceptance Criteria - a combination of the two above
* UI follows same predictable flow (minimal branching)
* See destination name and total fees before sending
* Works across financial institutions
* Secure and private, doesn't share phone numbers or other info
* End to end transfer is less than 30 seconds including time to enter data