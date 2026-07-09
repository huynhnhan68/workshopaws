---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---


### Mục tiêu tuần 10:

* Phát triển **Backend Lambda**: viết code xử lý CRUD hồ sơ ứng tuyển và logic tạo **S3 Presigned URL** để upload CV.
* Xây dựng **Core (SmartCV Shared Layer)**: dùng **Pydantic** để validate request tự động, **aws-lambda-powertools** để chuẩn hóa Log và Middleware (CORS, Error Handler).
* Thiết lập pipeline **CI/CD** bằng **GitHub Actions** với cơ chế bảo mật **OIDC** (không dùng IAM Access Key tĩnh).

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 22/06/2026 | Phát triển **Lambda `applications`**  ECRUD hồ sơ ứng tuyển: viết code Python cho các endpoints (POST/GET/PUT/DELETE /applications, POST /status), kết nối **DynamoDB**, định nghĩa **Pydantic model** `CreateApplicationRequest` / `UpdateApplicationRequest` với field validator tự động (kiểm tra định dạng ngày `followUpDate`, kiểm tra field không được rỗng). Thiết lập IAM Role Least Privilege. | [docs.aws.amazon.com/lambda](https://docs.aws.amazon.com/lambda/) |
| 2 | Thứ 3 | 23/06/2026 | Bổ sung logic tạo **S3 Presigned URL** (upload và download CV trực tiếp từ trình duyệt, không cần credentials), cấu hình S3 bucket CORS policy, thiết lập expiration time và validate file type. Tích hợp endpoint `GET /resumes/list` và `DELETE /resumes/{versionName}`. | [docs.aws.amazon.com/s3/presigned-url](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| 3 | Thứ 4 | 24/06/2026 | Xây dựng **SmartCV Shared Layer (`smartcv-shared`)**: viết module `shared/middleware.py` với các hàm `resp()` chuẩn hóa HTTP response kèm **dynamic CORS origin**, `get_user_id()` / `get_user_email()` trích xuất claims từ Cognito JWT, `parse_body()` parse JSON an toàn, `with_middleware()` decorator tự động log structured + bắt exception toàn cục. Tích hợp **aws-lambda-powertools** (Logger, Tracer) + **aws-xray-sdk** + **Pydantic v2**. Đóng gói thành `shared_layer.zip` bằng script `build_layer.sh`. | [awslabs.github.io/aws-lambda-powertools-python](https://awslabs.github.io/aws-lambda-powertools-python/) |
| 4 | Thứ 5 | 25/06/2026 | Thiết lập **CI/CD đa-job bằng GitHub Actions** (`deploy.yml`) gồm 6 job: `test` (pytest + moto, coverage ≥70%) ↁE`test-frontend` (Vitest) ↁE`validate-openapi` (`openapi-spec-validator`) ↁE`deploy-backend` (CDK, chỉ chạy khi merge vào `main`) ↁE`deploy-frontend` (S3 + CloudFront invalidate) ↁE`deploy-frontend-pages` (GitHub Pages). Áp dụng **OIDC** (không lưu credentials tĩnh), cấu hình `concurrency` group. Viết **OpenAPI Specification** (`api/openapi.yml`) mô tả 16 API routes. Cấu hình **CodeQL** và **Dependabot** (`.github/dependabot.yml`). | [docs.github.com/actions](https://docs.github.com/en/actions) |
| 5 | Thứ 6 | 26/06/2026 | Kiểm thử tích hợp toàn bộ backend: test CRUD APIs, test Presigned URL upload/download flow, xác nhận CI/CD pipeline chạy thành công trên GitHub Actions, kiểm tra structured logs trên CloudWatch. Sửa các bug phát sinh. Viết worklog tổng kết tuần. | [docs.aws.amazon.com/cloudwatch](https://docs.aws.amazon.com/cloudwatch/) |

---

### Kết quả đạt được tuần 10:

* Phát triển thành công **Lambda `applications`**:
  * CRUD APIs cho hồ sơ ứng tuyển kết nối DynamoDB.
  * Presigned URL generator cho S3 CV upload/download trực tiếp từ trình duyệt.
  * IAM Role với quyền Least Privilege cho từng Lambda.
  * Định nghĩa **Pydantic model** `CreateApplicationRequest` / `UpdateApplicationRequest` với field validator tự động (kiểm tra định dạng ngày `followUpDate`, kiểm tra field không được rỗng...).

* Xây dựng thành công **SmartCV Shared Layer (`smartcv-shared`)**:
  * Pydantic models cho tất cả request/response schemas.
  * Module `shared/middleware.py`: hàm `resp()` chuẩn hóa HTTP response kèm **dynamic CORS origin**, `get_user_id()` / `get_user_email()` trích xuất claims từ Cognito JWT, `parse_body()` parse JSON an toàn, `with_middleware()` decorator tự động log structured + bắt exception toàn cục.
  * Tích hợp **aws-lambda-powertools** (Logger, Tracer) + **aws-xray-sdk** + **Pydantic v2**.
  * Đóng gói layer thành `shared_layer.zip` bằng script `build_layer.sh`.

* Thiết lập thành công **CI/CD đa-job với GitHub Actions + OIDC**:
  * File `deploy.yml` với 6 job song song/tuần tự: `test` (pytest + moto, coverage ≥70%) ↁE`test-frontend` (Vitest) ↁE`validate-openapi` ↁE`deploy-backend` (CDK) ↁE`deploy-frontend` (S3 + CloudFront invalidate) ↁE`deploy-frontend-pages` (GitHub Pages).
  * OIDC authentication: không lưu AWS credentials tĩnh, bảo mật cao hơn.
  * Cấu hình `concurrency` group để tự hủy run cũ khi có push mới.
  * Automated deployment thành công trên mỗi merge vào `main`.

* Kiểm thử tích hợp backend thành công:
  * Tất cả CRUD APIs hoạt động đúng.
  * Presigned URL upload flow hoạt động.
  * CloudWatch Logs ghi nhận structured logs từ aws-lambda-powertools.

* Viết **OpenAPI Specification** (`api/openapi.yml`) mô tả đầy đủ 16 API routes với schema, parameters, responses và Cognito JWT security scheme.

* Cấu hình **CodeQL workflow** quét bảo mật tự động trên mỗi Pull Request.

* Cấu hình **Dependabot** (`.github/dependabot.yml`) tự động cập nhật dependencies npm và pip theo lịch hàng tuần.

---

### Kế hoạch tuần tiếp theo:

* Tích hợp **Amazon SES** và **Cognito**: code Lambda `cognito_verify` làm trigger xác thực email sau đăng ký.
* Cấu hình **Giám sát (Observability)**: bật **X-Ray Tracing**, cài đặt **CloudWatch Alarms** và gửi cảnh báo qua **SNS**.
* Viết **Integration Tests** để đảm bảo các thành phần kết nối tốt với nhau.
