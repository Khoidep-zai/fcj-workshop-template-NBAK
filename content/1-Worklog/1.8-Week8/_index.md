---
title: "Week 8"
date: 2026-07-24
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

## Week 8: AWS Amplify and Frontend UI Construction (22/06/2026 - 26/06/2026)

**Week 8 Objectives:**

- Tìm hiểu AWS Amplify Hosting và bắt đầu xây dựng giao diện web cho hệ thống giám sát.
- Xây dựng trang đăng nhập và upload ảnh tích hợp với Cognito và S3.

**Tasks completed this week:**

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|-----------|--------------|-----------------|----------------|
| 2 | Tìm hiểu AWS Amplify Hosting: CI/CD pipeline, custom domain, build settings. So sánh Amplify Hosting với S3 Static Website Hosting. | 22/06/2026 | 22/06/2026 | https://docs.aws.amazon.com/amplify/ |
| 3 | Tìm hiểu Amplify UI Components cho React/Next.js: Authenticator component tích hợp Cognito, Storage component upload ảnh lên S3. | 23/06/2026 | 23/06/2026 | https://ui.docs.amplify.aws/ |
| 4 | Thực hành tạo ứng dụng web Next.js cơ bản. Tích hợp Amplify với Cognito User Pool. Xây dựng trang đăng nhập/đăng xuất. | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| 5 | Xây dựng trang upload ảnh: Gọi API lấy S3 presigned URL, upload ảnh trực tiếp lên S3 từ frontend, hiển thị trạng thái upload. | 25/06/2026 | 25/06/2026 | https://docs.amplify.aws/ |
| 6 | Kiểm thử toàn bộ luồng upload: Đăng nhập qua Cognito → Lấy presigned URL → Upload ảnh → SQS → Lambda xử lý. | 26/06/2026 | 26/06/2026 | |

**Week 8 Results:**

- Hiểu AWS Amplify Hosting và CI/CD pipeline cho frontend web application.
- Xây dựng thành công ứng dụng Next.js với tích hợp Cognito (đăng nhập/đăng xuất).
- Triển khai thành công trang upload ảnh sử dụng S3 presigned URL.
- Kiểm thử thành công luồng đầy đủ từ giao diện người dùng đến AI phân tích.
