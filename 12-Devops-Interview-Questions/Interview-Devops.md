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

## What is the difference between agile and devops?
Agile and DevOps are both methodologies that aim to deliver software faster and more reliably, but they have different scopes and goals. Agile focuses on the flow of software from ideation to code completion, while DevOps extends the focus to delivery and maintenance.

DevOps is a culture that allows the development and the operations team to work together. This results in continuous development, testing, integration, deployment, and monitoring of the software throughout the lifecycle. Devops is a solution for the gap between development and operations teams.

Agile is a software development methodology that focuses on iterative, incremental, small, and rapid releases of software, along with customer feedback. It addresses gaps and conflicts between the customer and developers. Agile is a solution for the gap between customers and developers.

## What are the phases of Devops?

In general, Devops has 8 phases which occur continuously.
1. Continuous development

* Plan: It always starts with a plan. There should be a plan for the type of application that needs to be developed. The team should define project goals in line with customer expectations, identify the resources needed and sets a timeline.
* Code: The application is coded as per the end-user requirements. This phase is also called development and the development team writes the actual software code.

2. Continuous Testing
* Build: Build the application by integrating various codes formed in the previous steps.
* Test: This is the most crucial step of the application development. Test the application and rebuild, if necessary.

3. Continuous Integration
* Integrate: Multiple codes from different programmers are integrated into one ensuring a better software.

4. Continuous Deployment
* Deploy: Code is deployed into a cloud environment for further usage. It is ensured that any new changes do not affect the functioning of a high traffic website.
* Operate: Operations are performed on the code if required.

5. Continuous Monitoring
* Monitor: Application performance or in other words the performance of the software is monitored. Based on the performance indicators, changes are made to meet the end-user requirements.
