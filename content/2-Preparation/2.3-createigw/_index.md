---
title : "Create Internet Gateway"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

### Create Internet Gateway
1. After create subnet, we continue create Internet Gateway to enable our instances in VPC to connect to the internet. First, choose **Internet Gateways** in current dashboard and choose **Create internet gateway**
![ConnectPrivate](/images/2.Preparation/2.3-createigw/001-createigw.png)
2. Set name for your IGW and click **Create internet gateway**
- **Name tag**: **`workshop-igw-01`**
![ConnectPrivate](/images/2.Preparation/2.3-createigw/002-createigw.png)
3. Next, we attach the IGW to our VPC. Choose **Actions** and **Attach to VPC**
![ConnectPrivate](/images/2.Preparation/2.3-createigw/003-createigw.png)
 - **Available VPCs**: **`my-workshop-01`**
 - Choose **Attach internet gatewat**
![ConnectPrivate](/images/2.Preparation/2.3-createigw/004-createigw.png)
4. Finish creating IGW
![ConnectPrivate](/images/2.Preparation/2.3-createigw/005-createigw.png)
