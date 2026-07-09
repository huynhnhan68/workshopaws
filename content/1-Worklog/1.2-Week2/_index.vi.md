---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:

* Tìm hiểu và thực hành với **Amazon Virtual Private Cloud (VPC)**  Edịch vụ mạng ảo cốt lõi của AWS.
* Học cách thiết kế, triển khai và quản lý môi trường mạng riêng tư trên AWS Cloud.
* Cấu hình kết nối **Site-to-Site VPN** an toàn giữa hạ tầng On-premises và AWS Cloud.
* Nắm vững **Security Group**, **Network ACL**, **Internet Gateway**, **NAT Gateway**.
* Hiểu và thực hành **VPC Peering**, **Transit Gateway** và **Elastic Load Balancer**.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 27/04/2026 | Tìm hiểu kiến trúc mạng trên AWS: khái niệm **Amazon VPC**, CIDR block, Subnet (Public/Private), Availability Zone. Thực hành tạo VPC với Public Subnet và Private Subnet phân bổtrên nhiều AZ. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Thứ 3 | 28/04/2026 | Nghiên cứu và cấu hình **Security Group** (stateful firewall cho EC2) và **Network ACL** (stateless firewall cho Subnet) nhằm kiểm soát lưu lượng truy cập và tăng cường bảo mật hệ thống. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Thứ 4 | 29/04/2026 | Thiết lập **Internet Gateway** (cho Public Subnet), **NAT Gateway** (cho Private Subnet ra Internet), **Route Table** và tìm hiểu **VPC Endpoint** (truy cập S3/DynamoDB không qua Internet). Thực hành cấu hình **Site-to-Site VPN**. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thứ 5 | 30/04/2026 | Tìm hiểu **VPC Peering** (kết nối trực tiếp hai VPC), **Transit Gateway** (hub trung tâm kết nối nhiều VPC) và các phương thức kết nối hệ thống On-premises với AWS: **AWS VPN** và **AWS Direct Connect**. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 5 | Thứ 6 | 01/05/2026 | Thực hành **Elastic Load Balancer**: **ALB** (Application Load Balancer  ELayer 7), **NLB** (Network Load Balancer  ELayer 4), **GWLB** (Gateway Load Balancer  ELayer 3). Hoàn thiện Lab 03 về hạ tầng mạng AWS và viết worklog tổng kết tuần. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được tuần 2:

* Thiết lập thành công hệ thống mạng cơ bản trên AWS gồm:

  * 01 Amazon VPC với CIDR block phù hợp.
  * Các Public Subnet và Private Subnet phân bổtrên nhiều Availability Zones.

* Hoàn thành cấu hình các thành phần bảo mật:

  * Security Group cho EC2 với quy tắc Inbound/Outbound.
  * Network ACL cho các Subnet.

* Triển khai và cấu hình thành công:

  * Internet Gateway.
  * NAT Gateway.
  * Route Table.
  * VPC Endpoint cho S3.

* Hiểu rõ cơ chế định tuyến trong Amazon VPC và mối liên kết giữa các thành phần mạng.

* Nắm được nguyên lý hoạt động của:

  * VPC Peering.
  * Transit Gateway.
  * AWS VPN (Site-to-Site).
  * AWS Direct Connect.
  * VPC Endpoint.

* Thực hành dịch vụ Elastic Load Balancer, bao gồm:

  * Application Load Balancer (ALB).
  * Network Load Balancer (NLB).
  * Gateway Load Balancer (GWLB).

* Hiểu được vai trò của Load Balancer trong việc phân phối lưu lượng truy cập, nâng cao khả năng mở rộng và tính sẵn sàng của hệ thống.

---

### Kế hoạch tuần tiếp theo:

* Thực hành xây dựng hệ thống **DNS lai (Hybrid DNS)** tích hợp DNS On-premises với **Amazon Route 53**.
* Triển khai hạ tầng bằng **AWS CloudFormation**.
* Cấu hình **Inbound/Outbound Endpoint** và **Resolver Rules** cho Route 53.