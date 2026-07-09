---
title: "Resource Cleanup"
date: 2026-07-09
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

After completing the Workshop, please delete all created AWS resources to avoid unexpected charges.

#### 5.11.1. Empty and delete S3 Bucket

1. Access **Amazon S3**.
2. Select the `smartcv-resumes-YOUR_NAME` bucket.
3. Click **Empty** and confirm the deletion of all objects.
4. Return to the Bucket list, select the bucket, and click **Delete**.
5. Enter the bucket name to confirm.

*(Insert image: Bucket list no longer contains `smartcv-resumes-YOUR_NAME`)*

#### 5.11.2. Delete AWS Amplify App

1. Access **AWS Amplify**.
2. Select the `smartcv-frontend` app.
3. Select **Actions** ↁE**Delete app**.
4. Enter `delete` to confirm, then click **Delete**.

*(Insert image: Amplify list no longer contains `smartcv-frontend`)*

#### 5.11.3. Delete Amazon Cognito User Pool

1. Access **Amazon Cognito**.
2. Select the `smartcv-users` User Pool.
3. Click **Delete**, and enter the User Pool name to confirm.

*(Insert image: User Pool list no longer contains `smartcv-users`)*

#### 5.11.4. Delete DynamoDB Table

1. Access **Amazon DynamoDB** ↁE**Tables**.
2. Select the `smartcv` table, and click **Delete**.
3. Enter `delete` to confirm.

*(Insert image: DynamoDB list no longer contains the `smartcv` table)*

#### 5.11.5. Delete Lambda Functions

1. Access **AWS Lambda**.
2. Select each function: `smartcv-applications`, `smartcv-insights`, `smartcv-settings`, `smartcv-notes`, `smartcv-digest`, `smartcv-followup`, `smartcv-cognito-verify`.
3. Select **Actions** ↁE**Delete** for each function.

#### 5.11.6. Delete EventBridge Schedules

1. Access **Amazon EventBridge** ↁE**Scheduler** ↁE**Schedules**.
2. Select `smartcv-daily-followup` and `smartcv-weekly-digest`.
3. Click **Delete**.

*(Insert image: List of Lambda Functions and EventBridge Schedules after deletion)*

#### 5.11.7. Delete API Gateway

1. Access **API Gateway**.
2. Select the `SmartCV API`.
3. Select **Delete**, and confirm the deletion.

*(Insert image: API Gateway list no longer contains `SmartCV API`)*

#### 5.11.8. Delete IAM Role

1. Access **IAM** ↁE**Roles**.
2. Find `SmartCV-Lambda-Role`.
3. Click **Delete**.

*(Insert image: IAM Roles list no longer contains `SmartCV-Lambda-Role`)*

#### 5.11.9. Delete Amazon SES Identity (Optional)

If you no longer use the verified email for other purposes:
1. Access **Amazon SES** ↁE**Identities**.
2. Select the verified email, and click **Delete**.

{{% notice note %}}
The Enable Model Access step for **Amazon Bedrock** (section 5.10) **does not** incur charges when not in use, so there is no need to "delete" it  Eyou can leave it as is or disable model access in **Model access** if you prefer.
{{% /notice %}}

Congratulations on completing the SmartCV deployment Workshop on AWS Serverless Architecture!