# Reporting Bugs
This guides you through submitting a bug report for the Level One Project. Following these guidelines helps maintainers and the community understand your report, reproduce the behavior, and find related reports.

## Before Submitting a Bug Report
Perform a cursory search to see if the problem has already been reported. If it has and the issue is still open, add a comment to the existing issue instead of opening a new one

Note: If you find a Closed issue that seems like it is the same thing that you're experiencing, open a new issue and include a link to the original issue in the body of your new one.

Check the [FAQ](https://github.com/LevelOneProject/Docs/wiki/FAQ) in the Wiki for a list of common questions and problems.

## How Do I Submit a (Good) Bug Report?

Bugs are tracked as GitHub issues. 

Determine which repository the problem should be reported in. If the bug spans multiple repos use the Docs repo. 

After you've determined which repository your bug is related to, create an issue on that repository. When you are creating a bug report, use our [example bug](https://github.com/LevelOneProject/Docs/issues/81) as a template, the information it asks for helps us resolve issues faster.

The USSD interface will not have much information on what is going wrong. You'll want to dig into the logs to find the where the error(s) are happening and include those. Review the [Kibana guidelines](https://github.com/LevelOneProject/Docs/blob/master/ELK/kibana-user-guide.md) to see a log roll-up.

If the problem is related to performance or memory, include a CPU profile capture with your report.
Can you reliably reproduce the issue? If not, provide details about how often the problem happens and under which conditions it normally happens.

Include details about your configuration and environment: Are you running locally or in AWS? What environment and version are you using?