---
title: "Amazon Cognito"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

Amazon Cognito đóng vai trò xác thực người dùng (đăng ký, đăng nhập) cho SmartCV, phát hành JWT token đểFrontend gọi API an toàn.

1. Trong AWS Management Console, gõ **Cognito** trong ô tìm kiếm và nhấn Enter.
2. Nhấn **Create user pool**. ở mục **Option for sign-in identifiers**, click chọn **Email**.
3. Các mục còn lại đểmặc định, đặt tên user pool là `smartcv-users`.

![Tạo User Pool](/images/5-Workshop/5.4-Cognito/5.8.png)
**Hình 5.4.1**  ETạo User Pool `smartcv-users` với sign-in bằng Email.

#### Lấy thông tin cấu hình cho Frontend

Sau khi tạo xong, cần lấy các thông sở đểcấu hình React Frontend sau này:

1. Click vào User pool `smartcv-users` vừa tạo.
2. Tại trang tổng quan, sao chép **User pool ID** (ví dụ: `ap-southeast-1_xxxxxxxxx`) và lưu ra file nháp.
3. Chuyển sang tab **App integration**.
4. Cuộn xuống phần **App client list**, sao chép **Client ID** của `smartcv-frontend` và lưu ra nháp.

![Lấy thông tin User Pool ID và Client ID](/images/5-Workshop/5.4-Cognito/5.9.png)
**Hình 5.4.2**  ESao chép User pool ID và Client ID đểcấu hình Frontend.
