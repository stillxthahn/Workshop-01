---
title : "Create NAT Gateway"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

### Create NAT Gateway
1. Next, we create NAT Gateway to help our private instances connect to the Internet. First, choose **NAT Gateways** in current dashboard and choose **Create NAT gateway**
![ConnectPrivate](/images/2.Preparation/2.4-createnatgw/001-createnatgw.png)
2. Configure NAT Gateway
 - **Name**: **`workshop-natgw-01`**
 - **Subnet**: **`public-subnet-01`**
 - **Connectivity type**: **Public**
 - We also need to create a new Elastic IP Address for our NAT Gateway. Choose **Allocate Elastic IP**
![ConnectPrivate](/images/2.Preparation/2.4-createnatgw/002-createnatgw.png)
 - Finish the configuration by choosing **Create NAT Gateway**
![ConnectPrivate](/images/2.Preparation/2.4-createnatgw/003-createnatgw.png)
3. Next, we attach the IGW to our VPC. Choose **Actions** and **Attach to VPC**
![ConnectPrivate](/images/2.Preparation/2.3-createigw/003-createigw.png)
 - **Available VPCs**: **`my-workshop-01`**
 - Choose **Attach internet gatewat**
![ConnectPrivate](/images/2.Preparation/2.3-createigw/004-createigw.png)
4. Finish creating IGW
![ConnectPrivate](/images/2.Preparation/2.3-createigw/005-createigw.png)
