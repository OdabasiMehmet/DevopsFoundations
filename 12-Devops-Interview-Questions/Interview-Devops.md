## What is Continuous Integration?

Continuous integration is a software delivery method where members of a software delivery team constantly work on the source code and integrate their work on a daily basis. Whether creating the code fraom scratch or modifying the code to make it better or free of bugs, developers work on their code every daya and commit the code at least once a day. 

## How does CI work?

Developers use source control systems and clone the original source code into their environments. This source code is originally placed under a main branch in the source control system and each developer creates a branch of their own to work on their codes. Then they commit the codes from their branches and merge them into the main branch. If conflicts occur, they are identified by source control systems and resolved by the software development team.

## What are the advantages of continuous integration?

* Lead Time: Continuous integration requires constant work and commits on the source code. This results in faster software delivery times as the code is evolved every day.
* Change failure rate: For each build, the updated code is tested so at the end of the day, there will be less bugs to deal with compared to methods that do not use CI. Without using CI, the source code will need to be tested after fully finished and is very likely to face more bugs. If the bugs are not found in the early stage with CI, it would be very difficult to fix them.
* Deployment frequency: With CI, the code is integrated daily so with fewer changes, the code is deployed more frequently.
* Time to restore service: Automated pipelines enable fixes to be deployed to production faster, reducing mean time to resolution (MTTR).

## What is the difference between Continuos Deployment (CD) and Continuous Delivery (CD)
Both of them are the second phase of a CI/CD process. The main difference between them is that continuous delivery prepares the deployment of a new release into a staging or testing environment whereas continuous deployment automatically deploys each new release into the production environment. In other words, continuous delivery needs a manual input to be deployed into production where as continuous deployment is automated already.