---
title: "Amazon Bedrock"
date: 2026-07-09
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

Amazon Bedrock là dịch vụ AI tạo sinh (Generative AI) được SmartCV dùng để phân tích nội dung CV/hồ sơ ứng tuyển và đưa ra gợi ý cải thiện (thông qua Lambda `smartcv-insights` và `smartcv-digest`). Model được chọn cho dự án là **Amazon Nova Lite** (`amazon.nova-lite-v1:0`)  Etối ưu chi phí và có sẵn ở region `ap-southeast-1`.

{{% notice warning %}}
**Bước bắt buộc trước khi test Lambda:** Amazon Bedrock yêu cầu **Enable Model Access** ở console riêng cho từng model, **tách biệt hoàn toàn** với quyền IAM. Dù Lambda Role đã có `AmazonBedrockFullAccess`, nếu model chưa được Enable ở bước này, mọi lời gọi API sẽ trả vềlỗi `AccessDeniedException`. Hãy làm bước này **trước khi** cấu hình Lambda ở mục [5.5](../5.5-lambda/).
{{% /notice %}}

#### Bước 1: Enable Model Access

1. Truy cập dịch vụ **Amazon Bedrock** trên AWS Console, đảm bảo đang ở region `ap-southeast-1` (hoặc region hỗ trợ Nova Lite mà bạn dùng xuyên suốt Workshop).
2. ở menu bên trái, chọn **Model access** (nằm trong phần Bedrock configurations).
3. Click **Modify model access** (hoặc **Manage model access**, tuỳ phiên bản UI).
4. Tìm đến model **Amazon Nova Lite**, tích chọn checkbox bên cạnh.
5. Cuộn xuống, đọc và chấp nhận điều khoản sử dụng (End User License Agreement) nếu được yêu cầu.
6. Click **Request model access** (hoặc **Save changes**).

![Enable Model Access cho Amazon Nova Lite](/images/5-Workshop/5.10-Bedrock/enable-model-access.png)

7. Đợi vài giây đến vài phút, trạng thái model sẽ chuyển từ *Available to request* ↁE**Access granted**.

![Model đã được cấp quyền truy cập](/images/5-Workshop/5.10-Bedrock/access-granted.png)

#### Bước 2: Thử nghiệm model trên Playground (tuỳ chọn, khuyến nghở 

Trước khi tích hợp vào Lambda, nên thử model trực tiếp đểhiểu định dạng input/output:

1. Menu bên trái Bedrock, chọn **Playgrounds** ↁE**Chat / Text**.
2. Chọn model **Amazon Nova Lite**.
3. Thử nhập một đoạn CV mẫu và một prompt phân tích, ví dụ:

```
Bạn là một chuyên gia tuyển dụng. Hãy phân tích CV sau và đưa ra 3 điểm mạnh,
2 điểm cần cải thiện, viết ngắn gọn dưới 150 từ, trả lời bằng tiếng Việt.

CV: <dán nội dung CV mẫu vào đây>
```

4. Quan sát kết quả trả vềđểtinh chỉnh prompt trước khi đưa vào code Lambda.

![Thử nghiệm trên Bedrock Playground](/images/5-Workshop/5.10-Bedrock/playground-test.png)

#### Bước 3: Lấy Model ID đểcấu hình Lambda

Model ID cần dùng cho biến môi trường `BEDROCK_MODEL_ID` (đã cấu hình ở mục [5.5](../5.5-lambda/)) là:

```
amazon.nova-lite-v1:0
```

Bạn có thểxác nhận lại chính xác Model ID này ở trang **Model catalog** trong Bedrock Console, mục thông tin chi tiết của Amazon Nova Lite.

#### Kiểm tra nhanh sau khi tích hợp

Sau khi Lambda `smartcv-insights` hoặc `smartcv-digest` đã được deploy code và cấu hình đầy đủ biến môi trường, hãy test trực tiếp hàm Lambda đó (tab **Test** trên Lambda Console) với một payload mẫu. Nếu vẫn gặp lỗi `AccessDeniedException`, kiểm tra lại theo thứ tự:
1. Model access đã ở trạng thái *Access granted* chưa (mục 5.10 này).
2. Region của Lambda và Region Enable Model Access có khớp nhau không.
3. IAM Role gắn cho Lambda có policy `AmazonBedrockFullAccess` chưa (mục 5.5).
