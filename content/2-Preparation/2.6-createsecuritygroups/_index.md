---
title : "Create Security groups"
date : "`r Sys.Date()`"
weight : 7 
chapter : false
pre : " <b> 2.7 </b> "
---

### Create security groups
In this section, we will create security groups for our **Application Load Balancer**, **Private Subnets (Containers)**, and **Private Database Subnets**.
1. Security groups for **Application Load Balancer**
- Choose **Security groups** on the left side of the screen and choose **Create security group**
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/001-createsecuritygroups.png)
- Configure our **ALB Security group** as follows:
  - **Security group name**: **`alb-sg-01`**
  - **Description**: **`Internet facing ALB`**
  - **VPC**: **`my-workshop-01`**
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/002-createsecuritygroups.png)
- Add **Inbound rules**:
  - Type: **HTTP**; Source: **Anywhere-IPv4**
  - Type: **SSH**; Source: **My IP**
  - Type: **All ICMP - IPv4**; Source: **Anywhere-IPv4**
  - Type: **Custom TCP**; Port range: **8000**; Source: **Anywhere**
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/003-createsecuritygroups.png)
  - Choose **Create security group**
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/004-createsecuritygroups.png)
1. Security groups for **Private Subnets (Containers)** 
- Do the same process as above, but configure **Security group** as follows:
  - **Security group name**: **`container-sg-01`**
  - **Description**: **`Private containers`**
  - **VPC**: **`my-workshop-01`**
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/005-createsecuritygroups.png)
- Add **Inbound rules**:
  - Type: **Custom TCP**; Port range: **8000**; Source: **Anywhere**
  - Type: **Custom TCP**; Port range: **8080**; Source: **Custom - alb-sg-01**
  - Type: **Custom TCP**; Port range: **8080**; Source: **Anywhere-IPv4**
  - Type: **Custom TCP**; Port range: **8080**; Source: **My IP**
  - Choose **Create security group**
![](/images/2-Preparation/2.6-createsecuritygroups/006-createsecuritygroups.png)
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/004-createsecuritygroups.png)
1. Security groups for **Private Databases** 
- Do the same process as above, but configure **Security group** as follows:
  - **Security group name**: **`container-sg-01`**
  - **Description**: **`Private containers`**
  - **VPC**: **`my-workshop-01`**
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/007-createsecuritygroups.png)
- Add **Inbound rules**:
  - Type: **MYSQL/Aurora**; Source: **Custom - alb-sg-01**
  - Type: **All traffic**; Source: **Anywhere-IPv4**
  - Type: **Custom TCP**; Port range: **8080**; Source: **Anywhere-IPv4**
  - Choose **Create security group**
{{%notice info%}}
**All traffic** is for tesing purpose only. In production, you should limit the traffic to the necessary ports only.
{{%/notice%}}
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/008-createsecuritygroups.png)
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/004-createsecuritygroups.png)
1. Finishing creating security groups:
![ConnectPrivate](/images/2-Preparation/2.6-createsecuritygroups/009-createsecuritygroups.png)
