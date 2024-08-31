+++
title = "Clean up resources"
date = 2022
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

We will take the following steps to delete the resources we created in this exercise.

#### Delete RDS instance

1. Go to RDS service
   + Choose your RDS instance
   + Click **Actions**.
   + Click **Delete**.
![Clean](/images/001-cleanup.png)


#### Delete ECS Cluster
1. Go to ECS service management console
   + Choose your **ECS cluster**
   + Click **Delete**
   + Enter deletion confirmation text 
   + Click **Delete**
![Clean](/images/002-cleanup.png)
![Clean](/images/003-cleanup.png)
![Clean](/images/004-cleanup.png)

#### Task Definition

1. Access Task Definitions in the ECS service management console.
   + Click on the task definition created for this lab.
   + Choose all revisions of the task definition.
   + Click **Actions**
   + Click **Deregister**.
![Clean](/images/005-cleanup.png)
![Clean](/images/006-cleanup.png)
![Clean](/images/007-cleanup.png)

#### Delete Load Balancer

1. Go to Load Balancer service management console
   + Mark the **Load Balancer** created for this lab.
   + Click **Actions**.
   + Click **Delete load balancer**.
   + Type **confirm**
   + Click **Delete**
![Clean](/images/008-cleanup.png)
![Clean](/images/009-cleanup.png)

#### Delete NAT Gateway
1. Go to NAT Gateway service management console
   + Choose the **NAT Gateway** created for this lab.
   + Click **Actions**.
   + Click **Delete NAT Gateway**.
   + Click **Delete**.


#### Delete Subnets and ENI
1. Go to Network Interfaces service management console.
   + Select the **Network Interface** created for this lab.
   + Click **Action**
   + Click **Detach**.
   + Click **Delete**.

2. Go to Subnets service management console.
   + Select the **Subnet** created for this lab.
   + Click **Action**
   + Click **Delete**.
