---
title : "Create Route tables"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

### Create Route tables
1. Next, we create Route tables to direct our private instances to the internet. First, choose **Route tables** in current dashboard and choose **Create Route table**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/001-createroutetables.png)
2. Conofigure Route tables
 - **Name**: **`public-route-table`**
 - **VPC**: **`my-workshop-01`**
 - Choose **Create route table**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/002-createroutetables.png)
3. Next, we add subnets to our route table. Choose **Subnet associations** and **Edit subnet associations**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/003-createroutetables.png)
4. Choose two public subnets and **Save associations**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/004-createroutetables.png)
5. Next, we add routes to our route table. Choose **Routes** and **Edit routes**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/005-createroutetables.png)
6. Configurate route:
- **Destination**: **`0.0.0.0/0`** 
- **Target**: **Internet Gateway**
- **Target**: **`workshop-igw-01`**
- Choose **Save Changes**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/006-createroutetables.png)
7. Continue to add private route table for **private subnets** with the same process
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/007-createroutetables.png)
 - In Subnet associations, choose our two **private subnets**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/008-createroutetables.png)
 - In Route, we route our private subnets to the internet through **NAT Gateway**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/009-createroutetables.png)
8. We also create our route table for **database subnets**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/010-createroutetables.png)
 - Choose our two private database subnets
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/011-createroutetables.png)
 - Routing these subnets to the internet through **NAT Gateway**
![ConnectPrivate](/images/2.Preparation/2.5-createroutetables/012-createroutetables.png)



  