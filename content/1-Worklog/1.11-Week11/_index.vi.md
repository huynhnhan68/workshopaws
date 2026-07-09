---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---


### Mục tiêu tuần 11:

* Tích hợp **Amazon SES** và **Amazon Cognito**: code Lambda `cognito_verify` làm trigger tự động xác thực email user sau khi đăng ký thành công.
* Cấu hình hệ thống **Giám sát (Observability)**: bật **AWS X-Ray Tracing** cho toàn bộhệ thống, cài đặt **CloudWatch Alarms** và gửi cảnh báo qua **Amazon SNS**.
* Viết **Integration Tests** để đảm bảo các thành phần kết nối tốt với nhau.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 29/06/2026 | Phát triển **Lambda `cognito_verify`**: viết trigger Cognito tự động gọi SES API để verify email ngay sau khi đăng ký thành công. Gắn trigger vào 2 event: `POST_CONFIRMATION` và `POST_AUTHENTICATION`. Xử lý trường hợp email đã verify (**idempotent**) tránh lỗi duplicate. Xác minh email domain/address trong SES sandbox. | [docs.aws.amazon.com/cognito](https://docs.aws.amazon.com/cognito/) |
| 2 | Thứ 3 | 30/06/2026 | Cấu hình **AWS X-Ray Active Tracing** cho toàn bộhệ thống: khai báo `xrayPolicy` IAM và `tracing: lambda.Tracing.ACTIVE` trong CDK cho cả 7 Lambda functions. Xác nhận Service Map hiển thịđầy đủ dependency graph trên X-Ray Console. | [docs.aws.amazon.com/xray](https://docs.aws.amazon.com/xray/) |
| 3 | Thứ 4 | 01/07/2026 | Thiết lập **6 CloudWatch Alarms**: Error alarm (ngưỡng ≥5 lỗi/5 phút) cho 4 Lambda chính; p99 Latency alarm (>10s cho `applications`, >30s cho `insights`). Cấu hình **SNS Topic** `smartcv-alarms` + email subscription, đính kèm vào tất cả alarms qua `SnsAction`. Tạo **CloudWatch Dashboard** `smartcv-overview` gồm 4 widget: Invocations, Errors, Duration p99, Throttles  E6 Lambda trên cùng màn hình. | [docs.aws.amazon.com/cloudwatch](https://docs.aws.amazon.com/cloudwatch/) |
| 4 | Thứ 5 | 02/07/2026 | Viết đầy đủ **Unit Tests** dùng pytest + moto mock AWS (coverage ≥70%): `test_applications.py` + `test_applications_integration.py` (CRUD, Presigned URL, phân trang); `test_cognito_verify.py` (idempotency); `test_insights.py` + `test_insights_analytics.py` + `test_insights_integration.py` (pattern analysis, AI chat); `test_digest.py`, `test_followup.py`, `test_notes.py`, `test_settings.py`; `conftest.py` (fixtures DynamoDB/S3/Cognito mock dùng chung). | [docs.pytest.org](https://docs.pytest.org/) |
| 5 | Thứ 6 | 03/07/2026 | Phối hợp **review Pull Request** từ các thành viên, đảm bảo chất lượng code trước khi merge vào `main`. Kiểm tra end-to-end kết nối **Frontend ↁEAPI Gateway ↁELambda ↁEDynamoDB** trên môi trường staging. Viết worklog tổng kết tuần. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được tuần 11:

* Tích hợp thành công **Amazon Cognito + SES** (Lambda `cognito_verify`):
  * Gắn trigger vào 2 event: `POST_CONFIRMATION` và `POST_AUTHENTICATION`.
  * Xử lý trường hợp email đã verify (idempotent) tránh lỗi duplicate.
  * Email chào mừng tự động gửi qua SES ngay sau khi user xác thực tài khoản.

* Cấu hình thành công **AWS X-Ray Active Tracing**:
  * Khai báo `xrayPolicy` IAM và `tracing: lambda.Tracing.ACTIVE` trong CDK cho toàn bộ7 Lambda.
  * Service Map hiển thịđầy đủ dependency graph của hệ thống.

* Cài đặt thành công **6 CloudWatch Alarms** và **SNS Notifications**:
  * Error alarm (ngưỡng ≥5 lỗi/5 phút) cho 4 Lambda chính.
  * p99 Latency alarm (>10s cho `applications`, >30s cho `insights`).
  * SNS Topic `smartcv-alarms` + email subscription, đính kèm vào tất cả alarms qua `SnsAction`.
  * Email cảnh báo nhận được ngay khi Alarm triggered.

* Tạo **CloudWatch Dashboard** `smartcv-overview` gồm 4 widget: Invocations, Errors, Duration p99, Throttles  Etất cả 6 Lambda hiển thịtrên cùng một màn hình.

* Viết đầy đủ **Unit Tests** (coverage ≥70%) sử dụng pytest + moto mock AWS:
  * `test_applications.py` + `test_applications_integration.py`: kiểm tra toàn bộCRUD, S3 Presigned URL, phân trang.
  * `test_cognito_verify.py`: mock Cognito + SES, kiểm tra idempotency.
  * `test_insights.py` + `test_insights_analytics.py` + `test_insights_integration.py`: kiểm tra pattern analysis engine, AI chat flow.
  * `test_digest.py`, `test_followup.py`, `test_notes.py`, `test_settings.py`: kiểm tra toàn bộ Lambda còn lại.
  * `conftest.py`: setup fixtures DynamoDB mock, S3 mock, Cognito mock dùng chung.

---

### Kế hoạch tuần tiếp theo:

* **Quản lý Release**: duyệt pull requests cuối, thực hiện **Production Deploy** chốt phiên bản.
* **Tài liệu hóa**: viết `README.md`, `CHANGELOG.md`, `CONTRIBUTING.md` và setup **Seed Data** cho Demo.
* **Viết Báo Cáo**: phần Tổng quan Kiến trúc Serverless 6-layer và Quy trình DevOps (CI/CD GitHub Actions).
