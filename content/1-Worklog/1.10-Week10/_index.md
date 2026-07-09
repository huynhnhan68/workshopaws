---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---


### Week 10 Objectives:

* Develop **Backend Lambda**: write code to handle job application CRUD and **S3 Presigned URL** logic to upload CVs.
* Build **Core (SmartCV Shared Layer)**: use **Pydantic** for automatic request validation, **aws-lambda-powertools** to standardize Logs, and Middleware (CORS, Error Handler).
* Set up the **CI/CD** pipeline using **GitHub Actions** with **OIDC** security mechanism (no static IAM Access Keys).

---

### Tasks to be carried out this week:

| No. | Day | Date | Task | Reference Material |
| --- | --- | ---- | ---- | ------------------ |
| 1 | Monday | 22/06/2026 | Develop **Lambda `applications`**  EJob application CRUD: write Python code for endpoints (POST/GET/PUT/DELETE /applications, POST /status), connect to **DynamoDB**, define **Pydantic model** `CreateApplicationRequest` / `UpdateApplicationRequest` with automatic field validators (check `followUpDate` format, ensure non-empty fields). Set up Least Privilege IAM Role. | [docs.aws.amazon.com/lambda](https://docs.aws.amazon.com/lambda/) |
| 2 | Tuesday | 23/06/2026 | Add **S3 Presigned URL** generation logic (upload and download CVs directly from the browser without credentials), configure S3 bucket CORS policy, set expiration time, and validate file types. Integrate `GET /resumes/list` and `DELETE /resumes/{versionName}` endpoints. | [docs.aws.amazon.com/s3/presigned-url](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| 3 | Wednesday | 24/06/2026 | Build **SmartCV Shared Layer (`smartcv-shared`)**: write `shared/middleware.py` module with `resp()` function to standardize HTTP responses with **dynamic CORS origin**, `get_user_id()` / `get_user_email()` to extract claims from Cognito JWT, `parse_body()` for safe JSON parsing, `with_middleware()` decorator for automatic structured logging + global exception handling. Integrate **aws-lambda-powertools** (Logger, Tracer) + **aws-xray-sdk** + **Pydantic v2**. Package into `shared_layer.zip` using the `build_layer.sh` script. | [awslabs.github.io/aws-lambda-powertools-python](https://awslabs.github.io/aws-lambda-powertools-python/) |
| 4 | Thursday | 25/06/2026 | Set up **multi-job CI/CD with GitHub Actions** (`deploy.yml`) consisting of 6 jobs: `test` (pytest + moto, coverage ≥70%) ↁE`test-frontend` (Vitest) ↁE`validate-openapi` (`openapi-spec-validator`) ↁE`deploy-backend` (CDK, only runs when merging to `main`) ↁE`deploy-frontend` (S3 + CloudFront invalidate) ↁE`deploy-frontend-pages` (GitHub Pages). Apply **OIDC** (no static credentials), configure `concurrency` group. Write **OpenAPI Specification** (`api/openapi.yml`) describing 16 API routes. Configure **CodeQL** and **Dependabot** (`.github/dependabot.yml`). | [docs.github.com/actions](https://docs.github.com/en/actions) |
| 5 | Friday | 26/06/2026 | Perform full backend integration testing: test CRUD APIs, test Presigned URL upload/download flow, verify CI/CD pipeline runs successfully on GitHub Actions, check structured logs on CloudWatch. Fix any arising bugs. Write the weekly summary worklog. | [docs.aws.amazon.com/cloudwatch](https://docs.aws.amazon.com/cloudwatch/) |

---

### Week 10 Achievements:

* Successfully developed **Lambda `applications`**:
  * CRUD APIs for job applications connected to DynamoDB.
  * Presigned URL generator for S3 CV upload/download directly from the browser.
  * IAM Role with Least Privilege permission for each Lambda.
  * Defined **Pydantic model** `CreateApplicationRequest` / `UpdateApplicationRequest` with automatic field validators (checked `followUpDate` format, checked for non-empty fields).

* Successfully built **SmartCV Shared Layer (`smartcv-shared`)**:
  * Pydantic models for all request/response schemas.
  * `shared/middleware.py` module: `resp()` function to standardize HTTP response with **dynamic CORS origin**, `get_user_id()` / `get_user_email()` to extract claims from Cognito JWT, `parse_body()` for safe JSON parsing, `with_middleware()` decorator to automatically log structured data + handle global exceptions.
  * Integrated **aws-lambda-powertools** (Logger, Tracer) + **aws-xray-sdk** + **Pydantic v2**.
  * Packaged the layer into `shared_layer.zip` using the `build_layer.sh` script.

* Successfully established **multi-job CI/CD with GitHub Actions + OIDC**:
  * `deploy.yml` file with 6 parallel/sequential jobs: `test` (pytest + moto, coverage ≥70%) ↁE`test-frontend` (Vitest) ↁE`validate-openapi` ↁE`deploy-backend` (CDK) ↁE`deploy-frontend` (S3 + CloudFront invalidate) ↁE`deploy-frontend-pages` (GitHub Pages).
  * OIDC authentication: no static AWS credentials stored, higher security.
  * Configured `concurrency` group to auto-cancel old runs when a new push occurs.
  * Successful automated deployment on every merge to `main`.

* Successfully tested backend integration:
  * All CRUD APIs function correctly.
  * Presigned URL upload flow operates smoothly.
  * CloudWatch Logs recorded structured logs from aws-lambda-powertools.

* Wrote **OpenAPI Specification** (`api/openapi.yml`) fully describing 16 API routes with schemas, parameters, responses, and Cognito JWT security scheme.

* Configured **CodeQL workflow** for automatic security scanning on every Pull Request.

* Configured **Dependabot** (`.github/dependabot.yml`) to automatically update npm and pip dependencies on a weekly schedule.

---

### Plan for next week:

* Integrate **Amazon SES** and **Cognito**: code the `cognito_verify` Lambda as an email verification trigger after registration.
* Configure **Observability**: enable **X-Ray Tracing**, set up **CloudWatch Alarms** and send alerts via **SNS**.
* Write **Integration Tests** to ensure components connect well with each other.
