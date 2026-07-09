---
title: "Tuần 6"
date: 2026-07-24
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## Tuần 6: Amazon API Gateway và thiết kế RESTful API (08/06/2026 - 12/06/2026)

**Mục tiêu tuần 6:**

- Tìm hiểu Amazon API Gateway để xây dựng API cho frontend tra cứu kết quả phân tích.
- Thiết kế và kiểm thử các endpoint RESTful phục vụ dashboard quản lý.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Tìm hiểu Amazon API Gateway: REST API và HTTP API. So sánh REST API và HTTP API để chọn phương án phù hợp cho dự án. | 08/06/2026 | 08/06/2026 | https://docs.aws.amazon.com/apigateway/ |
| 3 | Thiết kế các API endpoint cần thiết: GET /scans, GET /scans/{orderId}, POST /upload-url lấy presigned URL upload ảnh lên S3. | 09/06/2026 | 09/06/2026 | |
| 4 | Thực hành tạo API Gateway HTTP API. Tạo Lambda function trả về dữ liệu từ DynamoDB. Kết nối API Gateway với Lambda Integration. | 10/06/2026 | 10/06/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 5 | Kiểm thử các API endpoint bằng Postman/curl. Xử lý CORS để cho phép frontend gọi API từ trình duyệt. | 11/06/2026 | 11/06/2026 | https://docs.aws.amazon.com/apigateway/ |
| 6 | Vẽ sơ đồ kiến trúc tổng thể của hệ thống giám sát hàng hóa (kiến trúc AWS Serverless). Trao đổi với mentor để rà soát kiến trúc đề xuất. | 12/06/2026 | 12/06/2026 | |

**Kết quả đạt được tuần 6:**

- Hiểu sự khác biệt giữa REST API và HTTP API trên Amazon API Gateway.
- Tạo thành công HTTP API với các endpoint phục vụ tra cứu kết quả phân tích.
- Kiểm thử thành công các API endpoint qua Postman, xử lý CORS đúng cách.
- Hoàn thành bản vẽ sơ đồ kiến trúc tổng thể AWS Serverless cho hệ thống, được mentor góp ý.
