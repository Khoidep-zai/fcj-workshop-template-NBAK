---
title: "Week 4"
date: 2026-07-24
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## Week 4: Amazon Rekognition and Textract - AI/ML Image Analysis (25/05/2026 - 29/05/2026)

**Week 4 Objectives:**

- Tích hợp Amazon Rekognition để nhận diện tình trạng hư hỏng của kiện hàng.
- Tích hợp Amazon Textract để trích xuất mã vận đơn và thông tin từ nhãn dán.

**Tasks completed this week:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Tìm hiểu Amazon Rekognition: detect_labels, detect_text, compare_faces. Hiểu cách sử dụng MaxLabels, MinConfidence để lọc kết quả phân tích. | 25/05/2026 | 25/05/2026 | https://docs.aws.amazon.com/rekognition/ |
| 3 | Tìm hiểu Amazon Textract: detect_document_text, analyze_document. Hiểu sự khác biệt giữa LINE và WORD block trong kết quả Textract. | 26/05/2026 | 26/05/2026 | https://docs.aws.amazon.com/textract/ |
| 4 | Tích hợp Amazon Rekognition vào Lambda function: Gọi detect_labels với ảnh từ S3, log nhãn nhận diện và confidence score. Thực hành với ảnh kiện hàng. | 27/05/2026 | 27/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 5 | Tích hợp Amazon Textract vào Lambda function: Gọi detect_document_text với ảnh từ S3, trích xuất và log các dòng text (mã vận đơn, SĐT, địa chỉ). | 28/05/2026 | 28/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 6 | Kiểm thử end-to-end: upload 5-10 ảnh cùng lúc lên S3. Kiểm tra CloudWatch Logs và SQS queue trống sau khi Lambda xử lý hết message. | 29/05/2026 | 29/05/2026 | |

**Week 4 Results:**

- Hiểu cách sử dụng Amazon Rekognition để nhận diện tình trạng hàng hóa (Box, Cardboard, Damaged...).
- Hiểu cách sử dụng Amazon Textract để trích xuất văn bản từ nhãn dán vận đơn.
- Tích hợp thành công cả Rekognition và Textract vào Lambda function xử lý ảnh.
- Kiểm thử end-to-end thành công: ảnh upload → SQS → Lambda → AI phân tích → CloudWatch Logs.
- Hoàn thành kiểm thử song song với nhiều ảnh, xác nhận SQS queue được xử lý sạch.
