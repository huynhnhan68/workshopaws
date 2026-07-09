---
title: "Week 7 Worklog"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Week 7 Objectives:

* Deploy an advanced automated backup system with **AWS Backup** and test the restoration process.
* Fully configure **AWS Storage Gateway** (File Gateway) to support SMB file sharing and storage to S3.
* Deploy a **static website on S3 + CloudFront** optimized for speed and security.
* Enable **S3 Cross-Region Replication (CRR)** to ensure Disaster Recovery.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 01/06/2026 | Deploy an advanced automated backup system with **AWS Backup**: create a Backup Vault, configure a detailed Backup Plan (daily/weekly/monthly), establish retention policies. Successfully test the EC2 and EBS restore process from a Recovery Point. Set up stable backup status alerts via **AWS SNS**. | [docs.aws.amazon.com/aws-backup](https://docs.aws.amazon.com/aws-backup/) |
| 2 | Tuesday | 02/06/2026 | Fully configure **AWS Storage Gateway** (File Gateway): upload/download files via **SMB** protocol from a Windows client, verify data is synchronized to the S3 bucket, configure Cache storage to optimize performance. Practice managing the Gateway via the AWS Console. | [docs.aws.amazon.com/storagegateway](https://docs.aws.amazon.com/storagegateway/) |
| 3 | Wednesday | 03/06/2026 | Complete the deployment of a **static website on S3 + CloudFront**: configure **Origin Access Control (OAC)** to block direct access to S3 (only allowing access via CloudFront), set up **CloudFront Cache Behaviors**, configure **Custom Error Pages** and **HTTPS** (SSL/TLS Certificate via ACM). | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thursday | 04/06/2026 | Enable and test advanced **S3 Versioning**: configure **MFA Delete** to protect critical objects, practice restoring deleted objects from previous versions. Configure **S3 Cross-Region Replication (CRR)**: create a Replication Rule, select the destination region, verify data is replicated to the standby region. | [docs.aws.amazon.com/s3](https://docs.aws.amazon.com/s3/) |
| 5 | Friday | 05/06/2026 | Comprehensively test the system: verify the static website operates via the CloudFront URL, check Cross-Region Replication, confirm backup and restore function correctly. Clean up unnecessary resources. Write the weekly summary worklog and note down lessons learned. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Week 7 Achievements:

* Successfully deployed an automated backup system with **AWS Backup**:
  * Backup Vault with encryption.
  * Backup Plan with daily backup schedule and 30-day retention.
  * Successfully tested restoring EC2/EBS from a Recovery Point.
  * Received backup alerts via SNS email notifications.

* Successfully configured **AWS Storage Gateway** (File Gateway):
  * Shared files via SMB protocol from a Windows client.
  * Automatically synchronized data to the S3 bucket.

* Completed the static website on **S3 + CloudFront**:
  * Origin Access Control (OAC): blocked direct S3 access.
  * HTTPS with SSL Certificate (ACM).
  * Optimized CloudFront Cache Behaviors.

* Successfully enabled **S3 Cross-Region Replication (CRR)**:
  * Automatically replicated data to the standby region (ap-southeast-2).
  * Tested recovery from the standby region.

---

### Plan for next week:

* Advanced practice with **Amazon FSx**: Multi-AZ, SSD/HDD, file shares, shadow copies, storage quotas.
* Deploy and operate redundant FSx clusters, measure and monitor performance metrics.
* Activate and comprehensively test **S3 Versioning**.
* Start researching the AWS architecture diagram for the **SmartCV  EAgainst The Wind** team project.