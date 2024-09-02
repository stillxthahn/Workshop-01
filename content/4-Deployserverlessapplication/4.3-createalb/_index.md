---
title : "Create Application Load Balancer"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---


### Create Application Load Balancer
In this section, we will create an **ALB** to forward the incoming traffic to the private ECS cluster.
{{% notice info %}}
First, we have to set **Outbound rule** in the security group of the ALB to allow the traffic from the ALB to the ECS cluster.
{{% /notice %}}
![Container](/images/4-Deployserverlessapplication/4.3-createalb/017-createalb.png)

1. Search Load Balancers in the AWS Management Console and click on the **Create Load Balancer** button.
![Container](/images/4-Deployserverlessapplication/4.3-createalb/001-createalb.png)
![Container](/images/4-Deployserverlessapplication/4.3-createalb/002-createalb.png)

 - Choose **Application Load Balancer** 
![Container](/images/4-Deployserverlessapplication/4.3-createalb/003-createalb.png)

 - Name: **`docker-container-alb`**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/004-createalb.png)

 - In Network mapping, select the VPC and the subnets.
   - VPC: **my-workshop-01** 
   - Availability Zones: **us-east-1a** and **us-east-1b**
   - Subnet: **public-subnet-01** and **public-subnet-02**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/005-createalb.png)

 - Security group: **alb-sg-01**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/006-createalb.png)

 - In **Listeners and routing** section, we create a target group by choosing **Create target group**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/007-createalb.png)

 - This will lead you to the **Create target group** page. Configure the target group as shown below and click on the **Create** button.
   - Target type: **Instances**
   - Target group name: **`alb-tg-01`**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/008-createalb.png)
   - VPC: **my-workshop-01**
   - Protocol version: **HTTP1**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/009-createalb.png)
   - Healthy threshold: **2**
   - Unhealthy threshold: **5**
   - Interval: **10**
   - Choose **Next**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/010-createalb.png)
![Container](/images/4-Deployserverlessapplication/4.3-createalb/011-createalb.png)
   - Choose **Create target group**
![Container](/images/4-Deployserverlessapplication/4.3-createalb/012-createalb.png)
![Container](/images/4-Deployserverlessapplication/4.3-createalb/013-createalb.png)

2. Back to the **Create Load Balancer** page:
 - Click on Reload button and choose the target group that we have just created.
![Container](/images/4-Deployserverlessapplication/4.3-createalb/014-createalb.png)
 - Finally, click on the **Create load balancer** button.
![Container](/images/4-Deployserverlessapplication/4.3-createalb/015-createalb.png)
![Container](/images/4-Deployserverlessapplication/4.3-createalb/016-createalb.png)
