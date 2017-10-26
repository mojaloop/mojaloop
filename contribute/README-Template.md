_Use this template for the README file when you create a repository for a new (micro)service or application under the Mojaloop organization._

_Also don't forget to provide higher-level documentation in the [Docs repo](https://github.com/Mojaloop/Docs), such as an architecture overview, user flow, and resilience modeling. See [Architecture Documentation Guidelines](https://github.com/Mojaloop/mojaloop/contribute/blob/master/Architecture-Documentation-Guidelines.md) for details._

-----

# (Repository name)

(Intro blurb - no more than two sentences explaining what this repo is for)

Contents:

- [Deployment](#deployment)
- [Configuration](#configuration)
- [API](#api)
- [Logging](#logging)
- [Tests](#tests)

## Deployment

(How do you deploy/build/run this code? If this is included as part of a larger package, link the parent package.)

(Example for NPM-published services--

Installation:

1. Install [Node.js and npm](https://nodejs.org/en/)

2. Configure your npm instance to use the Mojaloop repository.

    <TBD>

3. Install the '(package name)' package.

        npm install (package name)

Running the server locally:

    npm start

--end example)

## Configuration

(Location of Ansible playbooks that configure this code.)

(Explanation of important config parameters)


## API

(If the API is short, summarize it here; otherwise, link a separate page with the API docs or explain how to build the API docs from the repo.)

## Logging

(Where are the logs?)

(Explain important things about what gets logged or how to interpret the logs. Use subheaders if necessary.)

## Tests

(Explain what's covered, and what's not covered, by the tests. At this level, it's usually just unit tests.)

(Explain how to run the tests)