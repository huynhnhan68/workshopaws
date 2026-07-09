---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Week 6 Objectives:

* Complete the deployment of a multi-functional **Amazon S3** setup: Access Points, Gateway Endpoints, static website supporting CORS.
* Set up data protection mechanisms on S3: **Versioning**, **Object Lock**, transitioning to S3 Glacier.
* Operate automated periodic backups using **AWS Backup** and connect hybrid storage via **AWS Storage Gateway**.
* Initialize and perform basic configuration for **Amazon FSx for Windows File Server**.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 25/05/2026 | Deploy a multi-functional **Amazon S3 Bucket**: create an S3 Bucket, configure **S3 Access Points** for granular access control per application, set up a **Gateway Endpoint** (VPC Endpoint for S3) to allow EC2 instances in Private Subnets to securely access S3 without going through the Internet. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Tuesday | 26/05/2026 | Set up **S3 Static Website Hosting** with **CORS** (Cross-Origin Resource Sharing) support: upload HTML/CSS/JS files, configure Bucket Policy to allow public read, configure CORS policy, access the website via S3 endpoint URL. Configure a **CloudFront** distribution pointing to S3 to improve speed and security. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Wednesday | 27/05/2026 | Set up data protection mechanisms on S3: enable **S3 Versioning** to prevent overwrites and accidental deletions, configure **S3 Object Lock** (WORM  EWrite Once Read Many) to comply with storage regulations, set up **Lifecycle Rules** to automatically transition objects to S3 Glacier/Glacier Deep Archive to optimize costs. | [docs.aws.amazon.com/s3](https://docs.aws.amazon.com/s3/) |
| 4 | Thursday | 28/05/2026 | Operate an automated backup system using **AWS Backup**: create a Backup Plan with a periodic backup schedule, assign Resources (EC2, EBS, RDS) to the Backup Plan, test the Restore process from a backup point. Set up backup status alerts via **Amazon SNS**. | [docs.aws.amazon.com/aws-backup](https://docs.aws.amazon.com/aws-backup/) |
| 5 | Friday | 29/05/2026 | Initialize and configure **AWS Storage Gateway** (File Gateway mode) to connect Hybrid storage: install the Storage Gateway Appliance on a virtual machine, configure the connection to S3, create File Shares via SMB/NFS protocols. Perform initial initialization for **Amazon FSx for Windows File Server**. Write the weekly summary worklog. | [docs.aws.amazon.com/storagegateway](https://docs.aws.amazon.com/storagegateway/) |

---

### Week 6 Achievements:

* Completed the deployment of a multi-functional **Amazon S3** setup:
  * S3 Access Points for fine-grained application access control.
  * Gateway Endpoints (VPC Endpoint for S3) allowing EC2s in Private Subnets to access S3 securely.
  * Static Website Hosting with CORS policy and CloudFront integration.

* Successfully set up data protection mechanisms:
  * S3 Versioning: stored multiple versions of each object.
  * S3 Object Lock: prevented unauthorized deletion/modification.
  * Lifecycle Rules: automatically transitioned objects to Glacier to save costs.

* Successfully operated a periodic backup system with **AWS Backup**:
  * Created a Backup Plan with a cron expression schedule.
  * Successfully tested the Restore process from a Recovery Point.
  * Received backup status alerts via SNS.

* Initialized and configured **AWS Storage Gateway** (File Gateway):
  * Successfully connected to the S3 bucket.
  * Created a File Share via SMB protocol.

* Completed the initial setup of **Amazon FSx for Windows File Server**.

---

### Plan for next week:

* Deploy an advanced automated backup system with **AWS Backup** and test restoration.
* Configure **AWS Storage Gateway** to support file sharing via SMB and data storage to S3.
* Deploy a **static website on S3 + CloudFront** and enable **S3 Cross-Region Replication** for Disaster Recovery.