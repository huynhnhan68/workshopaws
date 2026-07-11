
---
title: "Event 3"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Tech Talk & Certification Insights
### Khởi động bằng mà đọ tài chung kết giữa 2 team AWS Cloud Achitect

### Mục Đích Của Sự Kiện

- Hiểu rõ hơn về các giải pháp bảo mật tự động trên AWS và cách tối ưu hóa quy trình bảo mật.
- Nắm bắt tư duy đúng đắn về SLA và chiến lược giám sát hệ thống (Monitoring) hiệu quả trong môi trường Cloud.
- Trang bị kiến thức, kinh nghiệm và chiến lược ôn thi chứng chỉ AWS Cloud Practitioner một cách tối ưu nhất.

### Danh Sách Diễn giả

- **Anh Thịnh Nguyễn** - DevOps/DevSecOps/Cloud Engineer tại Styl Solutions
- **Anh Nguyễn Huỳnh Sơn** 
- **Ngô Lê Tấn Huy**

### Nội Dung Nổi Bật

### 1. Diễn giả Anh Thịnh Nguyễn - DevOps/DevSecOps/Cloud Engineer tại Styl Solutions

**Chủ đề:** *Securing Your Web Apps With AWS Security Agent*
**Dịch:** *Bảo mật ứng dụng Web của bạn với AWS Security Agent*

Anh Thịnh Nguyễn chia sẻ về các thách thức trong quy trình bảo mật truyền thống, đặc biệt là sự thiếu hụt khả năng phản ứng theo thời gian thực và độ trễ cao khi xử lý các sự cố bảo mật. Để giải quyết vấn đề này, anh đã giới thiệu giải pháp sử dụng **AWS Security Agent** với những khả năng tự động hóa vô cùng mạnh mẽ, bao gồm: Security Review, Code Review và Automated Pentesting. Việc áp dụng tự động hóa giúp đội ngũ phát hiện và ngăn chặn các lỗ hổng từ sớm.

Tuy nhiên, phần trình bày cũng đi sâu vào các hạn chế kỹ thuật khi triển khai thực tế. Cụ thể, người dùng cần lưu ý đến các điểm yếu về **Authentication Blocks** (các cơ chế xác thực tùy chỉnh thường dễ bị bypass nếu không cấu hình kỹ), **Logic Flaws** (những lỗ hổng logic nghiệp vụ mà các công cụ quét tự động rất khó phát hiện) và **Task-hour Accumulation** (bài toán tối ưu chi phí tài nguyên khi quét bảo mật ở quy mô lớn).

**Kết quả hoặc giá trị đạt được:**
Qua phần chia sẻ này, em nhận thấy tầm quan trọng của việc tự động hóa bảo mật trong kỷ nguyên Cloud. Đồng thời, em cũng học được cách nhìn nhận hệ thống dưới góc độ DevSecOps, hiểu rằng công cụ tự động hóa không phải là "chìa khóa vạn năng" mà cần sự kiểm soát chặt chẽ của con người ở các khâu logic phức tạp.

---

### 2. Diễn giả Anh Nguyễn Huỳnh Sơn - SLY and Monitoring 

**Chủ đề:** *From SLA to Monitoring: What Really Matters*
**Dịch:** *Từ SLA đến Giám sát hệ thống: Điều gì thực sự quan trọng*

Anh Nguyễn Huỳnh Sơn mang đến một góc nhìn rất cốt lõi về **SLA (Service Level Agreement)** và định vị **Monitoring (Giám sát hệ thống)** không chỉ là một công việc kỹ thuật, mà nằm trong toàn bộ quy trình quản trị rủi ro (Risk Management) của doanh nghiệp. Anh giới thiệu một lộ trình quản trị rõ ràng: **Identify Risk → Monitor Signals → Respond → Improve**.

Đặc biệt, anh chia sẻ về **Chiến lược Monitoring theo mô hình Kim tự tháp ngược**. Theo đó, thay vì chỉ chăm chăm giám sát hạ tầng, chúng ta cần tập trung tài nguyên theo thứ tự ưu tiên từ cao xuống thấp: **Customer Journey** (Trải nghiệm khách hàng) ⭢ **Business Metrics** (Chỉ số kinh doanh) ⭢ **Application** (Ứng dụng) ⭢ **Infrastructure** (Hạ tầng) ⭢ **AWS Services** (Dịch vụ nền tảng). Điều này đảm bảo rằng hệ thống giám sát đang thực sự bảo vệ giá trị kinh doanh.

**Kết quả hoặc giá trị đạt được:**
Phần trình bày giúp em thay đổi tư duy từ việc "giám sát server có chết hay không" sang việc "giám sát trải nghiệm của khách hàng có bị ảnh hưởng hay không". Tư duy kim tự tháp ngược là một kim chỉ nam tuyệt vời để thiết lập hệ thống cảnh báo (alert) sao cho hiệu quả, tránh bị nhiễu thông tin (alert fatigue) trong các dự án thực tế.

---

### 3. Diễn giả Ngô Lê Tấn Huy

**Chủ đề:** *Inside The Exam: AWS Cloud Practitioner*
**Dịch:** *Bên trong kỳ thi: AWS Cloud Practitioner*

Diễn giả Ngô Lê Tấn Huy cung cấp một bức tranh toàn cảnh về lộ trình 4 cấp độ chứng chỉ của AWS, sau đó đi sâu vào cấu trúc và các nội dung cốt lõi của kỳ thi **AWS Cloud Practitioner**. Những mảng kiến thức trọng tâm cần nắm vững bao gồm: Cloud Concepts, Security & Compliance, Technology, và Billing/Pricing/Support.

Không chỉ nói về lý thuyết, anh còn chia sẻ các "tips" ôn thi vô cùng hiệu quả, được đúc kết từ kinh nghiệm thực tế. Các phương pháp như **Mapping Keywords** (liên kết nhanh từ khóa với dịch vụ AWS tương ứng) và **Review Mistakes** (phân tích kỹ nguyên nhân các câu hỏi làm sai) giúp tối ưu thời gian học. Anh cũng đặc biệt nhấn mạnh về **Mindset** khi đi thi: tránh suy diễn quá đà (Don't overthink) và cần cẩn trọng với các **Language Pitfalls** (bẫy ngôn ngữ) thường gặp trong đề thi.

**Kết quả hoặc giá trị đạt được:**
Những chia sẻ của anh Huy như một bản "hướng dẫn sinh tồn" quý giá cho những ai đang chuẩn bị thi chứng chỉ AWS đầu tiên. Em học được cách học và ôn thi thông minh hơn, cũng như cách chuẩn bị tâm lý vững vàng để vượt qua các bẫy trắc nghiệm của bài thi.

---

#### Một số hình ảnh khi tham gia sự kiện

![Event 3.1](/images/4-EventParticipated/3.1.jpg)
![Event 3.2](/images/4-EventParticipated/3.2.jpg)
![Event 3.3](/images/4-EventParticipated/3.3.jpg)
![Event 3.4](/images/4-EventParticipated/3.4.jpg)
![Event 3.5](/images/4-EventParticipated/3.5.jpg)
![Event 3.6](/images/4-EventParticipated/3.6.jpg)
![Event 3.7](/images/4-EventParticipated/3.7.jpg)
