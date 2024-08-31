---
title : "Create database subnet group"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

### Create database subnet group
In this section, we will create a subnet group for database.
1. Search **RDS** on search bar
![ConnectPrivate](/images/3.Createdatabase/3.1-createdatabasesg/001-createdatabasesg.png)
2. First, we have to create **Subnet groups**. Choose **Subnet groups** on the left side of the screen and choose **Create DB subnet group**
![ConnectPrivate](/images/3.Createdatabase/3.1-createdatabasesg/002-createdatabasesg.png)
3. Configure our **Subnet group** as follows:
- **Name**: **`db-subnet-group-01`**
- **Description**: **`db-subnet-group-01`**
- **VPC**: **`my-workshop-01`**
![ConnectPrivate](/images/3.Createdatabase/3.1-createdatabasesg/003-createdatabasesg.png)
4. In Add subnets section:
- Choose **Availability Zones**: **`us-east-1a`**, **`us-east-1b`**
- **Subnets**: choose our two **private database subnets** that we have configured in VPC section
- After that, choose **Create**
![ConnectPrivate](/images/3.Createdatabase/3.1-createdatabasesg/004-createdatabasesg.png)
5. We will see that we have created **Subnet group** successfully. We choose **Database** on the left side of the screen to create database
![ConnectPrivate](/images/3.Createdatabase/3.1-createdatabasesg/005-createdatabasesg.png)


