---
title: "Tuần 3: AWS Lambda và xử lý ảnh bất đồng bộ (18/05/2026 - 22/05/2026)"
menuTitle: "Tuần 3"
date: 2026-07-24
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Mục tiêu tuần 3:**

- Tìm hiểu AWS Lambda và cách viết hàm Python xử lý message từ SQS.
- Thực hành xây dựng Lambda function đọc thông tin ảnh từ SQS và S3.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Tìm hiểu AWS Lambda: Function, Trigger, Runtime, Layer, Execution Role. Tìm hiểu mô hình tính phí. | 18/05/2026 | 18/05/2026 | https://docs.aws.amazon.com/lambda/ |
| 3 | Chuẩn bị IAM Role cho Lambda (Lambda-ImageProcessing-Role): AWSLambdaBasicExecutionRole, AmazonS3ReadOnlyAccess, AmazonSQSFullAccess, AmazonRekognitionFullAccess, AmazonTextractFullAccess. | 19/05/2026 | 19/05/2026 | https://docs.aws.amazon.com/IAM/ |
| 4 | Thực hành tạo Lambda Function (image-quality-processor, Python 3.x). Cấu hình Timeout = 60 giây, Memory = 512 MB. Gắn SQS làm Trigger với Batch size = 1. | 20/05/2026 | 20/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 5 | Viết code Python xử lý SQS message: Parse SQS record lấy bucket name và object key từ S3 event. Ghi log ra CloudWatch. Deploy và kiểm thử. | 21/05/2026 | 21/05/2026 | https://docs.aws.amazon.com/lambda/ |
| 6 | Kiểm tra CloudWatch Logs sau khi upload ảnh. Debug lỗi kết nối. Dọn dẹp tài nguyên test sau kiểm thử. | 22/05/2026 | 22/05/2026 | |

**Kết quả đạt được tuần 3:**

- Hiểu cách hoạt động của AWS Lambda và mô hình tính phí.
- Tạo thành công IAM Role theo nguyên tắc Least Privilege cho Lambda.
- Tạo và cấu hình Lambda Function với SQS Trigger, Batch size = 1.
- Viết thành công code Python xử lý SQS message, đọc thông tin ảnh từ S3 và ghi log ra CloudWatch.
- Kiểm thử và debug thành công toàn bộ luồng S3 → SQS → Lambda.
