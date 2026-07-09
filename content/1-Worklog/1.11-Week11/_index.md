---
title: "Week 11 Worklog"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---


### Week 11 Objectives:

* Integrate **Amazon SES** and **Amazon Cognito**: code Lambda `cognito_verify` as a trigger to automatically verify user email after successful registration.
* Configure the **Observability** system: enable **AWS X-Ray Tracing** for the entire system, set up **CloudWatch Alarms** and send alerts via **Amazon SNS**.
* Write **Integration Tests** to ensure components connect well with each other.

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 29/06/2026 | Develop **Lambda `cognito_verify`**: write a Cognito trigger to automatically call the SES API to verify emails immediately after successful registration. Attach the trigger to 2 events: `POST_CONFIRMATION` and `POST_AUTHENTICATION`. Handle already verified emails (**idempotent**) to prevent duplicate errors. Verify email domain/address in the SES sandbox. | [docs.aws.amazon.com/cognito](https://docs.aws.amazon.com/cognito/) |
| 2 | Tuesday | 30/06/2026 | Configure **AWS X-Ray Active Tracing** for the entire system: declare IAM `xrayPolicy` and `tracing: lambda.Tracing.ACTIVE` in CDK for all 7 Lambda functions. Confirm the Service Map fully displays the system's dependency graph on the X-Ray Console. | [docs.aws.amazon.com/xray](https://docs.aws.amazon.com/xray/) |
| 3 | Wednesday | 01/07/2026 | Set up **6 CloudWatch Alarms**: Error alarm (threshold ≥5 errors/5 mins) for 4 main Lambdas; p99 Latency alarm (>10s for `applications`, >30s for `insights`). Configure **SNS Topic** `smartcv-alarms` + email subscription, attach it to all alarms via `SnsAction`. Create **CloudWatch Dashboard** `smartcv-overview` consisting of 4 widgets: Invocations, Errors, Duration p99, Throttles  Eall 6 Lambdas on one screen. | [docs.aws.amazon.com/cloudwatch](https://docs.aws.amazon.com/cloudwatch/) |
| 4 | Thursday | 02/07/2026 | Write comprehensive **Unit Tests** using pytest + moto mock AWS (coverage ≥70%): `test_applications.py` + `test_applications_integration.py` (CRUD, Presigned URL, pagination); `test_cognito_verify.py` (idempotency); `test_insights.py` + `test_insights_analytics.py` + `test_insights_integration.py` (pattern analysis, AI chat); `test_digest.py`, `test_followup.py`, `test_notes.py`, `test_settings.py`; `conftest.py` (shared DynamoDB/S3/Cognito mock fixtures). | [docs.pytest.org](https://docs.pytest.org/) |
| 5 | Friday | 03/07/2026 | Coordinate **Pull Request reviews** from team members, ensuring code quality before merging into `main`. Test end-to-end connections **Frontend ↁEAPI Gateway ↁELambda ↁEDynamoDB** in the staging environment. Write the weekly summary worklog. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Week 11 Achievements:

* Successfully integrated **Amazon Cognito + SES** (Lambda `cognito_verify`):
  * Attached trigger to 2 events: `POST_CONFIRMATION` and `POST_AUTHENTICATION`.
  * Handled the case of already verified emails (idempotent) to prevent duplicate errors.
  * Welcome email automatically sent via SES right after the user successfully verifies their account.

* Successfully configured **AWS X-Ray Active Tracing**:
  * Declared IAM `xrayPolicy` and `tracing: lambda.Tracing.ACTIVE` in CDK for all 7 Lambdas.
  * Service Map fully displayed the system's dependency graph.

* Successfully set up **6 CloudWatch Alarms** and **SNS Notifications**:
  * Error alarm (threshold ≥5 errors/5 mins) for 4 main Lambdas.
  * p99 Latency alarm (>10s for `applications`, >30s for `insights`).
  * SNS Topic `smartcv-alarms` + email subscription, attached to all alarms via `SnsAction`.
  * Alert emails received immediately when an Alarm is triggered.

* Created **CloudWatch Dashboard** `smartcv-overview` consisting of 4 widgets: Invocations, Errors, Duration p99, Throttles  Eall 6 Lambdas displayed on a single screen.

* Wrote comprehensive **Unit Tests** (coverage ≥70%) using pytest + moto mock AWS:
  * `test_applications.py` + `test_applications_integration.py`: tested full CRUD, S3 Presigned URL, pagination.
  * `test_cognito_verify.py`: mocked Cognito + SES, tested idempotency.
  * `test_insights.py` + `test_insights_analytics.py` + `test_insights_integration.py`: tested pattern analysis engine, AI chat flow.
  * `test_digest.py`, `test_followup.py`, `test_notes.py`, `test_settings.py`: tested all remaining Lambdas.
  * `conftest.py`: set up shared DynamoDB mock, S3 mock, and Cognito mock fixtures.

---

### Plan for next week:

* **Release Management**: review final pull requests, execute **Production Deploy** to finalize the version.
* **Documentation**: write `README.md`, `CHANGELOG.md`, `CONTRIBUTING.md` and set up **Seed Data** for the Demo.
* **Write Report**: 6-layer Serverless Architecture Overview and DevOps Process (CI/CD GitHub Actions) sections.
