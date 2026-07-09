---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---


### Mục tiêu tuần 8:

* Thực hành nâng cao **Amazon FSx for Windows File Server**: Multi-AZ, SSD/HDD, file share, shadow copies, storage quota.
* Triển khai và vận hành các cụm FSx dự phòng, đo lường và theo dõi các chỉ sốhiệu suất.
* Kích hoạt và kiểm thử toàn diện **S3 Versioning**.
* Bắt đầu tìm hiểu và vẽ sơ đồ kiến trúc AWS cho dự án nhóm **Against The Wind  ESmartCV**.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 08/06/2026 | Tìm hiểu **Amazon FSx for Windows File Server** nâng cao: so sánh Single-AZ và **Multi-AZ** deployment, so sánh **SSD** (high IOPS) và **HDD** (cost-efficient). Tạo FSx Multi-AZ file system với cấu hình SSD, thiết lập kết nối từ Windows EC2 instance. | [docs.aws.amazon.com/fsx](https://docs.aws.amazon.com/fsx/) |
| 2 | Thứ 3 | 09/06/2026 | Cấu hình nâng cao FSx: tạo và quản lý **File Share** (SMB shares), cấu hình **Storage Quota** cho từng user/group, bật tính năng **Shadow Copies** (VSS  EVolume Shadow Copy Service) để tự động tạo snapshot file định kỳ. Kiểm thử khôi phục file từ Shadow Copy. | [docs.aws.amazon.com/fsx](https://docs.aws.amazon.com/fsx/) |
| 3 | Thứ 4 | 10/06/2026 | Đo lường và theo dõi **hiệu suất FSx**: sử dụng **Amazon CloudWatch** để xem metrics (DataReadBytes, DataWriteBytes, NetworkThroughput, StorageCapacityUtilization), tạo Dashboard theo dõi hiệu suất. Thực hành thêm cụm FSx HDD và so sánh kết quả hiệu năng với SSD. | [docs.aws.amazon.com/cloudwatch](https://docs.aws.amazon.com/cloudwatch/) |
| 4 | Thứ 5 | 11/06/2026 | Kích hoạt và kiểm thử toàn diện **S3 Versioning**: upload nhiều phiên bản của cùng một object, liệt kê tất cả versions, khôi phục object về version cụ thể xóa Delete Marker, so sánh hành vi Bucket với/không có Versioning. | [docs.aws.amazon.com/s3](https://docs.aws.amazon.com/s3/) |
| 5 | Thứ 6 | 12/06/2026 | Bắt đầu tìm hiểu và vẽ sơ đồ kiến trúc AWS cho dự án nhóm **Against The Wind** về "**Hệ thống theo dõi và tối ưu hóa hồ sơ xin việc ứng dụng trí tuệnhân tạo (AI)  ESmartCV**": xác định các dịch vụ AWS sử dụng (Lambda, DynamoDB, S3, Bedrock, Cognito, API Gateway), phác thảo High-Level Architecture Diagram. Dọn dẹp tài nguyên FSx. Viết worklog tổng kết. | [draw.io](https://draw.io/) |

---

### Kết quả đạt được tuần 8:

* Thực hành thành công **Amazon FSx for Windows File Server** nâng cao:
  * Khởi tạo thành công cụm lưu trữ dự phòng **Multi-AZ** (SSD và HDD).
  * Cấu hình File Share, chia sẻ tài nguyên thành công từ Windows client.
  * Bật và kiểm thử **Shadow Copies**  Ekhôi phục file từ snapshot.
  * Cấu hình **Storage Quota** cho từng user.

* Đo lường và theo dõi thành công các **chỉ sốhiệu suất FSx** qua CloudWatch:
  * Tạo CloudWatch Dashboard theo dõi IOPS, Throughput, Storage Utilization.
  * So sánh hiệu năng SSD vs HDD trong thực tế.

* Kích hoạt và kiểm thử thành công **S3 Versioning**:
  * Quản lý nhiều phiên bản object.
  * Khôi phục object về version mong muốn.

* Bắt đầu phác thảo sơ đồ kiến trúc AWS cho dự án **SmartCV**:
  * Xác định các dịch vụ AWS cần sử dụng.
  * Phác thảo High-Level Architecture Diagram.

---

### Kế hoạch tuần tiếp theo:

* Định hình chính thức đề tài **SmartCV** (AI-Powered Job Tracker) và lựa chọn kiến trúc **Serverless**.
* Phân công công việc cho 4 thành viên nhóm **Against The Wind**.
* Thiết kế kiến trúc 6 lớp: Presentation ↁERouting ↁECompute ↁECore ↁEData ↁEExternal.
* Thiết kế luồng sự kiện **Event-Driven Architecture** với EventBridge và Cognito.