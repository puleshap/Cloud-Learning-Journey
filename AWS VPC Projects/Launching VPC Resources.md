

# Launching VPC Resources

## Architecture Diagram


![Architecture Diagram](https://github.com/user-attachments/assets/90adfa28-8dea-47c6-a0e5-05395e7737ee)


Current project diagram:

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-ec2_8ee57662)

---

# Project Overview

In this project, I launched resources inside an Amazon VPC and explored how public and private EC2 instances are configured and accessed.

The project focused on:

* EC2 instances
* Security groups
* SSH access
* Public and private networking
* VPC resource creation

The goal was to understand how compute resources are deployed within a VPC and how access can be controlled using AWS networking and security features.

---

# What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a logically isolated network within AWS where cloud resources can be securely launched and managed.

It provides control over:

* IP addressing
* Subnets
* Routing
* Security
* Internet connectivity

VPCs allow organizations to build secure and scalable cloud environments.

---

# How I Used Amazon VPC in This Project

In this project, I used Amazon VPC to:

* Launch EC2 instances
* Configure public and private subnets
* Apply security groups
* Enable secure access through SSH
* Explore automated VPC creation tools

This helped me understand how resources are deployed and secured inside AWS networks.

---

# Personal Reflection

One thing I did not expect during this project was how security groups and networking configurations work together to control access to EC2 instances.

I also learned how AWS can automatically create multiple networking resources through the VPC creation wizard.

This project took me approximately 45–60 minutes to complete.

---

# Setting Up Direct VM Access

## What Is Direct VM Access?

Direct VM access refers to connecting directly to a virtual machine such as an EC2 instance for administration and management tasks.

This is commonly done through SSH.

## SSH and EC2 Access

SSH (Secure Shell) is a secure protocol used to remotely connect to Linux-based servers.

It allows administrators to:

* Manage systems
* Configure applications
* Transfer files
* Perform maintenance tasks

## Key Pairs

To enable SSH access, I created an AWS key pair.

A key pair consists of:

* A public key stored by AWS
* A private key stored securely by the user

The private key is required to authenticate and access the EC2 instance securely.

My private key was downloaded in `.pem` format, which is commonly used for SSH authentication.

---

# Launching a Public Server

## What I Configured

I launched an EC2 instance inside a public subnet and configured networking settings to allow internet access.

I had to change my EC2 instance's networking settings by ensuring:

* The instance was launched in a public subnet
* A public IP address was assigned
* Security group rules allowed inbound SSH access

This allowed the instance to be reachable from outside the VPC.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-ec2_88727bef)

---

# Launching a Private Server

## What I Configured

I also launched an EC2 instance inside a private subnet.

Unlike the public server, this instance did not have direct internet access.

## Dedicated Security Group

My private server used its own dedicated security group to provide tighter access control.

The security group's source was configured to allow traffic only from trusted resources within the VPC.

This means the server can communicate internally while remaining protected from direct public access.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-ec2_4a9e8014)

---

# Speeding Up VPC Creation

## Using AWS VPC Automation

I explored an alternative way of creating VPC resources using AWS's built-in VPC creation wizard.

Instead of manually creating:

* VPCs
* Subnets
* Route tables
* Internet Gateways

AWS automatically generated the required networking resources based on my selections.

## What Is a VPC Resource Map?

A VPC Resource Map is a visual representation of networking components inside a VPC.

It helps users understand:

* Resource relationships
* Connectivity paths
* Network architecture

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-ec2_1cbb1b88)

---

# Additional VPC Creation Features

## Public Subnet Options

While using the VPC wizard, AWS provided options for automatically creating public subnets.

These predefined configurations help simplify network setup for common use cases.

## NAT Gateways

The setup wizard also offered the option to create a NAT Gateway.

A NAT Gateway allows resources inside private subnets to access the internet for outbound connections while preventing inbound internet access.

This is commonly used for:

* Software updates
* Package downloads
* Accessing external APIs

while maintaining security for private resources.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-ec2_8ee57662)

---

# Key Learnings

Through this project, I learned:

* How EC2 instances are launched within a VPC
* The difference between public and private servers
* How SSH access works
* The purpose of AWS key pairs
* How security groups control access to instances
* How AWS automates VPC resource creation
* The role of NAT Gateways in private networking

---

# Conclusion

In this project, I launched both public and private EC2 instances inside an Amazon VPC and explored how networking and security configurations affect accessibility.

This project strengthened my understanding of EC2 deployment, SSH access, security groups, and AWS networking architecture.
