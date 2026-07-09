---
title: "Amazon EventBridge"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

EventBridge dùng để tự động chạy Lambda theo lịch, ví dụ gửi Weekly Digest hằng tuần hoặc kiểm tra các hồ sơ cần nhắc Follow-up.

#### Tạo Schedule gửi email Follow-up hằng ngày

1. Truy cập dịch vụ **Amazon EventBridge** trên AWS Console.
2. Menu bên trái chọn **Scheduler** ↁE**Schedules**.
3. Nhấn **Create schedule**.
4. **Schedule name:** nhập `smartcv-daily-followup`.
5. Chọn **Recurring schedule**.
6. **Time zone:** chọn **Asia/Saigon (UTC+07:00)**.
7. **Schedule type:** chọn **Cron-based schedule**.
8. Nhập Cron Expression: `0 9 * * ? *`

{{% notice note %}}
Vì Time zone đã được chọn là **Asia/Saigon**, các giá trở giở trong cron expression được hiểu theo **giở địa phương Việt Nam**, không phải UTC. `0 9 * * ? *` = **09:00 sáng mỗi ngày theo giở Việt Nam** (không phải 2 giở sáng  Eđây là lỗi thường gặp khi nhầm giữa giở UTC và giở local sau khi đã chọn Time zone).
{{% /notice %}}

![Tạo Schedule Follow-up](/images/5-Workshop/5.8-EventBridge/5.48.png)

9. Nhấn **Next**.
10. ở phần **Target API**, chọn **AWS Lambda** ↁE**Invoke**.
11. **Lambda function:** chọn `smartcv-followup`, nhấn **Next**.
12. Nhấn **Create schedule** đểhoàn tất.

![Hoàn tất Schedule](/images/5-Workshop/5.8-EventBridge/5.49.png)

#### Tạo Schedule gửi email tổng kết hàng tuần

1. Chọn **Create schedule** một lần nữa.
2. **Schedule name:** nhập `smartcv-weekly-digest`.
3. Chọn **Recurring schedule**.
4. **Time zone:** chọn **Asia/Saigon (UTC+07:00)**.
5. Chọn **Cron-based schedule**.
6. Nhập Cron Expression: `cron(0 8 ? * MON *)`  Etương ứng **08:00 sáng Thứ Hai** hàng tuần theo giở Việt Nam.
7. Nhấn **Next** ↁEchọn **AWS Lambda** ↁE**Invoke**. **Lambda function:** chọn `smartcv-digest`.
8. Nhấn **Next**.
9. Nhấn **Create schedule**.

![Tạo Schedule Weekly Digest](/images/5-Workshop/5.8-EventBridge/5.50.png)

Cả hai Schedule **Weekly Digest** và **Daily Followup** đã được tạo thành công.

![Danh sách Schedules](/images/5-Workshop/5.8-EventBridge/5.52.png)
