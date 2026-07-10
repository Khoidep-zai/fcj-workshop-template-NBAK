---
title: "Tuần 5: Amazon DynamoDB và lưu trữ kết quả phân tích (01/06/2026 - 05/06/2026)"
menuTitle: "Tuần 5"
date: 2026-07-24
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Mục tiêu tuần 5:**

- Tìm hiểu Amazon DynamoDB để lưu trữ kết quả phân tích hình ảnh.
- Tích hợp Lambda lưu kết quả Rekognition, Textract vào DynamoDB.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Tìm hiểu Amazon DynamoDB: Table, Item, Partition Key, Sort Key. Tìm hiểu mô hình tính phí: On-Demand vs Provisioned Capacity. | 01/06/2026 | 01/06/2026 | https://docs.aws.amazon.com/dynamodb/ |
| 3 | Thiết kế schema DynamoDB cho bảng image_scan_results: Partition Key: order_id, Sort Key: scan_timestamp, Attributes: bucket, key, rekognition_labels, textract_lines, status. | 02/06/2026 | 02/06/2026 | |
| 4 | Thực hành tạo DynamoDB table với On-Demand mode. Cập nhật IAM Role của Lambda thêm quyền AmazonDynamoDBFullAccess. | 03/06/2026 | 03/06/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 5 | Tích hợp DynamoDB vào Lambda function: Sau khi gọi Rekognition và Textract, lưu kết quả vào bảng. Kiểm thử upload ảnh và xem item trong DynamoDB Console. | 04/06/2026 | 04/06/2026 | https://docs.aws.amazon.com/dynamodb/ |
| 6 | Tích hợp Amazon SNS gửi email cảnh báo khi phát hiện hàng hóa hư hỏng (confidence > 80%). Kiểm thử toàn bộ pipeline. | 05/06/2026 | 05/06/2026 | |

**Kết quả đạt được tuần 5:**

- Hiểu cách thiết kế schema DynamoDB hợp lý cho bài toán lưu kết quả phân tích ảnh.
- Tạo và cấu hình thành công DynamoDB table với On-Demand mode.
- Tích hợp thành công DynamoDB vào Lambda, kết quả phân tích được lưu trữ đầy đủ.
- Tích hợp Amazon SNS gửi email cảnh báo tự động khi phát hiện hàng hóa hư hỏng.
- Hoàn thành pipeline đầy đủ: S3 → SQS → Lambda → AI/ML → DynamoDB → SNS.
