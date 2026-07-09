---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---


### Week 5 Objectives:

* Conduct in-depth research on **Amazon EC2**: Nitro System architecture, chipset types (AMD/Graviton), Elasticity mechanism.
* Learn about **EC2 Auto Scaling** and pricing models: Reserved Instances (RI), On-Demand, Spot Instances.
* Master storage solutions on AWS: **EBS**, Instance Store, **EFS**, **FSx**, Lightsail, **AWS MGN**.
* Practice deploying and managing EC2 instances with popular storage types.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 18/05/2026 | Research **Amazon EC2** theory: Instance Families (General Purpose, Compute Optimized, Memory Optimized, Storage Optimized), **AMD** and **AWS Graviton** (ARM-based) chipsets, **AWS Nitro System** architecture (next-generation hypervisor). Learn about Amazon Machine Images (AMIs). | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Tuesday | 19/05/2026 | Research **EC2 Auto Scaling**: Launch Templates, Auto Scaling Groups, Scaling Policies (Target Tracking, Step Scaling, Scheduled Scaling). Learn and compare pricing models: **On-Demand**, **Reserved Instances (RI)**  EStandard/Convertible, **Spot Instances**, **Savings Plans**. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Wednesday | 20/05/2026 | Research Block Storage solutions: **Amazon EBS** (gp3, io2, st1, sc1) and **Instance Store** (ephemeral storage). Compare use cases: when to use EBS versus Instance Store. Practice creating and attaching an EBS Volume to an EC2 instance. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thursday | 21/05/2026 | Research File/Object Storage solutions: **Amazon EFS** (Elastic File System  ENFS managed), **Amazon FSx** (FSx for Windows File Server, FSx for Lustre), **Amazon Lightsail** (simple VPS). Learn about **AWS Application Migration Service (MGN)** for migrating On-premises servers to AWS. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 5 | Friday | 22/05/2026 | Comprehensive practice: Create a **t3.micro** EC2 instance (Free Tier), configure Security Groups, attach an EBS Volume, mount EFS to the instance, test connectivity. Clean up resources. Write the weekly summary worklog and compare the pros/cons of the storage solutions. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Week 5 Achievements:

* Mastered knowledge of **Amazon EC2**:
  * Instance Families and their respective use cases.
  * **AWS Nitro System** architecture and its performance advantages.
  * Benefits of **Graviton** chipsets (~40% cost savings).

* Clearly understood the **EC2 Auto Scaling** mechanism and how to set appropriate Scaling Policies for different workloads.

* Successfully compared the pros/cons of pricing models:
  * On-Demand: flexible, no commitment.
  * Reserved Instances: up to 72% savings with a 1-3 year commitment.
  * Spot Instances: up to 90% savings for fault-tolerant workloads.

* Successfully practiced with storage solutions:
  * Created and attached an **EBS Volume** (gp3) to EC2.
  * Mounted **Amazon EFS** to an EC2 instance.
  * Understood the differences between Block, File, and Object Storage.

---

### Plan for next week:

* Complete **Amazon S3** deployment with Access Points, Gateway Endpoints, and a static website supporting CORS.
* Set up data protection mechanisms: **S3 Versioning**, **Object Lock**, Storage Class transitions.
* Deploy backup systems using **AWS Backup** and configure **AWS Storage Gateway**.