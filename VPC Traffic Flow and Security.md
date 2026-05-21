# VPC Traffic Flow and Security

## Architecture Diagram



![Image](https://github.com/user-attachments/assets/1505eaf3-4985-4706-af4e-8e3ee823fada)


Example placement:

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-security_92b0b0b4)

---

# Project Overview

In this project, I explored how traffic flows inside an Amazon VPC and how AWS networking security components help control and protect cloud resources.

The project focused on:
- Route tables
- Internet connectivity
- Security groups
- Network ACLs (NACLs)
- Traffic filtering and routing

This project helped me better understand how AWS networking components work together to securely manage inbound and outbound traffic.

---

# What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a logically isolated networking environment in AWS where cloud resources can be securely launched and managed.

It provides control over:
- Subnets
- Routing
- Internet access
- Security configurations
- IP addressing

---

# How I Used Amazon VPC in This Project

In this project, I used Amazon VPC to:
- Create networking resources inside subnets
- Configure route tables
- Attach an Internet Gateway
- Apply security groups
- Explore Network ACL configurations

This allowed me to understand how traffic is routed and secured inside AWS cloud environments.

---

# Personal Reflection

One thing I did not expect during this project was using the AWS CLI to create and manage networking resources.

This project took me approximately 60 minutes to complete.

---

# Route Tables

## What Are Route Tables?

Route tables are used to control how network traffic is directed inside a VPC.

Each route defines:
- A destination IP range
- A target where the traffic should be sent

## Why Route Tables Are Important

Route tables are required to make a subnet public because they direct internet-bound traffic to the Internet Gateway.

Without proper routing configuration, resources inside the subnet cannot communicate with the internet.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-security_0a07b191)

---

# Route Destinations and Targets

## Route Destination

The destination specifies the range of IP addresses the route applies to.

Example:
- `0.0.0.0/0` represents all IPv4 addresses and is commonly used for internet traffic.

## Route Target

The target defines where the traffic should be sent.

In this project:
- The destination was `0.0.0.0/0`
- The target was the Internet Gateway

This configuration allowed internet access for resources inside the public subnet.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-security_0a07b191)

---

# Security Groups

## What Are Security Groups?

Security groups act as virtual firewalls for AWS resources such as EC2 instances.

They control inbound and outbound traffic at the instance level.

## Inbound vs Outbound Rules

### Inbound Rules
Inbound rules control incoming traffic to resources.

In this project, the security group was configured to allow:
- HTTP traffic
- From any source

### Outbound Rules
Outbound rules control traffic leaving AWS resources.

By default, outbound traffic is generally allowed to all destinations.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-security_92b0b0b4)

---

# Network ACLs (NACLs)

## What Are Network ACLs?

Network ACLs (Access Control Lists) are subnet-level firewalls used to filter inbound and outbound traffic for entire subnets.

They provide an additional layer of security within the VPC.

---

# Security Groups vs Network ACLs

| Security Groups | Network ACLs |
|---|---|
| Operate at instance level | Operate at subnet level |
| Stateful | Stateless |
| Allow rules only | Allow and deny rules |
| Applied to EC2 instances | Applied to subnets |

---

# Default vs Custom Network ACLs

## Default Network ACLs

By default, AWS network ACLs:
- Allow all inbound traffic
- Allow all outbound traffic

## Custom Network ACLs

Custom NACLs can be configured with:
- Specific allow rules
- Specific deny rules

This provides more detailed traffic filtering control.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-security_4faeb056)

---

# Tracking VPC Resources

## What I Explored

In this section, I explored how AWS tracks networking resources such as:
- VPCs
- Subnets
- Internet Gateways
- Security Groups
- Route Tables

AWS provides centralized visibility into networking resources across regions through the VPC dashboard.

This helps users monitor and manage cloud networking infrastructure more effectively.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-security_b03ea6162)

---

# Key Learnings

Through this project, I learned:
- How route tables control traffic flow
- The purpose of Internet Gateways
- How security groups filter instance traffic
- The difference between security groups and Network ACLs
- How subnet-level and instance-level security work together
- Basic networking security concepts inside AWS

---

# Conclusion

In this project, I explored AWS networking security and traffic management using Amazon VPC components.

By configuring route tables, security groups, and Network ACLs, I gained a better understanding of how AWS securely controls traffic flow between cloud resources and the internet.
