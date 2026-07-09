---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Week 2 Objectives:

* Learn and practice with **Amazon Virtual Private Cloud (VPC)**  Ethe core virtual networking service of AWS.
* Learn how to design, deploy, and manage private network environments on AWS Cloud.
* Configure secure **Site-to-Site VPN** connections between On-premises infrastructure and AWS Cloud.
* Master **Security Group**, **Network ACL**, **Internet Gateway**, and **NAT Gateway**.
* Understand and practice **VPC Peering**, **Transit Gateway**, and **Elastic Load Balancer**.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 27/04/2026 | Learn about network architecture on AWS: concepts of **Amazon VPC**, CIDR block, Subnets (Public/Private), Availability Zones. Practice creating a VPC with Public and Private Subnets distributed across multiple AZs. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Tuesday | 28/04/2026 | Research and configure **Security Groups** (stateful firewall for EC2) and **Network ACLs** (stateless firewall for Subnets) to control traffic and enhance system security. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Wednesday | 29/04/2026 | Set up an **Internet Gateway** (for Public Subnets), **NAT Gateway** (for Private Subnets to access the Internet), **Route Tables**, and learn about **VPC Endpoints** (accessing S3/DynamoDB without going through the Internet). Practice configuring **Site-to-Site VPN**. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thursday | 30/04/2026 | Learn about **VPC Peering** (direct connection between two VPCs), **Transit Gateway** (central hub connecting multiple VPCs), and methods for connecting On-premises systems to AWS: **AWS VPN** and **AWS Direct Connect**. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 5 | Friday | 01/05/2026 | Practice with **Elastic Load Balancer**: **ALB** (Application Load Balancer  ELayer 7), **NLB** (Network Load Balancer  ELayer 4), **GWLB** (Gateway Load Balancer  ELayer 3). Complete Lab 03 on AWS network infrastructure and write the weekly summary worklog. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Week 2 Achievements:

* Successfully set up a basic network system on AWS including:
  * 01 Amazon VPC with an appropriate CIDR block.
  * Public Subnets and Private Subnets distributed across multiple Availability Zones.

* Completed the configuration of security components:
  * Security Groups for EC2 with Inbound/Outbound rules.
  * Network ACLs for Subnets.

* Successfully deployed and configured:
  * Internet Gateway.
  * NAT Gateway.
  * Route Table.
  * VPC Endpoint for S3.

* Clearly understood the routing mechanisms in Amazon VPC and the relationships between network components.

* Mastered the operational principles of:
  * VPC Peering.
  * Transit Gateway.
  * AWS VPN (Site-to-Site).
  * AWS Direct Connect.
  * VPC Endpoint.

* Practiced with Elastic Load Balancer services, including:
  * Application Load Balancer (ALB).
  * Network Load Balancer (NLB).
  * Gateway Load Balancer (GWLB).

* Understood the role of Load Balancers in distributing traffic, enhancing scalability, and ensuring system availability.

---

### Plan for next week:

* Practice building a **Hybrid DNS** system integrating On-premises DNS with **Amazon Route 53**.
* Deploy infrastructure using **AWS CloudFormation**.
* Configure **Inbound/Outbound Endpoints** and **Resolver Rules** for Route 53.