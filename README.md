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
