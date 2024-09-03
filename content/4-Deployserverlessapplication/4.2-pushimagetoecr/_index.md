---
title : "Push image to ECR"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

#### Push image to ECR
In this step, we will push the Docker image to the **Amazon Elastic Container Registry (ECR)** service. 

**Amazon ECR** is a fully managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images. Amazon ECR is integrated with Amazon Elastic Container Service (ECS), simplifying your development to production workflow.

1. Create a new repository in **Amazon Elastic Container Registry (ECR)**.
 - Go to the **ECR** service.
![Container](/images/4-Deployserverlessapplication/4.2-Pushimagetoecr/001-pushimagetoecr.png)

 - Choose **Create**
![Container](/images/4-Deployserverlessapplication/4.2-Pushimagetoecr/002-pushimagetoecr.png)

 - Enter the repository name **`docker-container-01`** and choose **Create**
![Container](/images/4-Deployserverlessapplication/4.2-Pushimagetoecr/003-pushimagetoecr.png)
![Container](/images/4-Deployserverlessapplication/4.2-Pushimagetoecr/004-pushimagetoecr.png)

 - Finish creating the repository
![Container](/images/4-Deployserverlessapplication/4.2-Pushimagetoecr/005-pushimagetoecr.png)
1. Configure **AWS CLI** with your credentials
 - Install **AWS CLI** using the following command in **Command Prompt**
  
```
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
```
![Container](/images/4-Deployserverlessapplication/4.2-Pushimagetoecr/006-pushimagetoecr.png)

 - After the installation is complete, open the **Command Prompt** and run the following command to check the version of **AWS CLI**
```
aws --version
```
![Container](/images/4-Deployserverlessapplication/4.2-Pushimagetoecr/007-pushimagetoecr.png)

 - Following the instructions to install **AWS CLI**
 - Next, we will configure the **AWS CLI** with your credentials using following command
```
aws configure
```
 - Enter your **Access Key ID**, **Secret Access Key**, **Default region name**, and **Default output format**.
```
AWS Access Key ID [None]: EXAMPLE
AWS Secret Access Key [None]: EXAMPLE
Default region name [None]: us-east-1
Default output format [None]: json
```

3. Back to ECR dashboard, choose the repository you created and click on **View push commands**
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/008-pushimagetoecr.png)
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/009-pushimagetoecr.png)

 - You will see the commands to push the Docker image to the repository. Run the commands in the Terminal at the root directory of the project.
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/010-pushimagetoecr.png)
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/011-pushimagetoecr.png)

 - Run **docker build -t docker-container-01 .**
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/012-pushimagetoecr.png)

 - You can use **`docker images`** to review the images that have been built
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/013-pushimagetoecr.png)

 - After the build completes, tag your image so you can push the image to our repository
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/014-pushimagetoecr.png)

 - Push your image to the repository
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/015-pushimagetoecr.png)

 - Reload the **ECR** dashboard and you will see the image has been pushed to the repository
![Container](/images/4-Deployserverlessapplication/4.2-pushimagetoecr/016-pushimagetoecr.png)








