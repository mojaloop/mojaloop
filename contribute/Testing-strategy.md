# Manual and automated Testing Strategy
Regression tests are meant to cover use cases that we want to repeatedly test. These include epic and story acceptance criteria, bugs that made it beyond a sprint or main pull request, and code functionality.

We break regression tests into several types:

* **Unit** - tests the smallest functionality of the system, typically by forcing an event or state change. They test only one behavior per test. Often a unit tests validates a single path through a method or function. Stubs, dependency injection, and extract and override are often used to isolate the part under test. Unit tests do NOT test multiple components or include external dependencies like a database. These tests run very quickly (milliseconds each) and should get high code coverage. Mocks can be used to test communication with other components. Unit test code follows the Arrange, Act, Assert (AAA) pattern, and unit test names follow a good naming convention like unit_should_when (ex: Hand_ShouldHaveNoCards_WhenItsCreated). It should always be possible to know exactly what the unit test does from it's title.
* **Component** - testing the interaction between two or more components. Component tests are almost always built from a model of the system. Most systems can be modeled with stateless pair-combinations of the inputs and outputs where the test oracle implements a chain of responsibility pattern going from worst (negative) to best (positive) cases. More complicated systems may be modeled with finite state engines or petri-nets. With microservices, the component tests are all within the microservice and don't cross boundaries to external services. Component tests use much of the same stubs and code used by the unit tests. These test also run quickly.
* **Integration** - Verifies the communication between two services. For example: between the business logic and the persistence service. Because the contracts have already been tested, there are many fewer integration tests. These cover simple positive cases, verifying errors are returned, and performance.
* **Contract** - These are acceptance tests for the contract or interface and are a type of compatibility test. These tests are most often written when different teams or groups are on either sides of the interface. The tests are written by the consumer(s) of the interface, not the producer. They are run to validate that changes to the interface haven't broken systems that depend on that contract. The contract tests are white box, in that they don't duplicate the producer's unit, component, and integration tests. They often includes performance and scale tests as part of the contract. Contract tests use mocks for the external system and run quickly.
* **End-to-end** - Verifies important user scenarios. These tests often map directly to a use case for an epic. They don't always use UI to drive part of the testing.

![Test Pyramid](https://github.com/mojaloop/docs/blob/master/Wiki/Test%20Pyramid.png)

By default, regression tests will be automated, especially at the unit, component, contract, and integrations levels. Because we are using microservices as a design pattern, we are using standard [microservice testing patterns](http://martinfowler.com/articles/microservice-testing)

Success measures are covered in [Code Quality Metrics](https://github.com/mojaloop/docs/wiki/Code-Quality-Metrics)

![Microservice Testing](https://github.com/mojaloop/docs/blob/master/Wiki/Microservice%20testing.png)

Tests remain manual only in a few situations:
* **In-sprint testing** - during the sprint, when a change is first created, you might test in manually while automation is being developed. This is a good time to use [exploratory testing tours](https://msdn.microsoft.com/en-us/library/jj620911(v=vs.120).aspx)
* **Difficult to automate scenarios** - some tests are very hard to automate and these can remain manual, however, when this occurs, think if there may be a better way to write the code to make the testing automatable. 
* **Very low priority scenarios** - Some tests a very low priority and thus don't need to be repeated often.
* **UI validation** - when a change to the UI is made, the best way to test it is to see it. With good MVVM design patterns, there should be no business logic in the UI to test, so the UI is just a thin presentation layer. Given that, contract testing below the UI covers most UI functional testing. The UI itself is rarely automated.

For now, manual tests are documented in text files. They include type and components covered so that a subset can be run. Manual test execution is tracked in a spreadsheet.

Most boundary and negative testing is done below the integration level and so run quickly. End-to-end tests don't need to duplicate that testing and so mostly cover positive cases.

Tests are as close to the code they test as possible. Thus, checking a simple function is done by unit tests on the function, interactions between components is done through component testing, checking compliance to an interface is done through automated contract tests on that interface (which don't duplicate the unit test and component tests).

In the end, we expect the number of unit and contract tests to be 10x or more times the number of component and integration tests which are also 10x or more times the number of end-to-end tests. These numbers aren't a goal, but meant to describe the expected shape of a very flat pyramid.

![Tracking Requirements to Results](https://github.com/mojaloop/docs/blob/master/Wiki/Tracking%20requirements%20to%20results.png)