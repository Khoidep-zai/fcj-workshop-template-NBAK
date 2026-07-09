---
title: "Tuần 7"
date: 2026-07-24
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

## Tuần 7: Amazon Cognito và bảo mật truy cập (15/06/2026 - 19/06/2026)

**Mục tiêu tuần 7:**

- Tìm hiểu Amazon Cognito và thiết kế phân quyền truy cập cho nhân viên Logistics.
- Tích hợp Cognito Authorizer vào API Gateway để bảo vệ API.

**Các công việc cần triển khai trong tuần này:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Tìm hiểu Amazon Cognito User Pool và Identity Pool. So sánh các phương án xác thực: Cognito, IAM User, bên thứ ba. | 15/06/2026 | 15/06/2026 | https://docs.aws.amazon.com/cognito/ |
| 3 | Tìm hiểu cách kết hợp IAM Role với Cognito Identity Pool. Tìm hiểu Cognito Authorizer trên Amazon API Gateway và JWT Token. | 16/06/2026 | 16/06/2026 | https://docs.aws.amazon.com/cognito/ |
| 4 | Thực hành tạo Cognito User Pool cho hệ thống giám sát hàng hóa. Thực hành tạo App Client và cấu hình thuộc tính người dùng. | 17/06/2026 | 17/06/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 5 | Thực hành tích hợp Cognito Authorizer vào API Gateway. Kiểm thử gọi API có yêu cầu xác thực bằng token Cognito. | 18/06/2026 | 18/06/2026 | https://docs.aws.amazon.com/cognito/ |
| 6 | Rà soát toàn bộ IAM Policy theo nguyên tắc Least Privilege. Đảm bảo mỗi Lambda function chỉ có đúng quyền cần thiết. | 19/06/2026 | 19/06/2026 | |

**Kết quả đạt được tuần 7:**

- Hiểu sự khác biệt giữa Cognito User Pool và Identity Pool và cách kết hợp với IAM Role.
- Tạo và cấu hình thành công Cognito User Pool cho hệ thống giám sát hàng hóa.
- Tích hợp thành công Cognito Authorizer vào API Gateway, đảm bảo chỉ người dùng đã xác thực mới gọi được API.
- Rà soát và tối ưu toàn bộ IAM Policy theo nguyên tắc Least Privilege.
