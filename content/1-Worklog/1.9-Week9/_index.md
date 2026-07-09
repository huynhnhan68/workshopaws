---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---


### Week 9 Objectives:

* Officially finalize the **SmartCV** (AI-Powered Job Tracker) project topic and select the **Serverless** architecture.
* Assign tasks to the 4 members of the **Against The Wind** team.
* Design the **6-layer Serverless architecture**: Presentation ↁERouting ↁECompute ↁECore ↁEData ↁEExternal.
* Design the **Event-Driven Architecture** flow including EventBridge cron and Cognito Post-Confirmation trigger.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 15/06/2026 | Officially finalize the **SmartCV  EAI-Powered Job Tracker** topic: define the problem (tracking and optimizing job applications using AI), identify functional and non-functional requirements, and agree on a **fully Serverless** technology stack on AWS. | [aws.amazon.com/serverless](https://aws.amazon.com/serverless/) |
| 2 | Tuesday | 16/06/2026 | Assign tasks to the 4 members of the **Against The Wind** team (Nhan  EHuy  EPhong  EThang) based on architecture layers: Backend Lambda, Frontend React, Infrastructure IaC, AI/Bedrock Integration. Set up GitHub repository, configure GitFlow, and create a Kanban Project Board. | [github.com](https://github.com/) |
| 3 | Wednesday | 17/06/2026 | Design the **6-layer Serverless architecture**: **Presentation** (React) ➁E**Routing** (API GW/CloudFront) ➁E**Compute** (Lambda) ➁E**Core** (Shared Layer) ➁E**Data** (DynamoDB/S3) ➁E**External** (Bedrock/SES). Draw the **Event-Driven Architecture** diagram including EventBridge cron job and Cognito Post-Confirmation trigger. | [draw.io](https://draw.io/) |
| 4 | Thursday | 18/06/2026 | Define the **DynamoDB Single-Table Design** model: define Entities (Applications, Notes, Settings, Users, Streaks) with shared PK/SK/GSI1. Create a **4-week sprint plan** with specific milestones for each member. | [docs.aws.amazon.com/dynamodb](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-general-nosql-design.html) |
| 5 | Friday | 19/06/2026 | Synthesize and review the entire design with the team: check architectural consistency, evaluate Scalability/Cost/Security of each layer. Complete the Architecture Decision Record (ADR) and write the weekly summary worklog. | [draw.io](https://draw.io/) |

---

### Week 9 Achievements:

* Officially finalized the **SmartCV (AI-Powered Job Tracker)** topic and agreed on a **fully Serverless** technology stack on AWS.

* Assigned tasks to the 4 members of the **Against The Wind** team (Nhan  EHuy  EPhong  EThang) based on architecture layers.

* Established collaboration infrastructure for the team:
  * GitHub repository with GitFlow branching.
  * Project Board to track progress (Kanban style).
  * Task assignment per architecture layer.

* Completed the **6-layer Serverless architecture** design:
  * **Presentation** (React) ➁E**Routing** (API GW/CloudFront) ➁E**Compute** (Lambda) ➁E**Core** (Shared Layer) ➁E**Data** (DynamoDB/S3) ➁E**External** (Bedrock/SES).
  * Clearly defined the role of each AWS service in the architecture.

* Successfully designed the **Event-Driven Architecture** flow:
  * EventBridge cron job for automated scanning.
  * Cognito Post-Confirmation trigger for user onboarding.
  * S3 Event trigger for CV processing.

* Defined the **DynamoDB Single-Table Design** model:
  * Defined Entities: Applications, Notes, Settings, Users, Streaks.
  * Designed shared PK/SK/GSI1 for all entities.

* Created a **4-week sprint plan** with specific milestones for each member.

---

### Plan for next week:

* Develop **Backend Lambda `applications`**: write code to handle job application CRUD operations and S3 Presigned URL generation logic.
* Build the **SmartCV Shared Layer**: Pydantic v2, aws-lambda-powertools, aws-xray-sdk, Middleware.
* Set up a **multi-job CI/CD pipeline** using GitHub Actions with OIDC authentication.
