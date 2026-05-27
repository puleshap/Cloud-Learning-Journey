# Creating a Private Subnet

## Architecture Diagram



![Architecture Diagram](https://github.com/user-attachments/assets/80568974-0bb7-4916-b784-d7c2baa607ed)


---

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-private_afe1fdbd)

---

# Project Overview

In this project, I explored how to create and configure a private subnet inside an Amazon VPC.

The project focused on:
- Private subnets
- Route tables
- Network ACLs (NACLs)
- Internal-only traffic flow
- AWS network security concepts

The main goal was to understand how AWS resources can remain isolated from the public internet while still communicating securely within a VPC.

---

# What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a networking service in AWS that allows users to create logically isolated cloud networks.

It helps organize and secure AWS resources by providing control over:
- Subnets
- IP addressing
- Routing
- Internet access
- Security configurations

---

# How I Used Amazon VPC in This Project

In this project, I used Amazon VPC to:
- Create a private subnet
- Configure a dedicated private route table
- Create a custom Network ACL (NACL)
- Control traffic flow within the VPC

This helped me understand how private AWS networking environments are structured and secured.

---

# Personal Reflection

One thing I did not expect during this project was configuring multiple Network ACLs and understanding how different subnets can use different route tables and traffic rules.

This project took me approximately 20 minutes to complete.

---

# Private vs Public Subnets

## Public Subnets

Public subnets are connected to an Internet Gateway through a route table, allowing resources inside them to communicate with the internet.

## Private Subnets

Private subnets do not have direct internet access because their route tables are not connected to an Internet Gateway.

Private subnets are useful for hosting:
- Internal applications
- Databases
- Backend services
- Secure internal resources

These resources should not be directly accessible from the public internet for security reasons.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-private_afe1fdbd)

---

# A Dedicated Route Table

## What I Configured

In this step, I associated the private subnet with a dedicated route table called:

- **NextWork Private Route Table**

## Why a Dedicated Route Table Is Important

The private route table does not contain a route to the Internet Gateway.

Because of this:
- Resources inside the private subnet cannot directly access the internet
- Traffic remains internal to the VPC
- The subnet becomes isolated from public internet traffic

This improves security for sensitive AWS resources.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-private_b4b904b5)

---

# A New Network ACL

## Default Network ACL Behavior

By default, the private subnet was associated with the default Network ACL.

I later created and associated a custom Network ACL named:
- **NextWork Private NACL**

## Why I Created a Custom NACL

I created a dedicated Network ACL to configure custom inbound and outbound traffic rules specifically for the private subnet.

## Custom Rules

The custom NACL was configured with rules that:
- Denied all inbound traffic
- Denied all outbound traffic

This demonstrated how Network ACLs can provide subnet-level traffic filtering and stronger network isolation.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-private_1ed2cb07)

---

# Key Learnings

Through this project, I learned:
- The difference between public and private subnets
- How private subnets isolate resources from the internet
- How route tables control internet connectivity
- The role of Network ACLs in subnet-level security
- Why internal-only AWS resources improve security architecture
- How AWS networking components work together inside a VPC

---

# Conclusion

In this project, I successfully created a private subnet inside an Amazon VPC and configured routing and security rules to isolate resources from public internet access.

This project improved my understanding of AWS networking security, traffic isolation, and private cloud architecture.
