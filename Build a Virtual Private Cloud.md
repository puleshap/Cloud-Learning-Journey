---
# Build a Virtual Private Cloud (VPC)

![Architecture Diagram](https://github.com/user-attachments/assets/ed09b4e5-3656-4bcb-8f6d-d97fadf85cda)

---
## Project Overview
![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project

In this project, I created a Virtual Private Cloud (VPC) in AWS and configured networking components such as subnets and an Internet Gateway.

The goal of this project was to understand how networking works inside AWS and how resources can securely communicate with the internet.

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a networking service in AWS that allows users to create isolated virtual networks for their cloud resources.

It helps separate resources from the public internet and gives more control over networking, security, IP addressing, and connectivity.

### Personal Reflection

This project took me approximately 60 minutes to complete.

One of the interesting parts of this project was learning how VPC networking components work together to enable internet connectivity securely.

I also explored basic AWS CLI usage through CloudShell.

---

# Virtual Private Clouds (VPCs)

## What I Did in This Step

In this step, I created a custom VPC using the AWS Management Console.

## How VPCs Work

VPCs are logically isolated virtual networks within AWS where users can launch and manage cloud resources securely.

They allow full control over networking configurations such as IP ranges, subnets, route tables, and internet access.

## Why There Is a Default VPC in AWS Accounts

There was already a default VPC available in my AWS account. AWS automatically creates a default VPC so users can quickly launch services like EC2 instances without manually configuring networking first.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-vpc_2facf927)

## Defining IPv4 CIDR Blocks

When creating the VPC, I had to define an IPv4 CIDR block.

A CIDR block specifies the IP address range available inside the network and determines how many devices or resources can exist within the VPC.

---

# Subnets

## What I Did in This Step

In this step, I created and configured a subnet inside the VPC.

## Creating and Configuring Subnets

Subnets are smaller network sections within a VPC that help organize and separate resources.

They can be configured as either public or private depending on internet accessibility requirements.

## Public vs Private Subnets

Public subnets are connected to the internet through an Internet Gateway, while private subnets are isolated from direct internet access.

In this project, I configured a public subnet for internet connectivity.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-vpc_157c4219)

## Auto-Assigning Public IPv4 Addresses

I enabled automatic public IPv4 assignment so that EC2 instances launched in the subnet would automatically receive public IP addresses and be accessible from the internet.

---

# Internet Gateways

## What I Did in This Step

In this step, I created and attached an Internet Gateway to the VPC.

## Setting Up Internet Gateways

An Internet Gateway allows communication between resources inside the VPC and the public internet.

By attaching the gateway and updating routing configurations, resources in the public subnet could send and receive internet traffic.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-vpc_4ae90410)

---

# Using the AWS CLI

## What I'm Doing in This Extension

In this section, I explored creating and managing VPC resources using AWS CloudShell and the AWS CLI.

## Exploring CloudShell and CLI

AWS CloudShell provides a browser-based terminal environment with AWS CLI preinstalled, making it easier to interact with AWS services using commands.

## Debugging My Setup

During the setup process, I encountered an issue because the required CIDR block was not properly defined in the command.

After correcting the CIDR configuration, the VPC was successfully created.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-vpc_9b2465411)

## Comparing CloudShell vs AWS Console

The AWS Console is easier for beginners because of its graphical interface, while CloudShell and the AWS CLI provide faster and more flexible management through commands.

Using the CLI also requires some familiarity with Linux/bash commands.

---

# Conclusion

In this project, I learned the fundamentals of AWS networking by creating a custom VPC, configuring subnets, attaching an Internet Gateway, and exploring basic AWS CLI usage.

This project gave me a better understanding of how cloud networking and internet connectivity work inside AWS.
