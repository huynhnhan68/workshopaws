---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Mục tiêu tuần 7:

* Triển khai hệ thống sao lưu tự động với **AWS Backup** nâng cao và kiểm thử quy trình khôi phục.
* Cấu hình hoàn chỉnh **AWS Storage Gateway** (File Gateway) để hỗ trợ chia sẻ tệp qua SMB và lưu trữ lên S3.
* Triển khai **website tĩnh trên S3 + CloudFront** với tối ưu hóa tốc độvà bảo mật.
* Bật **S3 Cross-Region Replication (CRR)** để đảm bảo Disaster Recovery.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 01/06/2026 | Triển khai hệ thống sao lưu tự động nâng cao với **AWS Backup**: tạo Backup Vault, cấu hình Backup Plan chi tiết (daily/weekly/monthly), thiết lập retention policy. Kiểm thử thành công quy trình khôi phục EC2 và EBS từ Recovery Point. Thiết lập cảnh báo trạng thái backup ổn định qua **AWS SNS**. | [docs.aws.amazon.com/aws-backup](https://docs.aws.amazon.com/aws-backup/) |
| 2 | Thứ 3 | 02/06/2026 | Cấu hình hoàn chỉnh **AWS Storage Gateway** (File Gateway): upload/download file qua giao thức **SMB** từ Windows client, kiểm tra dữ liệu được đồng bộlên S3 bucket, cấu hình Cache storage để tối ưu hiệu suất. Thực hành các thao tác quản lý Gateway qua AWS Console. | [docs.aws.amazon.com/storagegateway](https://docs.aws.amazon.com/storagegateway/) |
| 3 | Thứ 4 | 03/06/2026 | Hoàn thiện triển khai **website tĩnh trên S3 + CloudFront**: cấu hình **Origin Access Control (OAC)** để chặn quyền truy cập trực tiếp vào S3 (chỉ cho phép qua CloudFront), thiết lập **CloudFront Cache Behaviors**, cấu hình **Custom Error Pages** và **HTTPS** (SSL/TLS Certificate qua ACM). | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thứ 5 | 04/06/2026 | Bật và kiểm thử **S3 Versioning** nâng cao: cấu hình **MFA Delete** để bảo vệobjects quan trọng, thực hành khôi phục object đã xóa từ previous version. Cấu hình **S3 Cross-Region Replication (CRR)**: tạo Replication Rule, chọn destination region, kiểm tra dữ liệu được replicate sang region dự phòng. | [docs.aws.amazon.com/s3](https://docs.aws.amazon.com/s3/) |
| 5 | Thứ 6 | 05/06/2026 | Kiểm thử toàn diện hệ thống: xác nhận website tĩnh hoạt động qua CloudFront URL, kiểm tra Cross-Region Replication, xác nhận backup và restore hoạt động đúng. Dọn dẹp tài nguyên không cần thiết. Viết worklog tổng kết tuần và ghi chú kinh nghiệm rút ra. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được tuần 7:

* Triển khai thành công hệ thống sao lưu tự động với **AWS Backup**:
  * Backup Vault với encryption.
  * Backup Plan với lịch daily backup và 30-day retention.
  * Kiểm thử Restore EC2/EBS từ Recovery Point thành công.
  * Nhận cảnh báo backup qua SNS email notification.

* Cấu hình thành công **AWS Storage Gateway** (File Gateway):
  * Chia sẻ tệp qua giao thức SMB từ Windows client.
  * Dữ liệu tự động đồng bộlên S3 bucket.

* Hoàn thiện website tĩnh trên **S3 + CloudFront**:
  * Origin Access Control (OAC): chặn quyền truy cập S3 trực tiếp.
  * HTTPS với SSL Certificate (ACM).
  * CloudFront Cache Behaviors tối ưu.

* Bật thành công **S3 Cross-Region Replication (CRR)**:
  * Dữ liệu tự động replicate sang region dự phòng (ap-southeast-2).
  * Kiểm thử khôi phục từ region dự phòng.

---

### Kế hoạch tuần tiếp theo:

* Thực hành nâng cao **Amazon FSx**: Multi-AZ, SSD/HDD, file share, shadow copies, storage quota.
* Triển khai và vận hành hệ thống FSx, đo lường và theo dõi các chỉ sốhiệu suất.
* Kích hoạt và kiểm thử **S3 Versioning** toàn diện.
* Bắt đầu tìm hiểu sơ đồ kiến trúc AWS cho dự án nhóm **SmartCV  EAgainst The Wind**.