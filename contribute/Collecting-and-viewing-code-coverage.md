# View code coverage
Connect to sonarqube at http://35.163.188.144:9000/, use the user name/password of public/public.

Also look at any bugs or code smells in your code. 

# Collecting code coverage
(see deploytest repo for an example)
During your unit tests, generate code coverage in a LCOV format in the file lcov.info and copy it to the circleCI ${CIRCLE_TEST_REPORTS} directory.

An example of the package.json for this for NodeJS looks like:
>     "scripts": {
>         "test": "tape ./test/*.js | tap-xunit", # runs tests
>         "createcoverage": "nyc npm test", # creates code coverage for tests
>         "reportcoverage": "nyc report --reporter=lcov --reporter=text-lcov npm test", # generates a coverage report
>         "lint": "standard" # runs lint
>       },
>       "devDependencies": {
>         "nyc": "^7.1.0", # tool to collect coverage
>         "standard": "^8.1.0", # lint tool
>         "tap-xunit": "^1.4.0", # converts tape output to xunit format
>         "tape": "^4.6.0" # unit test libary
>       },

In the CircleCI
>     override:
>        - set -o pipefail && npm -s test > ${CIRCLE_TEST_REPORTS}/testresults.xml
>        - npm run lint
>        - npm run createcoverage
>        - set -o pipefail && npm -s run reportcoverage
>        - cp -R ./coverage/* ${CIRCLE_TEST_REPORTS}    # puts both coverage file and the reports into the report folder
>        - aws s3 cp ./coverage/lcov.info s3://elasticbeanstalk-us-west-2-886403637725/sonar/deploytest/
>                        # the aws command sends the coverage info to the beanstalk bucket where sonarcube picks it up

The coverage file, which should always be called lcov.info and be in the lcov format, should be copied to the s3://elasticbeanstalk-us-west-2-886403637725/sonar/<repo name> directory. From there it will automatically be picked up by the SonarQube job.

To make the aws command work you'll need to set the AWS permission in your CircleCI repo (example: https://circleci.com/gh/LevelOneProject/deploytest/edit#aws). A good set of credentials to use are the CircleTest account, which only has access to the AWS bucket. Contact BHCrosslake for the access keys.

# Testing the AWS command locally
to configure the aws client, from a bash shell run 
>      aws configure 
and enter the access key, secret key and the region: us-west-1





