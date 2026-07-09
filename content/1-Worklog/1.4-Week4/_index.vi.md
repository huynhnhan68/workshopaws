---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Mục tiêu tuần 4:

* Tối ưu hóa kiến trúc **VPC Peering** với Route Table và Cross-Peer DNS Resolution.
* Triển khai **AWS Transit Gateway** kết nối 4 VPC trong một kiến trúc Hub-and-Spoke.
* Thực hành **Infrastructure as Code** bằng **AWS CloudFormation** và **Application Composer**.
* Sử dụng **VPC Reachability Analyzer** để phân tích và xử lý sự cố mạng.
* Thiết lập **Bastion Host** để quản lý an toàn các máy chủ trong Private Subnet.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 11/05/2026 | Tối ưu **VPC Peering**: cấu hình Route Table cho phép lưu lượng đi qua Peering Connection, bật tính năng **DNS Resolution** (Cross-Peer DNS) để các EC2 instance giao tiếp với nhau bằng tên DNS thay vì IP. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Thứ 3 | 12/05/2026 | Triển khai **AWS Transit Gateway** cho 4 VPC theo mô hình Hub-and-Spoke: tạo Transit Gateway, tạo Transit Gateway Attachment cho từng VPC, cấu hình Route Table Transit Gateway và kiểm tra kết nối liên VPC. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Thứ 4 | 13/05/2026 | Thực hành **Infrastructure as Code** với **AWS CloudFormation** nâng cao: sử dụng **Application Composer** để thiết kế kiến trúc bằng giao diện đồ họa và tự động sinh CloudFormation template. Triển khai stack và kiểm tra kết quả. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thứ 5 | 14/05/2026 | Sử dụng **VPC Reachability Analyzer** để phân tích khả năng kết nối giữa các tài nguyên mạng: tạo phân tích giữa nguồn và đích, đọc kết quả và xác định nguyên nhân sự cố(Security Group, Route Table, NACL). Thực hành xử lý các lỗi mạng phổ biến. | [docs.aws.amazon.com](https://docs.aws.amazon.com/vpc/latest/reachability/) |
| 5 | Thứ 6 | 15/05/2026 | Thiết lập **Bastion Host** (Jump Server) trên Public Subnet: tạo EC2 instance, cấu hình Security Group cho phép SSH từ IP được phép, thực hành kết nối SSH multi-hop vào EC2 trong Private Subnet thông qua Bastion. Viết worklog tổng kết tuần. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được tuần 4:

* Tối ưu thành công kiến trúc **VPC Peering**:
  * Cấu hình Route Table hai chiều giữa các VPC.
  * Bật DNS Resolution qua Peering Connection, các hệ thống giao tiếp bằng tên thay vì IP.

* Triển khai thành công **AWS Transit Gateway** kết nối 4 VPC:
  * Tạo Transit Gateway và các Attachment.
  * Cấu hình Transit Gateway Route Table.
  * Xác nhận kết nối thành công giữa tất cả VPC.

* Nắm vững quy trình **Infrastructure as Code** bằng CloudFormation + Application Composer.

* Sử dụng thành thạo **VPC Reachability Analyzer** để phân tích và xử lý sự cố mạng.

* Thiết lập thành công **Bastion Host** và kết nối SSH vào EC2 trong Private Subnet qua Jump Server.

---

### Kế hoạch tuần tiếp theo:

* Nghiên cứu lý thuyết **Amazon EC2**: Elasticity, chipset AMD/Graviton, hệ thống Nitro.
* Tìm hiểu **Auto Scaling** và các mô hình giá: Reserved Instance, On-Demand, Spot.
* Nghiên cứu giải pháp lưu trữ: **EBS**, Instance Store, **EFS**, **FSx**, Lightsail, **AWS MGN**.