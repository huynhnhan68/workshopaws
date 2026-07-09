---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---


### Mục tiêu tuần 9:

* Định hình chính thức đề tài **SmartCV** (AI-Powered Job Tracker) và lựa chọn kiến trúc **Serverless**.
* Phân công công việc cho 4 thành viên nhóm **Against The Wind**.
* Thiết kế kiến trúc **Serverless 6-layer**: Presentation ↁERouting ↁECompute ↁECore ↁEData ↁEExternal.
* Thiết kế luồng sự kiện **Event-Driven Architecture** bao gồm EventBridge cron và Cognito Post-Confirmation trigger.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 15/06/2026 | Định hình chính thức đề tài **SmartCV  EAI-Powered Job Tracker**: xác định bài toán (theo dõi và tối ưu hóa hồ sơ xin việc bằng AI), phân tích yêu cầu chức năng (Functional Requirements) và phi chức năng (Non-Functional Requirements). Lựa chọn stack công nghệ**Serverless** trên AWS. | [aws.amazon.com/serverless](https://aws.amazon.com/serverless/) |
| 2 | Thứ 3 | 16/06/2026 | Phân công công việc cho 4 thành viên nhóm **Against The Wind**: xác định vai trò (Backend Lambda, Frontend React, Infrastructure IaC, AI/Bedrock Integration), thiết lập repository GitHub, cấu hình branching strategy (GitFlow), tạo Project Board để theo dõi tiến độ | [github.com](https://github.com/) |
| 3 | Thứ 4 | 17/06/2026 | Thiết kế kiến trúc **Serverless 6-layer** cho SmartCV: **Layer 1  EPresentation** (React SPA trên S3+CloudFront) ↁE**Layer 2  ERouting** (API Gateway + CloudFront) ↁE**Layer 3  ECompute** (AWS Lambda Python) ↁE**Layer 4  ECore** (SmartCV Shared Layer) ↁE**Layer 5  EData** (DynamoDB + S3) ↁE**Layer 6  EExternal** (Amazon Bedrock + Amazon SES). Vẽ sơ đồ kiến trúc chi tiết. | [draw.io](https://draw.io/) |
| 4 | Thứ 5 | 18/06/2026 | Thiết kế luồng sự kiện **Event-Driven Architecture**: vẽ sơ đồ**EventBridge** cron job (tự động scan job posting định kỳ), thiết kế **Cognito Post-Confirmation trigger** (Lambda tự động khởi tạo user profile sau đăng ký), xác định các event flow khác (S3 Event ↁELambda xử lý CV, Bedrock AI analysis). | [docs.aws.amazon.com/eventbridge](https://docs.aws.amazon.com/eventbridge/) |
| 5 | Thứ 6 | 19/06/2026 | Tổng hợp và review toàn bộthiết kế với nhóm: kiểm tra tính nhất quán của kiến trúc, đánh giá Scalability/Cost/Security của từng layer, điều chỉnh thiết kế dựa trên feedback. Viết tài liệu thiết kế sơ bộ(Architecture Decision Record  EADR). Viết worklog tổng kết tuần. | [draw.io](https://draw.io/) |

---

### Kết quả đạt được tuần 9:

* Định hình thành công đề tài **SmartCV (AI-Powered Job Tracker)**:
  * Xác định rõ bài toán và yêu cầu hệ thống.
  * Lựa chọn kiến trúc Serverless tối ưu cho use case.

* Thiết lập hạ tầng cộng tác cho nhóm **Against The Wind** (Nhân  EHuy  EPhong  EThắng):
  * GitHub repository với GitFlow branching.
  * Project Board để theo dõi tiến độ (Kanban style).
  * Phân công theo từng lớp kiến trúc.

* Hoàn thành thiết kế kiến trúc **Serverless 6-layer**:
  * **Presentation** (React) ➁E**Routing** (API GW/CloudFront) ➁E**Compute** (Lambda) ➁E**Core** (Shared Layer) ➁E**Data** (DynamoDB/S3) ➁E**External** (Bedrock/SES).
  * Xác định rõ vai trò từng AWS service trong kiến trúc.

* Thiết kế thành công luồng sự kiện **Event-Driven Architecture**:
  * EventBridge cron job cho automated scanning.
  * Cognito Post-Confirmation trigger cho user onboarding.
  * S3 Event trigger cho CV processing.

* Xác định mô hình **DynamoDB Single-Table Design**:
  * Định nghĩa các Entity: Applications, Notes, Settings, Users, Streaks.
  * Thiết kế PK/SK/GSI1 chung cho toàn bộ entity.

* Lập **kế hoạch sprint 4 tuần** với milestone cụ thểcho từng thành viên.

---

### Kế hoạch tuần tiếp theo:

* Phát triển **Backend Lambda**: viết code xử lý CRUD hồ sơ ứng tuyển và logic tạo S3 Presigned URL.
* Xây dựng **Core (SmartCV Shared Layer)**: Pydantic validation, aws-lambda-powertools logging, Middleware.
* Thiết lập **CI/CD pipeline** bằng GitHub Actions với OIDC authentication.
