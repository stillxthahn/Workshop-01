---
title : "Create Service"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---


### Create service
In this section, we will create a service to run our containerized application on the ECS cluster.

{{% notice info %}}
In order to pull image from ECR, we have to add **Outbound rule** for our private subnet. 
{{% /notice %}}
![Container](/images/4-Deployserverlessapplication/4.5-createservice/009-createservice.png)

1. Go back to **Cluster** tab, choose our cluster **`docker-container-ecs`** 
![Container](/images/4-Deployserverlessapplication/4.5-createservice/001-createservice.png)
2. In service tab, choose **Create** button
![Container](/images/4-Deployserverlessapplication/4.5-createservice/002-createservice.png)
 - Compute options: **Launch type**
 - Launch type: **FARGATE**
![Container](/images/4-Deployserverlessapplication/4.5-createservice/003-createservice.png)
 - Application type: **Service**
 - Family: our newly created task definition **`docker-container-task`**
 - Revision: your latest revision
 - Service name: **`docker-service-01`**
![Container](/images/4-Deployserverlessapplication/4.5-createservice/004-createservice.png)
 - VPC: **`my-workshop-01`**
 - Subnets: our private subnets
 - Choose **Use an existing security group** and choose **`alb-sg-01`**
 - Turn off **public IP** to secure our service
![Container](/images/4-Deployserverlessapplication/4.5-createservice/005-createservice.png)
 - Load balancer type: **Application Load Balancer**
 - Container: choose **container-01 8000:8000**
 - Choose **Use an existing load balancer** and choose **`workshop-alb-01`**
![Container](/images/4-Deployserverlessapplication/4.5-createservice/006-createservice.png)
 - Choose **Use an existing listener** and choose **80:HTTP**
![Container](/images/4-Deployserverlessapplication/4.5-createservice/007-createservice.png)
 - Choose **Create new target group**
 - Target group name: **`single-service-01`**
 - Protocol: **HTTP**
 - Path pattern: **`/todos`** to route all traffic to our root path
 - Evaluation order: **1**
 - Health check path: **`/todos`**
 - Choose **Create** button
![Container](/images/4-Deployserverlessapplication/4.5-createservice/008-createservice.png)
3. After a few minutes, our service will be up and running.
 - Click on the service name to see the details
![Container](/images/4-Deployserverlessapplication/4.5-createservice/010-createservice.png)
![Container](/images/4-Deployserverlessapplication/4.5-createservice/011-createservice.png)
 - Click **View load balancer** to see the details of the load balancer
 - Copy **DNS name** and paste it to the browser with the path `/todos` to see the result
![Container](/images/4-Deployserverlessapplication/4.5-createservice/012-createservice.png)
![Container](/images/4-Deployserverlessapplication/4.5-createservice/013-createservice.png)







