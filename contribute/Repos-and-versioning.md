## Repos
Each repo in GitHub contains one or more functional components that we will release and version together. This group is independently functional an most often is a single microservice.

Each repo has all the info for the software the ships from it: documentation, tests, code, and issues. 

Initially, we expect to have many repos, but as some related components become stable, they may be combined into a single versioned group in a single repo.

## Naming
Repos are named following a simple convention of: **service-microservice** or **Area-component**. Example: **dfsp-ledger**. Services/Areas include: **dfsp**, **central**, **interop**, and **ilp**.

## Versioning
We use [semantic versioning](http://semver.org/) for each repo. 

Versions are identified with git tags. For Node.js projects you can run npm version {major,minor,patch} and it will update the package.json and create a git tag. Then you run git push && git push --tags to push the change to the repo.