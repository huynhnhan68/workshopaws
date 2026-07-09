---
title: "Week 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Week 4 Objectives:

* Optimize **VPC Peering** architecture with Route Tables and Cross-Peer DNS Resolution.
* Deploy **AWS Transit Gateway** to connect 4 VPCs in a Hub-and-Spoke architecture.
* Practice **Infrastructure as Code** using **AWS CloudFormation** and **Application Composer**.
* Use **VPC Reachability Analyzer** to analyze and troubleshoot network issues.
* Set up a **Bastion Host** to securely manage servers in Private Subnets.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 11/05/2026 | Optimize **VPC Peering**: configure Route Tables to allow traffic through the Peering Connection, enable **DNS Resolution** (Cross-Peer DNS) so EC2 instances can communicate using DNS names instead of IP addresses. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Tuesday | 12/05/2026 | Deploy **AWS Transit Gateway** for 4 VPCs using a Hub-and-Spoke model: create a Transit Gateway, create Transit Gateway Attachments for each VPC, configure Transit Gateway Route Tables, and test inter-VPC connectivity. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Wednesday | 13/05/2026 | Practice advanced **Infrastructure as Code** with **AWS CloudFormation**: use **Application Composer** to design architecture through a graphical interface and automatically generate CloudFormation templates. Deploy the stack and verify the results. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thursday | 14/05/2026 | Use **VPC Reachability Analyzer** to analyze connectivity between network resources: create an analysis between a source and destination, read the results, and identify the root cause of issues (Security Groups, Route Tables, NACLs). Practice troubleshooting common network errors. | [docs.aws.amazon.com](https://docs.aws.amazon.com/vpc/latest/reachability/) |
| 5 | Friday | 15/05/2026 | Set up a **Bastion Host** (Jump Server) in a Public Subnet: create an EC2 instance, configure Security Groups to allow SSH from authorized IPs, and practice multi-hop SSH connections to EC2 instances in Private Subnets via the Bastion. Write the weekly summary worklog. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Week 4 Achievements:

* Successfully optimized the **VPC Peering** architecture:
  * Configured bidirectional Route Tables between VPCs.
  * Enabled DNS Resolution over Peering Connections, allowing systems to communicate using names instead of IPs.

* Successfully deployed **AWS Transit Gateway** to connect 4 VPCs:
  * Created the Transit Gateway and Attachments.
  * Configured Transit Gateway Route Tables.
  * Confirmed successful connectivity across all VPCs.

* Mastered the **Infrastructure as Code** process using CloudFormation + Application Composer.

* Proficiently used **VPC Reachability Analyzer** to analyze and troubleshoot network issues.

* Successfully set up a **Bastion Host** and established SSH connections to EC2 instances in Private Subnets via the Jump Server.

---

### Plan for next week:

* Research **Amazon EC2** theory: Elasticity, AMD/Graviton chipsets, Nitro system.
* Learn about **Auto Scaling** and pricing models: Reserved Instances, On-Demand, Spot.
* Research storage solutions: **EBS**, Instance Store, **EFS**, **FSx**, Lightsail, **AWS MGN**.