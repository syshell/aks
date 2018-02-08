# Azure AKS (managed Kubernetes) - Test Guide #

This guide will demonstrate how to test Azure Container Service - Kubernetes as a Managed Service (AKS). 

AKS offer a nice feature to manage Kubernetes cluster without complexity. One important feature that differs from ACS (using Kubernetes) and AKS is about the absence of the Master node as a management endpoint for the Kubernetes cluster. The role for the Master Node is responsibility of Azure and simplifies the management. If you are new in kubernetes we recommend this solution to be evaluated.


Before you follow the procedures it's very important to understand all the options to use Containers on Azure. 

## Understand each choice ##

1) Virtual Machine with Docker

This scenario is recommended for companies evaluating Containers. You have options to use here:
- Virtual Machines using Linux: There is a lot of distros supporting Docker engine (including Ubuntu, CoreOS, CentOS, SUSE, Red Hat, etc) 
- Virtual Machines using Windows: Windows 10 and Windows Server 2016 support Windows Containers using Docker engine. Also Hyper-V Containers is supported. 
---
Important: you must understand that one container running Linux cannot be run on Windows Containers  just because both are using Docker engine. Remember that the container use a shared kernel from host. 

If you are deploying containers based on .Net Core 2.0 then you can move between these 2 different hosts with minor adjusts. 

Another option: Windows Server 2016 build 1709 (With Hyper-v Containers and Linux Subsystem) allow Hyper-V Containers running Linux (using Ubuntu). This is another great alternative to run Linux Containers on Windows Server 2016 without using Virtual Machines. 

---

2) Containers with Management/Orchestrator

This scenario use more than 1 virtual machine (with Docker) running some management system / orchestration. You have a lot of options like Docker Swarm, DCOS, Rancher, Kubernetes, Portainer, OpenShift, etc. It requires a lot of work because you need to manually setup the networking, storage, etc. 


3) Container Service

The scenario for Container Service solves a lot of work to setup storage, nodes, networking, etc. Still use virtual machines as nodes but you don't need to care about the difficult part of the setup because it's normally a solution from many Cloud Providers. 
Microsoft offers the Azure Container Service (ACS) using 3 options: Docker Swarm, DCOS and Kubernetes. 


4) Containers as a Service | Serverless Containers

The last option is very attractive for some scenarios. You don't need to setup the nodes because you cannot manage or access. This option allows you to run your containers without the requirement to setup neyworking, storage, nodes, etc. 
Microsoft Azure offers 2 solutions:
- Azure Container Instance (ACI): you can run your containers on Azure and manage using Azure CLI and Docker
- Azure Container service (AKS) Managed Kubernetes: you can run your containers on Azure and manage using Azure CLI and Kubectl (with the most part of the benefits from Kubernetes)
