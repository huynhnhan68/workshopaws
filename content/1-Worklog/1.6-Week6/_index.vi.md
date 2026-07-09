---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Mục tiêu tuần 6:

* Hoàn thiện triển khai **Amazon S3** đa chức năng: Access Point, Gateway Endpoint, website tĩnh hỗ trợ CORS.
* Thiết lập cơ chế bảo vệdữ liệu trên S3: **Versioning**, **Object Lock**, chuyển đổi sang S3 Glacier.
* Vận hành hệ thống sao lưu định kỳ bằng **AWS Backup** và kết nối lưu trữ lai qua **AWS Storage Gateway**.
* Khởi tạo và cấu hình cơ bản **Amazon FSx for Windows File Server**.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 25/05/2026 | Triển khai **Amazon S3 Bucket** đa chức năng: tạo S3 Bucket, cấu hình **S3 Access Point** để kiểm soát truy cập chi tiết theo ứng dụng, thiết lập **Gateway Endpoint** (VPC Endpoint cho S3) để các EC2 trong Private Subnet truy cập S3 an toàn mà không qua Internet. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Thứ 3 | 26/05/2026 | Thiết lập **S3 Static Website Hosting** hỗ trợ **CORS** (Cross-Origin Resource Sharing): upload file HTML/CSS/JS, cấu hình Bucket Policy cho phép public read, cấu hình CORS policy, truy cập website qua S3 endpoint URL. Cấu hình **CloudFront** distribution trỏ vào S3 để tăng tốc độvà bảo mật. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Thứ 4 | 27/05/2026 | Thiết lập cơ chế bảo vệdữ liệu trên S3: bật **S3 Versioning** để chống ghi đè và xóa nhầm, cấu hình **S3 Object Lock** (WORM  EWrite Once Read Many) để tuân thủ quy định lưu trữ, thiết lập **Lifecycle Rules** để tự động chuyển đổi objects sang S3 Glacier/Glacier Deep Archive nhằm tối ưu chi phí. | [docs.aws.amazon.com/s3](https://docs.aws.amazon.com/s3/) |
| 4 | Thứ 5 | 28/05/2026 | Vận hành hệ thống sao lưu tự động bằng **AWS Backup**: tạo Backup Plan với lịch backup định kỳ, gán Resource (EC2, EBS, RDS) vào Backup Plan, kiểm thử quy trình khôi phục (Restore) từ backup point. Thiết lập cảnh báo trạng thái backup qua **Amazon SNS**. | [docs.aws.amazon.com/aws-backup](https://docs.aws.amazon.com/aws-backup/) |
| 5 | Thứ 6 | 29/05/2026 | Khởi tạo và cấu hình **AWS Storage Gateway** (File Gateway mode) để kết nối lưu trữ Hybrid: cài đặt Storage Gateway Appliance trên máy ảo, cấu hình kết nối với S3, tạo File Share qua giao thức SMB/NFS. Khởi tạo cơ bản **Amazon FSx for Windows File Server**. Viết worklog tổng kết tuần. | [docs.aws.amazon.com/storagegateway](https://docs.aws.amazon.com/storagegateway/) |

---

### Kết quả đạt được tuần 6:

* Hoàn thiện triển khai **Amazon S3** đa chức năng:
  * S3 Access Point kiểm soát quyền truy cập theo từng ứng dụng.
  * Gateway Endpoint (VPC Endpoint cho S3) cho phép EC2 trong Private Subnet truy cập S3 an toàn.
  * Static Website Hosting với CORS policy và tích hợp CloudFront.

* Thiết lập thành công cơ chế bảo vệdữ liệu:
  * S3 Versioning: lưu trữ nhiều phiên bản của từng object.
  * S3 Object Lock: chống xóa/chỉnh sửa không được phép.
  * Lifecycle Rules: tự động chuyển objects sang Glacier để tiết kiệm chi phí.

* Vận hành thành công hệ thống sao lưu định kỳ với **AWS Backup**:
  * Tạo Backup Plan với lịch backup theo cron expression.
  * Kiểm thử quy trình Restore từ Recovery Point thành công.
  * Cảnh báo trạng thái backup qua SNS.

* Khởi tạo và cấu hình cơ bản **AWS Storage Gateway** (File Gateway):
  * Kết nối thành công với S3 bucket.
  * Tạo File Share qua giao thức SMB.

* Khởi tạo ban đầu **Amazon FSx for Windows File Server**.

---

### Kế hoạch tuần tiếp theo:

* Triển khai hệ thống sao lưu tự động với **AWS Backup** nâng cao và kiểm thử khôi phục.
* Cấu hình **AWS Storage Gateway** để hỗ trợ chia sẻ tệp qua SMB và lưu trữ dữ liệu lên S3.
* Triển khai **website tĩnh trên S3 + CloudFront** và bật **S3 Cross-Region Replication** cho Disaster Recovery.