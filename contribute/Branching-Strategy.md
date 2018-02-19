The master branch for each repo must represent a good state where all tests have been run and pass. You should update master at the end of user stories when the code is ready for checkin. The master branch is used to build components for test and integration with other components. 

# Setup the repo to squash commits instead of merging
We like code checked into master to have a simple clean story, so we want all repos to use the squash option:
Under your repository settings uncheck allow merge:

![Merge Button Settings](https://github.com/mojaloop/docs/blob/master/Wiki/mergebtn.png)

This will force changes to master to be single named commit (see [Squash your commits](https://github.com/blog/2141-squash-your-commits)).

# Versioning
Based on [semantic versioning](http://semver.org/) (Breaking.Feature.Fix), as long a component is not shipped, the major version will be less than 1 (example: 0.15.1). Most user stories will increment the middle number. Minor changes and bug fixes increment the last number. 
Example: 

`git tag # this will tell you the current tags including the version

`git tag v0.3.0` # this sets a version tag

`git push --tags`

# Integrated tests
Make sure integrated build and testing is turned on for the repo at: https://circleci.com/add-projects.
This will build and run tests after any push on any branch. The test override section of the circle.yml has the commands to run for the tests.

# Quick and dirty
If you are making a small fix on a local branch dev that branches right off of master, you might follow a pattern like this (there are better as we'll see below):

`(master) git checkout -b dev  # create the dev branch and move to it`

`[code change here]`

`git commit -m  "a small change to the dev branch" `

`git rebase dev master # get the latest changes from master and move the master head up to dev`

`git tag v0.3.1 # update the version`

`git push && git push --tags # update the server and run the tests`

This will pick of the latest changes anyone else made on master and add yours onto them. We use rebase instead of merge to keep a clear story of the changes. 
If you have a bunch of extraneous commits, consider using git rebase -i to do an interactive rebase and remove a bunch of the extra noise.You can choose to keep your dev branch around if you are going to reuse it or else delete it.

The procedure above doesn't really work for larger changes since you can't share the development branch with others, you can't do code reviews on it in Github, and the integration tests won't run on your dev branch in advance of the push - you have to do the tests manually. This makes it inferior for larger changes, and we won't use it at all once we go past v1 or go to open source. With that in mind, let's look at a better solution.

# Cloned or Forked repos
Instead of just a local branch like above, you create the branch on the server.

![Create Server Branch](https://github.com/mojaloop/docs/blob/master/Wiki/CreateBranch.png)

Then, locally:

`git checkout dev # creates the local copy of the remote dev branch and switches to it`

`# make some code changes`

`(dev) git commit -m  "user story #111 "`

`git tag v0.4.0 # update the version`

`git pull --rebase`

`git push && git push --tags # kicks off tests on dev branch, yea!`

Now create a pull request from dev to master

![Create Pull Request](https://github.com/mojaloop/docs/blob/master/Wiki/CompareNPull.png)

After you resolve the comments, you can push the code.

![Squash](https://github.com/mojaloop/docs/blob/master/Wiki/ConfirmNSquash.png)

# Open Source
An open source contributor would follow almost the same steps. They'd fork instead of cloning. They'd do the same steps (without tags). The final step would be done by one of the repo owners. 
