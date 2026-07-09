---
title: "Worklog Tuần 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---


### Mục tiêu tuần 12:

* **Quản lý Release**: duyệt các pull request cuối cùng, thực hiện **Production Deploy** để chốt phiên bản **v1.0.0**.
* **Tài liệu hóa (Documentation)**: viết tài liệu kỹ thuật chuẩn kỹ sư phần mềm (`README.md`, `CHANGELOG.md`, `CONTRIBUTING.md`) và setup **Seed Data** cho Demo.
* **Viết Báo Cáo**: phụ trách viết phần **Tổng quan Kiến trúc Serverless 6-layer** và **Quy trình DevOps (CI/CD GitHub Actions)** trong báo cáo tổng kết.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 06/07/2026 | **Quản lý Release  ECode Freeze**: duyệt và merge tất cả các pull request cuối cùng, chạy toàn bộCI/CD pipeline lần cuối xác nhận tất cả job xanh. Tạo Release Tag v1.0.0 trên GitHub. Thực hiện **Production Deploy** phiên bản 1.0.0 lên **AWS Amplify** (`d1s2bq5nqqwd9y`) và **GitHub Pages**. | [github.com](https://github.com/) |
| 2 | Thứ 3 | 07/07/2026 | **Tài liệu hóa kỹ thuật**: viết lại toàn bộ `README.md` (thêm 5 badges, giới thiệu tiếng Việt, collapsible tính năng, bảng Lambda chi tiết, hướng dẫn cài đặt từng bước, sơ đồ kiến trúc text, cấu trúc thư mục, CI/CD OIDC/Dependabot). Viết `CLEANUP.md` hướng dẫn dọn dẹp thủ công 19 tài nguyên AWS theo thứ tự tránh dependency error. | [keepachangelog.com](https://keepachangelog.com/) |
| 3 | Thứ 4 | 08/07/2026 | **Setup Seed Data cho Demo**: viết script `scripts/seed_data.py` tạo dữ liệu mẫu thực tế trên DynamoDB và upload CV mẫu lên S3. Kiểm thử toàn bộluồng Demo end-to-end trơn tru. Xóa file debug (`lambda_logs.json`, `response.json`...) và dọn dẹp tài nguyên tạm thời. | [docs.aws.amazon.com/dynamodb](https://docs.aws.amazon.com/dynamodb/) |
| 4 | Thứ 5 | 09/07/2026 | **Viết Báo Cáo  EPhần Kiến trúc**: trực tiếp phụ trách viết phần **Tổng quan Kiến trúc Serverless 6-layer** trong báo cáo tổng kết  Emô tả chi tiết từng layer và lý do lựa chọn. Hỗ trợ chuẩn bị**Workshop FCJ** (cập nhật nội dung worklog, phân công công việc vào tài liệu workshop). | [draw.io](https://draw.io/) |
| 5 | Thứ 6 | 10/07/2026 | **Viết Báo Cáo  EPhần DevOps**: viết phần **Quy trình DevOps (CI/CD GitHub Actions)**  Emô tả OIDC, multi-job pipeline, automated testing, dual deployment S3+GitHub Pages. Hoàn thiện và review báo cáo. Chốt phiên bản cuối cùng trên GitHub repository. Viết worklog tuần 12 và tổng kết 12 tuần thực tập. | [docs.github.com/actions](https://docs.github.com/en/actions) |

---

### Kết quả đạt được tuần 12:

* **Production Deploy thành công phiên bản v1.0.0**:
  * Tất cả pull requests đã được review và merge.
  * Chạy toàn bộCI/CD pipeline lần cuối xác nhận tất cả job xanh.
  * Deploy thành công lên **AWS Amplify** (`d1s2bq5nqqwd9y`) và **GitHub Pages**.
  * Release Tag v1.0.0 được tạo trên GitHub với Release Notes đầy đủ.

* **Hoàn thành tài liệu kỹ thuật chuẩn kỹ sư phần mềm**:
  * `README.md`: thêm 5 badges (CI/CD, AWS Serverless, Python 3.12, React 18, License), phần giới thiệu tiếng Việt, tổ chức tính năng bằng `<details>` collapsible, bảng Lambda Functions chi tiết, hướng dẫn cài đặt từng bước đánh số(Deploy Backend ↁEFrontend ↁETests ↁESeed data), cấu trúc thư mục annotated, phần CI/CD & Bảo mật (OIDC, Dependabot).
  * `CLEANUP.md`: hướng dẫn dọn dẹp thủ công 19 tài nguyên AWS (Amplify, EventBridge, CloudWatch Alarms & Dashboard, SNS, API Gateway, Lambda x7, Lambda Layer, Cognito, Secrets Manager, SES, S3, DynamoDB, CloudWatch Logs, IAM Roles, KMS, OIDC Provider, CDK Stack, CDK Bootstrap) theo thứ tự tránh dependency error, kèm checklist xác nhận và bảng ước tính chi phí.

* **Setup Seed Data thành công cho Demo**:
  * Script `scripts/seed_data.py` tạo dữ liệu mẫu thực tế trên DynamoDB.
  * Luồng Demo end-to-end hoạt động trơn tru.

* **Hoàn thành Báo Cáo Tổng Kết**:
  * Phần Tổng quan Kiến trúc Serverless 6-layer: mô tả chi tiết từng layer và lý do lựa chọn.
  * Phần Quy trình DevOps (CI/CD GitHub Actions): OIDC, multi-job pipeline, automated testing, dual deployment S3+GitHub Pages.

* **Hỗ trợ chuẩn bộ Workshop FCJ** (First Cloud Journey): Cập nhật nội dung worklog, phân công công việc và tiến độcủa từng tuần vào tài liệu workshop của dự án.

* Dọn dẹp tài nguyên tạm thời: xóa file debug (`lambda_logs.json`, `response.json`...), chốt phiên bản cuối cùng trên GitHub repository.

---

### Tổng kết 12 tuần thực tập:

* **Tuần 1 E**: Nền tảng AWS Cloud  EVPC, Networking, DNS Hybrid, CloudFormation.
* **Tuần 5 E**: Compute & Storage  EEC2, EBS, EFS, FSx, S3, CloudFront, AWS Backup.
* **Tuần 9 E2**: Dự án SmartCV  EServerless Architecture, Lambda, DynamoDB, CI/CD, Observability.

> Qua 12 tuần thực tập tại **Amazon Web Services Việt Nam**, đã tích lũy được kiến thức và kinh nghiệm thực chiến về AWS Cloud từ cơ bản đến nâng cao, hoàn thành dự án **SmartCV** theo chuẩn kỹ sư phần mềm với kiến trúc Serverless hiện đại và quy trình DevOps chuyên nghiệp.
