---
title: "Week 2"
date: 2026-07-24
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Week 2: Amazon S3, SQS and Event-Driven Architecture (11/05/2026 - 15/05/2026)

**Week 2 Objectives:**

- Hiểu sâu về Amazon S3 và cách tổ chức lưu trữ ảnh hàng hóa.
- Tìm hiểu Amazon SQS và vai trò làm buffer trong kiến trúc Event-Driven.
- Thiết kế luồng S3 → SQS → Lambda cho hệ thống xử lý ảnh bất đồng bộ.

**Tasks completed this week:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Tìm hiểu Amazon S3: Bucket, Object, Storage Class, Lifecycle Policy, Versioning. Nghiên cứu cách tổ chức prefix hợp lý cho bucket lưu ảnh hàng hóa hư hỏng. | 11/05/2026 | 11/05/2026 | https://docs.aws.amazon.com/s3/ |
| 3 | Tìm hiểu Amazon SQS: Standard Queue vs FIFO Queue. Hiểu các thông số: Visibility Timeout, Message Retention Period, Dead Letter Queue. | 12/05/2026 | 12/05/2026 | https://docs.aws.amazon.com/sqs/ |
| 4 | Nghiên cứu kiến trúc Event-Driven với mô hình S3 → SQS → Lambda. Hiểu lý do cần SQS làm buffer để tránh Lambda bị gọi ồ ạt khi nhiều ảnh upload cùng lúc. | 13/05/2026 | 13/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 5 | Thực hành: Tạo S3 bucket lưu ảnh hàng hóa. Cấu hình S3 Lifecycle Policy và Versioning cho bucket. | 14/05/2026 | 14/05/2026 | https://000057.awsstudygroup.com/vi/ |
| 6 | Thực hành: Tạo SQS Standard Queue (image-processing-queue). Cấu hình Access Policy cho phép S3 gửi message vào SQS. Cấu hình S3 Event Notification. | 15/05/2026 | 15/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |

**Week 2 Results:**

- Hiểu các khái niệm cốt lõi của Amazon S3: Bucket, Object, Storage Class, Lifecycle, Versioning.
- Nắm được vai trò của Amazon SQS trong kiến trúc Event-Driven và lý do cần buffer giữa S3 và Lambda.
- Tạo và cấu hình thành công S3 bucket với Event Notification.
- Tạo thành công SQS Standard Queue và cấp quyền cho S3 gửi message vào hàng đợi.
- Hiểu rõ luồng xử lý S3 → SQS → Lambda và lý do kiến trúc này phù hợp với bài toán xử lý ảnh quy mô lớn.
