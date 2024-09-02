---
title : "Prerequisite"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

#### Prerequisite

1. First, we have to clone the initial application
 - Right click and select **Git Bash Here**
![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/001-prerequisite.png)

 - Run the following command to clone the application
```
git clone https://github.com/stillxthahn/FCJ-01-backend.git
```
![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/002-prerequisite.png)
![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/003-prerequisite.png)

 - Modify Dockerfile and fill in the following information. Replace **YOUR_RDS_ENDPOINT** and **YOUR_RDS_PORT** with your **RDS endpoint** and **port**
```
ENV RDS_HOSTNAME=YOUR_RDS_ENDPOINT
ENV RDS_PORT=YOUR_RDS_PORT
ENV RDS_DB_NAME=todolist
ENV RDS_USERNAME=admin
ENV RDS_PASSWORD=12345678
``` 
![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/008-prerequisite.png)

2. Download user security credentials

{{%notice warning%}}

It is best practice to create a new user with the necessary permissions for the application and download its credentials. But for this workshop only, we will use the root user.

{{%/notice%}}

 - Access **Security Credentials**

![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/004-prerequisite.png)

 - Choose **Creat Access Key**
![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/005-prerequisite.png)
![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/006-prerequisite.png)

 - Download the **.csv** file and **Done**
![ConnectPrivate](/images/4-Deployserverlessapplication/4.1-prerequisite/007-prerequisite.png)


