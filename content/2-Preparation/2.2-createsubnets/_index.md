---
title : "Create subnets"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Create subnets
1. After creating VPC, we continue create subnets. First, choose **Subnets** in current dashboard 
![Subnets](/2-Preparation/images/2.2-createsubnets/001-createsubnets.png) 
2. Choose **Create subnet**
![Subnets](/2-Preparation/images/2.2-createsubnets/002-createsubnets.png) 
3. Choose recent VPC that you have just created
![Subnets](/2-Preparation/images/2.2-createsubnets/003-createsubnets.png) 
4. After choosing VPC, we will configure the subnet as follows:
- **Subnet name**: **`public-subnet-01`**
- **Availability Zone**: choose **US East (N. Virginia) / us-east-1a**
- **IPv4 subnet CIDR block**: **`10.0.1.0/24`**
![Subnets](/2-Preparation/images/2.2-createsubnets/004-createsubnets.png) 
5. Choose **Add new subnet** and perform same configuration for other subnets:
![Subnets](/2-Preparation/images/2.2-createsubnets/005-createsubnets.png) 
- **`public-subnet-02`** in **US East (N. Virginia) / us-east-1b** withCIDR **`10.0.2.0/24`**
![Subnets](/2-Preparation/images/2.2-createsubnets/006-createsubnets.png) 
- **`private-subnet-01`** in **US East (N. Virginia) / us-east-1a** with CIDR **`10.0.3.0/24`**
![Subnets](/2-Preparation/images/2.2-createsubnets/007-createsubnets.png) 
- **`private-subnet-02`** in **US East (N. Virginia) / us-east-1b** with CIDR **`10.0.4.0/24`**
![Subnets](/2-Preparation/images/2.2-createsubnets/008-createsubnets.png) 
- **`private-db-subnet-01`** in **US East (N. Virginia) / us-east-1a** with CIDR **`10.0.5.0/24`**
![Subnets](/2-Preparation/images/2.2-createsubnets/009-createsubnets.png) 
- **`private-db-subnet-02`** in **US East (N. Virginia) / us-east-1b** with CIDR **`10.0.6.0/24`**
![Subnets](/2-Preparation/images/2.2-createsubnets/010-createsubnets.png) 
6. Choose **Create subnet** to finish creating subnets
![Subnets](/2-Preparation/images/2.2-createsubnets/011-createsubnets.png) 
7. After creating subnets, you can see the result as follows:
![Subnets](/2-Preparation/images/2.2-createsubnets/012-createsubnets.png) 
8. Next, we enable **public IPv4 address** for two public subnets.
- We choose each public subnet and choose **Actions** > **Edit subnet settings**
![Subnets](/2-Preparation/images/2.2-createsubnets/013-createsubnets.png) 
- Choose **Enable auto-assign public IPv4 address** and choose **Save**
![Subnets](/2-Preparation/images/2.2-createsubnets/014-createsubnets.png) 
![Subnets](/2-Preparation/images/2.2-createsubnets/015-createsubnets.png) 
- We do the same for **`public-subnet-01`**. After that, we can see the result as follows:
![Subnets](/2-Preparation/images/2.2-createsubnets/016-createsubnets.png) 
![Subnets](/2-Preparation/images/2.2-createsubnets/017-createsubnets.png) 
  
