---
title: "Week 12 Worklog"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---


### Week 12 Objectives:

* **Release Management**: review final pull requests, execute **Production Deploy** to finalize version **v1.0.0**.
* **Documentation**: write technical documentation up to software engineering standards (`README.md`, `CHANGELOG.md`, `CONTRIBUTING.md`) and set up **Seed Data** for the Demo.
* **Write Report**: in charge of writing the **6-layer Serverless Architecture Overview** and **DevOps Process (CI/CD GitHub Actions)** sections in the final report.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 06/07/2026 | **Release Management  ECode Freeze**: review and merge all remaining pull requests, run the entire CI/CD pipeline one last time to confirm all jobs are green. Create Release Tag v1.0.0 on GitHub. Execute **Production Deploy** version 1.0.0 to **AWS Amplify** (`d1s2bq5nqqwd9y`) and **GitHub Pages**. | [github.com](https://github.com/) |
| 2 | Tuesday | 07/07/2026 | **Technical Documentation**: rewrite the entire `README.md` (add 5 badges, Vietnamese introduction, collapsible features, detailed Lambda table, numbered step-by-step installation guide, text architecture diagram, directory structure, CI/CD OIDC/Dependabot). Write `CLEANUP.md` guiding the manual cleanup of 19 AWS resources sequentially to avoid dependency errors. | [keepachangelog.com](https://keepachangelog.com/) |
| 3 | Wednesday | 08/07/2026 | **Setup Seed Data for Demo**: write the `scripts/seed_data.py` script to create realistic sample data on DynamoDB and upload sample CVs to S3. Test the entire end-to-end Demo flow smoothly. Delete debug files (`lambda_logs.json`, `response.json`...) and clean up temporary resources. | [docs.aws.amazon.com/dynamodb](https://docs.aws.amazon.com/dynamodb/) |
| 4 | Thursday | 09/07/2026 | **Write Report  EArchitecture Section**: directly responsible for writing the **6-layer Serverless Architecture Overview** section in the final report  Edetail each layer and the reasoning behind choices. Support the preparation of the **FCJ Workshop** (update worklog content, assign tasks in the project's workshop document). | [draw.io](https://draw.io/) |
| 5 | Friday | 10/07/2026 | **Write Report  EDevOps Section**: write the **DevOps Process (CI/CD GitHub Actions)** section  Edescribe OIDC, multi-job pipeline, automated testing, dual deployment S3+GitHub Pages. Complete and review the report. Finalize the version on the GitHub repository. Write the week 12 worklog and summarize the 12-week internship. | [docs.github.com/actions](https://docs.github.com/en/actions) |

---

### Week 12 Achievements:

* **Successful Production Deploy of version v1.0.0**:
  * All pull requests were reviewed and merged.
  * Ran the entire CI/CD pipeline one last time to confirm all jobs were green.
  * Successfully deployed to **AWS Amplify** (`d1s2bq5nqqwd9y`) and **GitHub Pages**.
  * Release Tag v1.0.0 was created on GitHub with comprehensive Release Notes.

* **Completed technical documentation up to software engineering standards**:
  * `README.md`: added 5 badges (CI/CD, AWS Serverless, Python 3.12, React 18, License), Vietnamese introduction section, organized features using `<details>` collapsibles, detailed Lambda Functions table, numbered step-by-step installation guide (Deploy Backend ↁEFrontend ↁETests ↁESeed data), annotated directory structure, CI/CD & Security section (OIDC, Dependabot).
  * `CLEANUP.md`: guide for manually cleaning up 19 AWS resources (Amplify, EventBridge, CloudWatch Alarms & Dashboard, SNS, API Gateway, Lambda x7, Lambda Layer, Cognito, Secrets Manager, SES, S3, DynamoDB, CloudWatch Logs, IAM Roles, KMS, OIDC Provider, CDK Stack, CDK Bootstrap) in order to avoid dependency errors, accompanied by a confirmation checklist and cost estimation table.

* **Successfully set up Seed Data for the Demo**:
  * The `scripts/seed_data.py` script created realistic sample data on DynamoDB.
  * End-to-end Demo flow operated smoothly.

* **Completed Final Report**:
  * 6-layer Serverless Architecture Overview section: detailed description of each layer and the reasons for their selection.
  * DevOps Process (CI/CD GitHub Actions) section: OIDC, multi-job pipeline, automated testing, dual deployment S3+GitHub Pages.

* **Supported the preparation of the FCJ Workshop** (First Cloud Journey): Updated worklog content, task assignments, and weekly progress in the project's workshop document.

* Cleaned up temporary resources: deleted debug files (`lambda_logs.json`, `response.json`...), finalized the version on the GitHub repository.

---

### 12-Week Internship Summary:

* **Weeks 1-3**: AWS Cloud Fundamentals  EVPC, Networking, Hybrid DNS, CloudFormation.
* **Weeks 4-8**: Compute & Storage  EEC2, EBS, EFS, FSx, S3, CloudFront, AWS Backup.
* **Weeks 9-12**: SmartCV Project  EServerless Architecture, Lambda, DynamoDB, CI/CD, Observability.

> Over the 12-week internship at **Amazon Web Services Vietnam**, I accumulated practical knowledge and experience regarding AWS Cloud from basic to advanced, and completed the **SmartCV** project adhering to software engineering standards with a modern Serverless architecture and professional DevOps process.
