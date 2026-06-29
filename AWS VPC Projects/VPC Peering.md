# VPC Peering

## Architecture Diagram

> Add your architecture diagram here near the beginning of the document so readers can immediately understand how the two VPCs communicate.


![Architecture Diagram](https://github.com/user-attachments/assets/a8441b94-7739-459c-b525-844f25cd8587)



# Project Overview

In this project, I configured VPC Peering between two Amazon VPCs to enable private communication between resources without using the public internet.

The project focused on:

* Creating multiple VPCs
* Configuring a VPC Peering Connection
* Updating route tables
* Launching EC2 instances
* Testing private connectivity
* Troubleshooting networking issues

The goal was to understand how AWS networks can securely communicate across separate VPCs.

---

# What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a logically isolated networking environment within AWS that allows users to securely deploy cloud resources.

It provides complete control over:

* Networking
* IP addressing
* Routing
* Security
* Internet connectivity

---

# How I Used Amazon VPC in This Project

In this project, I used Amazon VPC to:

* Create two separate VPCs
* Establish a VPC Peering Connection
* Configure routing between the VPCs
* Deploy EC2 instances into each VPC
* Test secure communication across private networks

---

# Personal Reflection

One thing I did not expect during this project was how many networking components need to work together before two VPCs can communicate successfully.

This project took me approximately 45–60 minutes to complete.

---

# Project Workflow

The project consisted of the following steps:

1. Create two VPCs
2. Establish a VPC Peering Connection
3. Update Route Tables
4. Launch EC2 Instances
5. Connect using EC2 Instance Connect
6. Test communication between VPCs
7. Troubleshoot networking issues

---

# Multi-VPC Architecture

## Creating Two VPCs

I began by creating two independent Amazon VPCs.

Each VPC used its own unique IPv4 CIDR block.

The CIDR blocks must not overlap because AWS cannot correctly route traffic between VPCs that share the same IP address range.

## Launching EC2 Instances

I launched one EC2 instance inside each VPC.

Since I planned to use EC2 Instance Connect, I did not create traditional SSH key pairs for these instances.

![Image](http://nextwork.ai/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-peering_11111111)

---

# VPC Peering

## What Is VPC Peering?

A VPC Peering Connection is a private networking connection between two VPCs.

It allows resources in different VPCs to communicate using private IP addresses without sending traffic across the public internet.

This improves:

* Security
* Performance
* Network isolation

## Requester vs Accepter

When creating a VPC Peering Connection:

* **Requester** initiates the connection request.
* **Accepter** reviews and accepts the request.

Communication is enabled only after the peering request has been accepted.

![Image](http://nextwork.ai/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-peering_1cbb1b88)

---

# Updating Route Tables

After the peering connection was accepted, I updated the route tables for both VPCs.

This was necessary so that traffic destined for the other VPC would be routed through the VPC Peering Connection.

The new route contained:

* **Destination:** The CIDR block of the peer VPC
* **Target:** The VPC Peering Connection

Without these routes, the two VPCs would not know how to reach one another.

![Image](http://nextwork.ai/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-peering_4a9e8014)

---

# Connecting to the EC2 Instances

## EC2 Instance Connect

I used EC2 Instance Connect to securely access my EC2 instance through the AWS Management Console.

This removed the need to manually manage SSH key pairs while still providing secure access.

---

# Troubleshooting EC2 Instance Connect

Initially, EC2 Instance Connect was unavailable because the instance did not have a public IPv4 address.

Without a public IP address, AWS could not establish the management connection.

![Image](http://nextwork.ai/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-peering_7685490c)

---

# Elastic IP Addresses

To resolve the issue, I associated an Elastic IP address with my EC2 instance.

An Elastic IP is a static public IPv4 address that remains associated with an instance until it is manually released.

Assigning the Elastic IP allowed EC2 Instance Connect to establish a successful connection.

![Image](http://nextwork.ai/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-peering_45663498)

---

# Testing VPC Peering

## Verifying Connectivity

After both VPCs were connected, I tested communication between the EC2 instances using the `ping` command.

Example:

```bash
ping <private-ip-address>
```

A successful response confirmed that:

* The VPC Peering Connection was active
* Route tables were correctly configured
* Traffic was successfully routed between both VPCs

---

# Troubleshooting Ping Issues

Initially, the ping test failed because the second EC2 instance's security group did not allow ICMP traffic.

To resolve the issue, I updated the security group by adding an inbound rule that allowed ICMP Echo Requests from the peer VPC.

Once the rule was added, the ping test completed successfully.

![Image](http://nextwork.ai/restful_navy_jolly_buddha's_hand_citron/uploads/aws-networks-peering_7a29d352)

---

# Key Learnings

Through this project, I learned:

* How VPC Peering enables private communication between AWS networks
* Why each VPC requires a unique CIDR block
* How route tables direct traffic between peered VPCs
* The roles of the requester and accepter in a peering connection
* How Elastic IPs enable EC2 Instance Connect
* How security groups affect ICMP traffic
* How to troubleshoot connectivity issues between AWS resources

---

# Conclusion

In this project, I successfully configured VPC Peering between two Amazon VPCs and verified private communication between EC2 instances.

This project strengthened my understanding of AWS networking architecture, routing, security groups, and secure communication across multiple VPCs—an important concept used in many real-world cloud environments.
