# Blue/Green Deployments & Testing Overview

## What is a Blue/Green Deployment? 
* A blue/green deployment is a software release management strategy that aims to avoid downtime and mitigate risk. 
* Two identical environments, "blue" and "green" work in parallel during deployment, testing, and release.

## Standard Procedure 
1. Initial State: The current production environment is running, and users are accessing the application.
2. Deployment: The new identical and parallel environment is set up (the green environment) with the updated version of the application.
3. Testing: ITQE tests the new version in the green environment.
4. Switching Traffic: Once testing is successful, the user traffic is switched from the blue environment to the green environment
5. Monitoring: If any issues occur in the green environment, rollback to the blue environment to minimize downtime
6. Post-Deployment: The green environment is the production environment, and the blue environment is idle for the next deployment cycle

## Reference: Blue/Green Deployment Diagram
![](https://github.com/Mporter11/My-Writing/blob/main/Explainers/Blue_Green_Diagram.png) 

## Stipulations
* ITQE will perform the testing. Team members will be listed on the applicable JIRA ticket.
* The test will be tracked on the sub-task ticket titled "Smoke Test on Staging Environment" of the applicable JIRA story ticket.
![](https://github.com/Mporter11/My-Writing/blob/main/Explainers/Blue_Green_JIRA.PNG) 
* The test typically takes one hour to complete, but timing is dependent on the complexity of the work. See the applicable JIRA ticket for details.
* No coding changes will be made to the affected website during or post the blue/green deployment.

## Reference: Process Flow
![](https://github.com/Mporter11/My-Writing/blob/main/Explainers/Blue_Green__Flow.png) 
