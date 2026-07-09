---
title: "Amazon Bedrock"
date: 2026-07-09
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

Amazon Bedrock is a generative AI service used by SmartCV to analyze the content of CVs/job applications and provide suggestions for improvement (via the `smartcv-insights` and `smartcv-digest` Lambdas). The model chosen for the project is **Amazon Nova Lite** (`amazon.nova-lite-v1:0`)  Eoptimizing costs and available in the `ap-southeast-1` region.

{{% notice warning %}}
**Mandatory step before testing Lambda:** Amazon Bedrock requires you to **Enable Model Access** in its own console for each model, which is **completely separate** from IAM permissions. Even if the Lambda Role has `AmazonBedrockFullAccess`, if the model is not enabled in this step, all API calls will return an `AccessDeniedException` error. Please do this step **before** configuring Lambda in section [5.5](../5.5-lambda/).
{{% /notice %}}

#### Step 1: Enable Model Access

1. Access the **Amazon Bedrock** service on the AWS Console, ensuring you are in the `ap-southeast-1` region (or the region supporting Nova Lite that you use throughout the Workshop).
2. In the left menu, select **Model access** (located under Bedrock configurations).
3. Click **Modify model access** (or **Manage model access**, depending on the UI version).
4. Find the **Amazon Nova Lite** model and check the box next to it.
5. Scroll down, read, and accept the End User License Agreement (EULA) if required.
6. Click **Request model access** (or **Save changes**).

![Enable Model Access for Amazon Nova Lite](/images/5-Workshop/5.10-Bedrock/enable-model-access.png)

7. Wait a few seconds to a few minutes; the model status will change from *Available to request* ↁE**Access granted**.

![Model has been granted access](/images/5-Workshop/5.10-Bedrock/access-granted.png)

#### Step 2: Test the model in the Playground (Optional, recommended)

Before integrating into Lambda, it is recommended to test the model directly to understand the input/output format:

1. In the left menu of Bedrock, select **Playgrounds** ↁE**Chat / Text**.
2. Select the **Amazon Nova Lite** model.
3. Try entering a sample CV snippet and an analysis prompt, for example: