---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
### Overview

### Serverless Architecture
**Serverless Architecture** is a way to build and run applications and services without having to manage infrastructure. Our application still runs on servers, but all the server management is done by AWS. We no longer have to provision, scale, and maintain servers to run your applications, databases, and storage systems.

### Container
**Container** is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. This can be from a developer's laptop to a test environment, from a staging environment into production, and perhaps from a physical machine in a data center to a virtual machine in a private or public cloud.

A container includes the application and all of its dependencies, but shares the kernel with other containers, which is different from Virtual Machines. It runs as an isolated process in user space on the host operating system, sharing just the kernel.

![ConnectPrivate](/images/1-Introduction/001-container.png) 

### Amazon Elastic Container Service (ECS)
**Amazon ECS** is a highly scalable, high-performance **container orchestration** service that supports **Docker containers** and allows you to easily run and scale contain	erized applications on AWS.

### Amazon Elastic Container Registry (ECR)
**Amazon ECR** is a fully managed **Docker container registry** that makes it easy for developers to store, manage, and deploy Docker container images.

### AWS Fargate
**AWS Fargate** is a **serverless compute engine** for **containers** that works with both Amazon Elastic Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS).
