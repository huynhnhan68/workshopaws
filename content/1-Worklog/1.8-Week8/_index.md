---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---


### Week 8 Objectives:

* Advanced practice with **Amazon FSx for Windows File Server**: Multi-AZ, SSD/HDD, file shares, shadow copies, storage quotas.
* Deploy and operate redundant FSx clusters, measure and monitor performance metrics.
* Activate and comprehensively test **S3 Versioning**.
* Start researching and drawing the AWS architecture diagram for the **Against The Wind  ESmartCV** team project.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 08/06/2026 | Research advanced **Amazon FSx for Windows File Server**: compare Single-AZ vs **Multi-AZ** deployments, compare **SSD** (high IOPS) vs **HDD** (cost-efficient). Create an FSx Multi-AZ file system with SSD configuration, set up connections from Windows EC2 instances. | [docs.aws.amazon.com/fsx](https://docs.aws.amazon.com/fsx/) |
| 2 | Tuesday | 09/06/2026 | Advanced FSx configuration: create and manage **File Shares** (SMB shares), configure **Storage Quotas** for each user/group, enable **Shadow Copies** (VSS  EVolume Shadow Copy Service) to automatically create periodic file snapshots. Test file restoration from a Shadow Copy. | [docs.aws.amazon.com/fsx](https://docs.aws.amazon.com/fsx/) |
| 3 | Wednesday | 10/06/2026 | Measure and monitor **FSx performance**: use **Amazon CloudWatch** to view metrics (DataReadBytes, DataWriteBytes, NetworkThroughput, StorageCapacityUtilization), create a Dashboard to monitor performance. Practice adding an FSx HDD cluster and compare its performance results with the SSD cluster. | [docs.aws.amazon.com/cloudwatch](https://docs.aws.amazon.com/cloudwatch/) |
| 4 | Thursday | 11/06/2026 | Activate and comprehensively test **S3 Versioning**: upload multiple versions of the same object, list all versions, restore an object to a specific version, remove Delete Markers, compare Bucket behavior with/without Versioning. | [docs.aws.amazon.com/s3](https://docs.aws.amazon.com/s3/) |
| 5 | Friday | 12/06/2026 | Start researching and drawing the AWS architecture diagram for the **Against The Wind** team project regarding the "**AI-Powered Job Tracker System  ESmartCV**": identify the AWS services to be used (Lambda, DynamoDB, S3, Bedrock, Cognito, API Gateway), draft the High-Level Architecture Diagram. Clean up FSx resources. Write the summary worklog. | [draw.io](https://draw.io/) |

---

### Week 8 Achievements:

* Successfully practiced advanced **Amazon FSx for Windows File Server**:
  * Successfully initialized redundant **Multi-AZ** storage clusters (SSD and HDD).
  * Configured File Shares and successfully shared resources from Windows clients.
  * Enabled and tested **Shadow Copies**  Erestored files from snapshots.
  * Configured **Storage Quotas** for individual users.

* Successfully measured and monitored **FSx performance metrics** via CloudWatch:
  * Created a CloudWatch Dashboard monitoring IOPS, Throughput, and Storage Utilization.
  * Compared practical SSD vs HDD performance.

* Successfully activated and tested **S3 Versioning**:
  * Managed multiple object versions.
  * Restored objects to desired versions.

* Started drafting the AWS architecture diagram for the **SmartCV** project:
  * Identified the necessary AWS services to use.
  * Drafted the High-Level Architecture Diagram.

---

### Plan for next week:

* Officially finalize the **SmartCV** (AI-Powered Job Tracker) project topic and select the **Serverless** architecture.
* Assign tasks to the 4 members of the **Against The Wind** team.
* Design the 6-layer architecture: Presentation ↁERouting ↁECompute ↁECore ↁEData ↁEExternal.
* Design the **Event-Driven Architecture** flow with EventBridge and Cognito.