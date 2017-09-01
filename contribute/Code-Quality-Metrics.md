# Functional quality metrics

## Unit test metrics
High coverage and low dependencies show that the code is testable and therefore well isolated and easy to maintain. Low complexity also makes code readable and maintainable and helps enforce single responsibility. Real unit tests run very fast as they don't call external components.

Code Quality Metrics | New and Project Code 
--------- | --------- 
Unit test coverage | >= 80% block coverage 
Unit test speed | <= 10 seconds 
Dependencies/method | <= 10 
Complexity/method | <= 7 

## Component
Functional testing typically covers pair combinations of the system states.

## Integration
Functional tests have one test per message and error. Messages and errors that are handled the same way use the same test.

## Contract
Limited to what the consuming teams need that isn't covered by existing unit, component, and integration tests. Often added to over time.

## End to End
End to end tests cover acceptance tests from scenarios.

# Non Functional

## Performance and scale

## Security
All issues on the threat model logged and triaged, all higher priority issues closed.

## Availability and System Health
