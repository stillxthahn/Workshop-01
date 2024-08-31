---
title : "Create ECS Cluster"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---


### Create ECS Cluster
In this section, we will create an ECS cluster to run the serverless application.
1. Go to the ECS console and click on the **Create Cluster** button.
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/001-createecscluster.png)
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/002-createecscluster.png)
 - Configure the cluster as shown below and click on the **Create** button.
   - Cluster name: **`docker-container-ecs`**
   - In infrastructure, select **AWS Fargate (serverless)**
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/003-createecscluster.png)
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/004-createecscluster.png)

2. Next, we create a **task definition**.
{{% notice note %}}
In AWS ECS, a **task definition** is a blueprint that specifies how Docker containers should be configured and run, detailing the Docker images, CPU and memory requirements, networking settings like port mappings, environment variables, and data volumes.
{{% /notice %}}
 - Click **Task Definition** and choose **Create new Task Definition**.
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/005-createecscluster.png)
 - Configure the task definition as shown below and click on the **Create** button.
   - Task definition family: **`docker-container-task`**
   - Launch type: **`FARGATE`**
   - Task execution role: **`ecsTaskExecutionRole`**. You can choose **Create new role** if you don't have one.
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/006-createecscluster.png)
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/007-createecscluster.png)
 - Next configure the container definition as shown below:
   - Name: **`container-01`**
   - Image URL: you can find the recent repository URL in the **ECR repository**.
   - Port mappings: **`8000`**
   - Choose **Create**
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/008-createecscluster.png)
![Container](/4-Deployserverlessapplication/images/4.4-createecscluster/009-createecscluster.png)

 

