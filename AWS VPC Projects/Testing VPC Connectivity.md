# Testing VPC Connectivity

## Architecture Diagram


![Architecture Diagram](https://github.com/user-attachments/assets/8e5c2627-e188-4543-aade-6a213f3fbcd8)



---

# Project Overview

In this project, I tested connectivity between resources deployed inside an Amazon VPC and verified communication with the internet.

The project focused on:

* Connecting to EC2 instances
* SSH access
* Instance-to-instance communication
* Connectivity troubleshooting
* Internet connectivity testing

The goal was to understand how networking configurations affect communication between AWS resources and external networks.

---

# What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a logically isolated networking environment in AWS where cloud resources can communicate securely.

It provides control over:

* Networking
* Routing
* Security
* Internet connectivity
* Resource isolation

---

# How I Used Amazon VPC in This Project

In this project, I used Amazon VPC to:

* Connect to EC2 instances
* Test communication between public and private servers
* Troubleshoot networking issues
* Verify internet connectivity
* Understand how security groups affect communication

---

# Personal Reflection

One thing I did not expect during this project was how often connectivity issues are caused by security group configurations rather than the servers themselves.

This project reinforced the importance of checking networking and security settings before assuming something is wrong with the application.

This project took me approximately 30–45 minutes to complete.

---

# Connecting to an EC2 Instance

## What Is Connectivity?

Connectivity refers to the ability of resources to communicate with one another across a network.

In this project, my first test was verifying whether my public EC2 instance could communicate with my private EC2 instance.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-connectivity_88727bef)

---

# EC2 Instance Connect

## What Is EC2 Instance Connect?

EC2 Instance Connect is an AWS feature that allows users to securely connect to EC2 instances directly from the AWS Management Console.

It simplifies:

* SSH access
* Key management
* Temporary authentication

without requiring local SSH configuration.

## Troubleshooting My Connection

My first attempt to connect to the public EC2 instance resulted in an error because my security group did not allow inbound SSH traffic.

I resolved the issue by adding an inbound rule that allowed SSH (port 22) access to the instance.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-connectivity_1cbb1b88)

---

# Connectivity Between Servers

## Using Ping

The `ping` command is a networking utility used to test whether another device on a network can be reached.

In this project, I used `ping` to verify communication between the public and private EC2 instances.

Example command:

```bash
ping <private-instance-ip>
```

A successful response confirmed that the servers could communicate across the VPC.

This demonstrated that the networking configuration and security rules allowed internal communication.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-connectivity_defghijk)

---

# Troubleshooting Connectivity

When connectivity tests failed, I investigated:

* Security group rules
* Network ACLs
* Route tables
* Instance IP addresses

By reviewing these networking components, I was able to identify and resolve the connectivity issue.

This highlighted the importance of systematically checking each networking layer when troubleshooting AWS environments.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-connectivity_4a9e8014)

---

# Testing Internet Connectivity

## Using Curl

`curl` is a command-line tool used to send HTTP requests and retrieve responses from web servers.

I used `curl` to verify that my EC2 instance could successfully communicate with resources on the internet.

---

# Ping vs Curl

Although both commands test connectivity, they serve different purposes.

| Ping                         | Curl                                 |
| ---------------------------- | ------------------------------------ |
| Tests network reachability   | Tests application/web connectivity   |
| Uses ICMP packets            | Uses HTTP/HTTPS protocols            |
| Confirms a host is reachable | Confirms web services are responding |

---

# Verifying Internet Access

I ran the `curl` command against a public website.

The successful response confirmed that my EC2 instance had outbound internet connectivity through the VPC networking configuration.

This demonstrated that routing, security groups, and internet access were correctly configured.

![Image](http://learn.nextwork.org/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-connectivity_8ee57662)

---

# Key Learnings

Through this project, I learned:

* How to connect to EC2 instances using EC2 Instance Connect
* How to troubleshoot SSH connectivity issues
* How to test communication between EC2 instances
* The difference between `ping` and `curl`
* How networking components affect connectivity
* A structured approach to diagnosing AWS networking problems

---

# Conclusion

In this project, I tested connectivity between EC2 instances and verified internet access within an Amazon VPC.

By troubleshooting networking issues and validating communication using SSH, `ping`, and `curl`, I gained practical experience in diagnosing and verifying AWS network connectivity.
