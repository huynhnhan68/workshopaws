---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---


### Mục tiêu tuần 5:

* Nghiên cứu chuyên sâu về **Amazon EC2**: kiến trúc Nitro System, các loại chipset (AMD/Graviton), cơ chế Elasticity.
* Tìm hiểu **EC2 Auto Scaling** và các mô hình định giá: Reserved Instance (RI), On-Demand, Spot Instance.
* Nắm vững các giải pháp lưu trữ trên AWS: **EBS**, Instance Store, **EFS**, **FSx**, Lightsail, **AWS MGN**.
* Thực hành triển khai và quản lý EC2 instance với các loại storage phổ biến.

---

### Các công việc cần triển khai trong tuần này:

| STT | Thứ | Ngày | Công việc | Nguồn tài liệu |
| --- | --- | ---- | --------- | -------------- |
| 1 | Thứ 2 | 18/05/2026 | Nghiên cứu lý thuyết **Amazon EC2**: các loại Instance Family (General Purpose, Compute Optimized, Memory Optimized, Storage Optimized), chipset **AMD** và **AWS Graviton** (ARM-based), kiến trúc **AWS Nitro System** (hypervisor thế hệmới). Tìm hiểu các loại AMI (Amazon Machine Image). | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 2 | Thứ 3 | 19/05/2026 | Nghiên cứu **EC2 Auto Scaling**: Launch Template, Auto Scaling Group, Scaling Policies (Target Tracking, Step Scaling, Scheduled Scaling). Tìm hiểu và so sánh các mô hình giá: **On-Demand**, **Reserved Instance (RI)**  EStandard/Convertible, **Spot Instance**, **Savings Plans**. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 3 | Thứ 4 | 20/05/2026 | Nghiên cứu các giải pháp lưu trữ Block Storage: **Amazon EBS** (gp3, io2, st1, sc1) và **Instance Store** (ephemeral storage). So sánh use case: khi nào dùng EBS, khi nào dùng Instance Store. Thực hành tạo và gắn EBS Volume vào EC2 instance. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 4 | Thứ 5 | 21/05/2026 | Nghiên cứu các giải pháp lưu trữ File/Object: **Amazon EFS** (Elastic File System  ENFS managed), **Amazon FSx** (FSx for Windows File Server, FSx for Lustre), **Amazon Lightsail** (VPS đơn giản). Tìm hiểu **AWS Application Migration Service (MGN)** để di chuyển máy chủ On-premises lên AWS. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |
| 5 | Thứ 6 | 22/05/2026 | Thực hành tổng hợp: Tạo EC2 instance **t3.micro** (Free Tier), cấu hình Security Group, gắn EBS Volume, mount EFS vào instance, kiểm tra kết nối. Dọn dẹp tài nguyên. Viết worklog tổng kết tuần và so sánh ưu/nhược điểm các giải pháp storage. | [cloudjourney.awsstudygroup.com](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được tuần 5:

* Nắm vững kiến thức về **Amazon EC2**:
  * Các loại Instance Family và use case tương ứng.
  * Kiến trúc **AWS Nitro System** và lợi thế hiệu năng.
  * Ưu điểm của chipset **Graviton** (tiết kiệm chi phí ~40%).

* Hiểu rõ cơ chế **EC2 Auto Scaling** và cách thiết lập Scaling Policy phù hợp với từng loại workload.

* So sánh được ưu/nhược điểm các mô hình giá:
  * On-Demand: linh hoạt, không cam kết.
  * Reserved Instance: tiết kiệm đến 72% với cam kết 1-3 năm.
  * Spot Instance: tiết kiệm đến 90% cho workload fault-tolerant.

* Thực hành thành công với các giải pháp storage:
  * Tạo và gắn **EBS Volume** (gp3) vào EC2.
  * Mount **Amazon EFS** vào EC2 instance.
  * Hiểu được sự khác biệt giữa Block, File và Object Storage.

---

### Kế hoạch tuần tiếp theo:

* Hoàn thiện triển khai **Amazon S3** với Access Point, Gateway Endpoint và website tĩnh hỗ trợ CORS.
* Thiết lập cơ chế bảo vệdữ liệu: **S3 Versioning**, **Object Lock**, chuyển đổi Storage Class.
* Triển khai hệ thống sao lưu bằng **AWS Backup** và cấu hình **AWS Storage Gateway**.