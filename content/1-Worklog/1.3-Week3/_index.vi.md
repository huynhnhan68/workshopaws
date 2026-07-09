---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---


### Mục tiêu tuần 3:

* Xây dựng hệ thống **DNS lai (Hybrid DNS)** tích hợp giữa DNS On-premises và **Amazon Route 53**.
* Triển khai hạ tầng bằng **AWS CloudFormation** theo phương pháp Infrastructure as Code (IaC).
* Cấu hình **Inbound/Outbound Endpoint** và **Resolver Rules** cho Route 53 Resolver.
* Kiểm tra khả năng phân giải tên miền hai chiều giữa On-premises và AWS.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 04/05/2026 | Nghiên cứu tổng quan về **Amazon Route 53**: DNS Resolver, Private Hosted Zone, Public Hosted Zone. Tìm hiểu khái niệm **Hybrid DNS**  Etại sao cần tích hợp DNS On-premises với Route 53 trong môi trường Hybrid Cloud. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Thứ 3 | 05/05/2026 | Triển khai hạ tầng môi trường Lab bằng **AWS CloudFormation**: tạo stack, định nghĩa template YAML/JSON, hiểu cấu trúc Resources/Outputs/Parameters. Cấu hình VPC, Subnet, Security Group thông qua CloudFormation. | [docs.aws.amazon.com/cloudformation](https://docs.aws.amazon.com/cloudformation/) |
| 3 | Thứ 4 | 06/05/2026 | Tạo và cấu hình **Route 53 Inbound Endpoint**: cho phép DNS queries từ On-premises resolve vào AWS. Tạo **Route 53 Outbound Endpoint**: cho phép DNS queries từ AWS forward ra DNS server On-premises. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thứ 5 | 07/05/2026 | Thiết lập **Resolver Rules** (Forward Rules) đểđịnh tuyến DNS queries theo domain cụ thể Liên kết Resolver Rules với VPC tương ứng. Kiểm tra cấu hình DNS hai chiều bằng lệnh **nslookup** và **ping** từ EC2 instance. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 5 | Thứ 6 | 08/05/2026 | Kiểm thử toàn diện hệ thống Hybrid DNS: xác nhận phân giải tên miền hoạt động đúng theo cả hai chiều. Dọn dẹp tài nguyên sau Lab để tránh phát sinh chi phí. Viết worklog tổng kết tuần và ghi chú các lesson learned. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được tuần 3:

* Hiểu rõ kiến trúc **Hybrid DNS** và lý do cần tích hợp giữa DNS On-premises và Amazon Route 53.

* Triển khai thành công hạ tầng Lab bằng **AWS CloudFormation**, nắm được quy trình IaC cơ bản:
  * Viết template CloudFormation định nghĩa VPC, Subnet, Security Group.
  * Tạo và quản lý CloudFormation Stack.

* Cấu hình thành công **Route 53 Resolver**:
  * Inbound Endpoint: nhận DNS queries từ On-premises vào AWS.
  * Outbound Endpoint: forward DNS queries từ AWS ra On-premises.
  * Resolver Rules: định tuyến DNS theo domain cụ thể

* Kiểm tra thành công phân giải tên miền hai chiều bằng **nslookup** và **ping**.

* Dọn dẹp tài nguyên sau Lab, không để lại chi phí phát sinh.

---

### Kế hoạch tuần tiếp theo:

* Tối ưu **VPC Peering** (Route Table, Cross-Peer DNS) và triển khai **AWS Transit Gateway** cho 4 VPC.
* Thực hành **Infrastructure as Code** bằng CloudFormation + Application Composer.
* Sử dụng **Reachability Analyzer** để xử lý sự cố mạng và thiết lập **Bastion Host**.