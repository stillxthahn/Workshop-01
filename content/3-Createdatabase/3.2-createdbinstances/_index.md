---
title : "Create database instances"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---

### Create database instances
In this section, we will create database instances.
1. Choose **Create database**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/001-createdbinstances.png)
2. Configure our **Database** as follows:
- Choose a database creation method: **Standard Create**
- Engine options: **MySQL**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/002-createdbinstances.png)
- Templates: **Free tier**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/003-createdbinstances.png)
{{%notice info%}}
We can choose **Dev/Test** or **Production** templates to enable **Multi-AZ DB instance**, which accquire high availability and data redundancy. In this workshop, we will use the Free tier template to save cost.
{{%/notice%}}
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/004-createdbinstances.png)
- DB instance identifier: **`workshop-db-01`**
- Master username: **`admin`**
- Credentials management: **Self managed**
- Master password: **`12345678`**
- Confirm master password: **`12345678`**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/005-createdbinstances.png)
- Compute resource: **Don’t connect to an EC2 compute resource**
- Network type: **IPv4**
- Virtual private cloud (VPC): **my-workshop-01**
- DB subnet group: **db-subnet-group-01**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/006-createdbinstances.png)
- Public access: **No**
- VPC security group: **Choose existing**
- Existing VPC security groups: **database-sg-01**
- Availability zone: **us-east-1a**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/007-createdbinstances.png)
- In Additional configuration, we set initial database name as **`workshopdb`**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/008-createdbinstances.png)
- Choose **Create database** and finish the process
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/009-createdbinstances.png)
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/010-createdbinstances.png)
3. After creating the database, we connect to the database instance by using **MySQL Workbench.**
{{%notice info%}}
In order to test connection, we need to: Turn on **DNS hostnames** for our VPC; Enable **Publicly Accessible** in our RDS Instance; Add a new route with destination **0.0.0.0/0 and target internet gateway** in database route table. After testing, we should disable it to ensure security.
{{%/notice%}} 
 - Move to **VPC** section, choose our **my-workshop-01** VPC and select **Edit VPC Settings** in **Actions** tab.
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/016-createdbinstances.png)
 - In **DNS settings** section, choose **Enable DNS hostnames** and **Save**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/017-createdbinstances.png)
 - Move to **RDS** section, choose current RDS instance
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/011-createdbinstances.png)
 - Choose **Modify**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/012-createdbinstances.png)
 - In Additional Configuration, choose **Publicly Accessible** 
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/013-createdbinstances.png)
 - Choose **Continue**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/014-createdbinstances.png)
 - Choose **Apply immediately** and **Modify DB instance**
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/015-createdbinstances.png)
 - Now, we can connect to our RDS instance by using **MySQL Workbench**.
 - Open **MySQL Workbench** and open a connection to our RDS instance.
   - Connection Name: **`workshop-db-01`**
   - Hostname: our **endpoint** of RDS instance
   - Port: **`3306`**
   - Username: **`admin`**
   - Password: **`12345678`**
   - Finally, choose **Test Connection** 
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/018-createdbinstances.png)
 - Our connection should be like this:
![ConnectPrivate](/3-Createdatabase/images/3.2-createdbinstances/019-createdbinstances.png)





