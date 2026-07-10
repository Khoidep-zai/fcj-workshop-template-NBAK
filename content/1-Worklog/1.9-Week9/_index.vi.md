---
title: "Tuần 9: Phát triển backend - tích hợp Lambda, S3, SQS, AI/ML (29/06/2026 - 03/07/2026)"
menuTitle: "Tuần 9"
date: 2026-07-24
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

**Mục tiêu tuần 9:**

- Hoàn thiện toàn bộ backend serverless với đầy đủ Lambda functions.
- Tối ưu hiệu năng xử lý và xử lý các trường hợp lỗi (error handling).

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Hoàn thiện orchestrator Lambda function: Xử lý đầy đủ các record từ SQS batch, gọi Rekognition và Textract song song, xử lý timeout và retry. | 29/06/2026 | 29/06/2026 | |
| 3 | Phát triển evaluator Lambda function: Đánh giá mức độ hư hỏng từ kết quả Rekognition, xác định ngưỡng confidence để phân loại. | 30/06/2026 | 30/06/2026 | |
| 4 | Phát triển processor Lambda function: Lưu đầy đủ kết quả vào DynamoDB, kích hoạt SNS notification với các ca nghiêm trọng. | 01/07/2026 | 01/07/2026 | |
| 5 | Cấu hình Dead Letter Queue (DLQ) cho SQS. Thêm CloudWatch Alarms cho Lambda errors và SQS queue depth. Kiểm thử các tình huống lỗi. | 02/07/2026 | 02/07/2026 | |
| 6 | Kiểm thử tải backend: upload 20-30 ảnh cùng lúc. Ghi nhận giới hạn và đề xuất phương án tối ưu. Viết tài liệu API cho frontend sử dụng. | 03/07/2026 | 03/07/2026 | |

**Kết quả đạt được tuần 9:**

- Hoàn thiện 3 Lambda functions (orchestrator, evaluator, processor) với error handling đầy đủ.
- Cấu hình DLQ để xử lý message thất bại, tránh mất dữ liệu.
- Thêm CloudWatch Alarms giám sát chủ động các lỗi hệ thống.
- Kiểm thử tải thành công với 20-30 ảnh đồng thời, backend ổn định.
