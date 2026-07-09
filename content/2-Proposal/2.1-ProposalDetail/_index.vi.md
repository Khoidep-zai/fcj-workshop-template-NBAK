---
title: "Chi tiết đề xuất"
date: 2026-07-24
weight: 1
chapter: false
pre: " <b> 2.1. </b> "
---

# Giải pháp tự động hóa giám sát chất lượng hàng hóa dựa trên Serverless và AI/ML

### Tóm tắt điều hành

Trong lĩnh vực Logistics, doanh nghiệp đang chịu áp lực lớn về thời gian xử lý, độ chính xác dữ liệu và khả năng kiểm soát tổn thất hàng hóa. Việc giám sát chất lượng hàng hóa tại kho hiện nay phần lớn vẫn phụ thuộc vào con người, dẫn đến tình trạng xử lý sự cố chậm, dữ liệu bị phân tán và khó cập nhật theo thời gian thực.

Nhóm đề xuất xây dựng hệ thống **"Giải pháp tự động hóa giám sát chất lượng hàng hóa dựa trên kiến trúc Serverless và Trí tuệ nhân tạo (AI/ML)"**. Đây là một hệ thống phần mềm ứng dụng các dịch vụ của Amazon Web Services (AWS), cho phép nhân viên giao hàng hoặc khách hàng chụp ảnh kiện hàng gặp sự cố như rách, vỡ, móp méo hoặc hư hỏng, sau đó tải trực tiếp hình ảnh lên hệ thống để được phân tích tự động.

Hệ thống sử dụng AI/ML để nhận diện mức độ hư hại của hàng hóa, trích xuất thông tin vận đơn, lưu trữ bằng chứng và gửi cảnh báo cho bộ phận liên quan. Nhờ đó, quy trình xử lý sự cố có thể được rút ngắn từ vài giờ hoặc vài ngày xuống còn vài giây, đồng thời giúp doanh nghiệp giảm chi phí vận hành, hạn chế sai sót thủ công và nâng cao chất lượng dịch vụ.

---

### Tuyên bố vấn đề

#### Vấn đề hiện tại

Theo khảo sát thực tế, việc ghi nhận và xử lý hàng hóa hư hỏng hiện nay đang gặp nhiều điểm lỗi trong quy trình vận hành:

- **Quy trình thủ công, tốn thời gian và dễ sai sót:** Khi phát hiện hàng hóa bị hư hỏng, nhân viên thường phải tự chụp ảnh bằng điện thoại cá nhân, gửi qua nhóm chat hoặc lập tờ trình giấy. Bộ phận thẩm định sau đó phải tổng hợp các thông tin rời rạc này để nhập lại vào hệ thống ERP và xử lý thủ tục bồi hoàn cho khách hàng. Quy trình này mất nhiều thời gian và dễ gây nhầm lẫn dữ liệu.

- **Thiếu khả năng tự động hóa và cảnh báo tức thời:** Do chưa có phần mềm tự động phân tích hình ảnh và đọc thông tin đơn hàng, quản lý kho thường không biết ngay mức độ hư hỏng của hàng hóa để đưa ra quyết định xử lý kịp thời. Việc phản hồi chậm làm ảnh hưởng đến trải nghiệm khách hàng và uy tín dịch vụ.

- **Thiếu khả năng mở rộng hệ thống:** Vào mùa cao điểm, số lượng hàng hóa đổ về kho tăng mạnh. Quy trình kiểm tra thủ công không thể xử lý song song nhiều đơn hàng cùng lúc, dẫn đến quá tải, bỏ sót hàng hóa hư hỏng hoặc để sản phẩm lỗi tiếp tục đi đến tay người tiêu dùng.

- **Dữ liệu lưu trữ phân mảnh, khó truy xuất:** Hồ sơ sự cố hiện có thể nằm rải rác trong sổ tay, file Excel hoặc các nhóm chat. Khi cần thống kê tỷ lệ tổn thất theo tháng/quý để báo cáo cho ban giám đốc, nhân viên phải rà soát thủ công, mất thời gian và dễ sai lệch.

- **Chi phí vận hành cao:** Doanh nghiệp phải duy trì nhân sự chuyên trách tại từng điểm kho để kiểm tra, nhập liệu và xử lý sự cố. Bên cạnh chi phí nhân công, các sai sót thông tin và tranh chấp đền bù kéo dài cũng làm suy giảm lợi nhuận và uy tín của doanh nghiệp Logistics.

---

### Giải pháp đề xuất

Nhóm đề xuất xây dựng hệ thống tự động hóa quy trình giám sát chất lượng hàng hóa dựa trên kiến trúc Serverless và AI/ML. Hệ thống tập trung vào các khả năng cốt lõi sau:

- **Tự động hóa bằng AI thông minh:** Hệ thống sử dụng Amazon Rekognition để phân tích hình ảnh hàng hóa và nhận diện dấu hiệu hư hỏng. Kết quả phân tích có thể bao gồm nhãn trạng thái, mức độ hư hại và điểm tin cậy. Amazon Textract được dùng để trích xuất mã vận đơn, địa chỉ hoặc các thông tin văn bản liên quan từ ảnh mà không cần nhập tay.

- **Xử lý bất đồng bộ theo thời gian thực:** Hình ảnh sau khi được tải lên Amazon S3 sẽ kích hoạt luồng xử lý tự động. Dữ liệu hình ảnh, mã vận đơn và kết quả phân tích được đồng bộ về Amazon DynamoDB để tra cứu, thống kê và xuất báo cáo. Cách xử lý này giúp rút ngắn thời gian ghi nhận và phản hồi từ vài ngày xuống còn vài giây.

- **Hạ tầng Serverless tự động co giãn:** Hệ thống chạy trên các dịch vụ Serverless của AWS, có thể tự động mở rộng khi số lượng ảnh tăng đột biến vào mùa cao điểm. Doanh nghiệp không cần quản lý máy chủ thủ công nhưng vẫn đảm bảo khả năng xử lý nhiều yêu cầu cùng lúc.

- **Quản lý tập trung và minh bạch dữ liệu:** Tất cả lịch sử quét, hình ảnh bằng chứng, mã vận đơn và trạng thái xử lý được lưu trữ tập trung. Người quản lý có thể tra cứu lịch sử bất kỳ lúc nào, kiểm tra bằng chứng và xuất báo cáo thống kê tình hình hàng hóa hư hỏng.

- **Tối ưu hóa chi phí vận hành:** Việc đưa AI vào quy trình giúp giảm sai sót so với nhập liệu thủ công, giảm nhu cầu nhân sự chuyên trách tại từng kho, rút ngắn thời gian giải quyết tranh chấp và nâng cao độ tin cậy trong xử lý bồi hoàn.

---

### Kiến trúc giải pháp

#### Kiến trúc tổng quan
<div style="display: flex; gap: 10px; justify-content: center; flex-wrap: wrap;">
      <img src="/images/DiagramStructure.png" alt="" width="1939" />

</div>

Hệ thống được thiết kế theo mô hình kiến trúc hướng sự kiện, sử dụng các dịch vụ AWS để tự động co giãn theo lưu lượng thực tế. Toàn bộ vòng đời của một yêu cầu giám sát chất lượng hàng hóa được chia thành 4 lớp công nghệ chính:

| Lớp kiến trúc | Vai trò | Dịch vụ AWS đề xuất |
| --- | --- | --- |
| Frontend & Auth | Cung cấp giao diện web, quản lý đăng nhập/đăng ký, cấp JWT Token và kiểm soát quyền truy cập API | AWS Amplify, Amazon Cognito, Amazon API Gateway |
| Storage | Tiếp nhận và lưu trữ ảnh hàng hóa hư hỏng do người dùng tải lên | Amazon S3 |
| Backend & AI/ML | Xử lý sự kiện tải ảnh, phân tích hình ảnh, trích xuất thông tin vận đơn, đánh giá mức độ hư hại và cập nhật dữ liệu | Amazon SQS, AWS Lambda, Amazon Rekognition, Amazon Textract, Amazon DynamoDB |
| Giám sát & Bảo mật | Theo dõi hoạt động hệ thống, quản lý log, phân quyền truy cập theo nguyên tắc least privilege | Amazon CloudWatch, AWS IAM |

#### Luồng xử lý chính

| Bước | Mô tả |
| --- | --- |
| 1 | Người dùng đăng nhập vào hệ thống thông qua giao diện web được triển khai bằng AWS Amplify và xác thực bằng Amazon Cognito. |
| 2 | Người dùng tải ảnh kiện hàng bị hư hỏng lên hệ thống. Ảnh được lưu vào Amazon S3 Raw Image Bucket. |
| 3 | S3 Event Notification phát sinh sự kiện sau khi ảnh được tải lên thành công và đưa thông tin xử lý vào Amazon SQS. |
| 4 | Lambda orchestrator-function đọc sự kiện từ SQS, sau đó gọi Amazon Rekognition để phát hiện hư hỏng và Amazon Textract để đọc mã vận đơn/thông tin văn bản. |
| 5 | Lambda evaluator-function đánh giá mức độ hư hại dựa trên kết quả AI/ML và xác định trạng thái xử lý. |
| 6 | Lambda processor-function lưu kết quả vào Amazon DynamoDB, cập nhật trạng thái hồ sơ và kích hoạt cảnh báo nếu cần. |
| 7 | Amazon SNS gửi thông báo Email/SMS cho quản lý kho hoặc bộ phận xử lý khi phát hiện sự cố nghiêm trọng. |
| 8 | Amazon CloudWatch ghi nhận log, metrics và hỗ trợ theo dõi lỗi trong toàn bộ quá trình vận hành. |

---

### Các dịch vụ AWS sử dụng

#### Frontend & Auth

- **AWS Amplify:** Lưu trữ và phân phối giao diện web cho người dùng.
- **Amazon Cognito:** Quản lý đăng nhập, đăng ký và cấp JWT Token.
- **Amazon API Gateway:** Tiếp nhận API request, kiểm tra token và chuyển tiếp yêu cầu đến backend.

#### Storage

- **Amazon S3:** Lưu trữ ảnh gốc của hàng hóa, đóng vai trò điểm tiếp nhận dữ liệu đầu vào.

#### Backend Serverless & AI/ML

- **Amazon SQS:** Làm hàng đợi trung gian, giúp hệ thống xử lý bất đồng bộ và tránh quá tải khi nhiều ảnh được tải lên cùng lúc.
- **AWS Lambda orchestrator-function:** Đọc sự kiện từ SQS và điều phối các tác vụ phân tích AI/ML.
- **Amazon Rekognition:** Phân tích hình ảnh để phát hiện dấu hiệu hư hỏng của kiện hàng.
- **Amazon Textract:** Trích xuất văn bản, mã vận đơn hoặc thông tin giao hàng từ ảnh.
- **AWS Lambda evaluator-function:** Đánh giá mức độ hư hại và phân loại trạng thái xử lý.
- **AWS Lambda processor-function:** Lưu kết quả, cập nhật hồ sơ và kích hoạt các bước xử lý tiếp theo.
- **Amazon DynamoDB:** Lưu trữ kết quả phân tích, lịch sử xử lý, trạng thái đơn hàng và dữ liệu phục vụ báo cáo.
- **Amazon SNS:** Gửi cảnh báo Email/SMS cho bộ phận liên quan.

#### Giám sát & Bảo mật

- **Amazon CloudWatch:** Theo dõi log, metrics, cảnh báo lỗi và hiệu năng của hệ thống.
- **AWS IAM:** Quản lý quyền truy cập theo nguyên tắc least privilege, đảm bảo từng dịch vụ chỉ có quyền cần thiết để hoạt động.

---

### Đánh giá rủi ro

| Rủi ro | Ảnh hưởng | Hướng xử lý |
| --- | --- | --- |
| Chất lượng ảnh đầu vào kém | AI có thể nhận diện sai hoặc không trích xuất được mã vận đơn | Hướng dẫn người dùng chụp ảnh rõ nét, đủ sáng; kiểm tra định dạng và kích thước ảnh trước khi tải lên |
| Kết quả AI/ML chưa chính xác trong một số trường hợp | Có thể phân loại sai mức độ hư hỏng | Cho phép người quản lý xác nhận thủ công với các trường hợp có điểm tin cậy thấp |
| Lưu lượng tăng cao vào mùa cao điểm | Hệ thống có thể phát sinh độ trễ nếu không kiểm soát hàng đợi tốt | Sử dụng SQS để điều tiết tải, Lambda tự động co giãn và CloudWatch để giám sát backlog |
| Rò rỉ dữ liệu hình ảnh hoặc thông tin vận đơn | Ảnh hưởng đến bảo mật dữ liệu khách hàng | Áp dụng Cognito, IAM least privilege, phân quyền truy cập S3 và mã hóa dữ liệu khi lưu trữ |
| Chi phí tăng nếu xử lý số lượng ảnh quá lớn | Ảnh hưởng đến ngân sách vận hành | Theo dõi usage bằng CloudWatch, đặt cảnh báo chi phí và tối ưu kích thước ảnh trước khi phân tích |

---

### Kết quả kỳ vọng

- Rút ngắn thời gian ghi nhận và xử lý sự cố hàng hóa từ vài giờ hoặc vài ngày xuống còn vài giây.
- Tự động nhận diện dấu hiệu hư hỏng của hàng hóa bằng AI, giảm phụ thuộc vào kiểm tra thủ công.
- Tự động trích xuất mã vận đơn và thông tin liên quan, hạn chế lỗi nhập liệu.
- Tập trung hóa dữ liệu sự cố, hình ảnh bằng chứng và trạng thái xử lý trên một hệ thống duy nhất.
- Hỗ trợ quản lý kho tra cứu lịch sử, thống kê tỷ lệ tổn thất và xuất báo cáo nhanh chóng.
- Tăng khả năng mở rộng trong mùa cao điểm nhờ kiến trúc Serverless.
- Giảm chi phí nhân sự vận hành, giảm tranh chấp đền bù và nâng cao uy tín dịch vụ Logistics.

---

### Kết luận

Giải pháp tự động hóa giám sát chất lượng hàng hóa dựa trên Serverless và AI/ML giúp doanh nghiệp Logistics chuyển đổi quy trình xử lý sự cố từ thủ công sang tự động, tập trung và có khả năng mở rộng. Việc kết hợp Amazon S3, SQS, Lambda, Rekognition, Textract, DynamoDB, SNS, CloudWatch và IAM tạo ra một kiến trúc phù hợp cho bài toán xử lý hình ảnh theo thời gian thực, đồng thời tối ưu chi phí vận hành và cải thiện chất lượng dịch vụ khách hàng.

---

# Ước tính chi phí vận hành hệ thống trên AWS

### Tóm tắt điều hành

Tài liệu này ước tính chi phí AWS cho hệ thống phát hiện và xử lý hàng hóa hư hỏng trong kho vận, dựa trên kiến trúc serverless sử dụng Amplify, Cognito, API Gateway, S3, SQS, Lambda, Rekognition, Textract, DynamoDB, SNS, CloudWatch và IAM.

Ước tính được xây dựng cho kịch bản thử nghiệm / vận hành thực tế trong 1 tuần, với khối lượng khoảng 245 ảnh/tuần và ~30 người dùng hoạt động. Trong phạm vi giả định này, tổng chi phí thực tế của tài khoản AWS mới vẫn là $0,00 do toàn bộ mức sử dụng nằm trong Free Tier tương ứng. Nếu tính theo đơn giá chuẩn mà không áp Free Tier, tổng chi phí 1 tuần vào khoảng $1,57 USD.

---

### 1. Tổng quan kiến trúc hệ thống

Hệ thống serverless trên AWS dùng để phát hiện và xử lý hàng hóa hư hỏng trong kho vận. Người dùng truy cập giao diện web được lưu trữ trên AWS Amplify, đăng nhập qua Amazon Cognito để nhận JWT token, sau đó gọi API qua Amazon API Gateway để tải ảnh hàng hóa lên Amazon S3.

Khi ảnh được tải lên, S3 phát sự kiện đẩy vào Amazon SQS để tránh quá tải khi nhiều ảnh được gửi cùng lúc. SQS kích hoạt chuỗi AWS Lambda gồm xử lý ảnh, gọi Amazon Rekognition để phát hiện hư hỏng, gọi Amazon Textract để đọc mã vận đơn hoặc địa chỉ trên nhãn hàng, sau đó ghi kết quả vào Amazon DynamoDB và gửi cảnh báo qua Amazon SNS khi độ tin cậy của AI dưới 80%.

Toàn bộ hệ thống được giám sát bởi Amazon CloudWatch và áp dụng nguyên tắc least-privilege qua AWS IAM cho từng hàm Lambda. Báo cáo này ước tính chi phí AWS cho 12 dịch vụ xuất hiện trong bản vẽ, cho một tuần sử dụng.

---

### 2. Giả định sử dụng làm cơ sở ước tính

Các giả định dưới đây được dùng làm cơ sở tính toán:

- Khối lượng ảnh xử lý: khoảng 35 ảnh/ngày x 7 ngày, tương đương 245 ảnh/tuần.
- Người dùng hoạt động: khoảng 30 nhân viên/khách hàng đăng nhập và sử dụng web app trong tuần.
- Tài khoản AWS: tài khoản mới, còn trong 12 tháng AWS Free Tier.
- Vùng giá tham khảo: US East (N. Virginia).

---

### 3. Bảng ước tính chi phí theo từng dịch vụ AWS (1 tuần)

| Dịch vụ AWS | Khối lượng sử dụng ước tính (1 tuần) | Đơn giá tham khảo (US East, N. Virginia) | Chi phí theo đơn giá chuẩn (chưa áp Free Tier) | Hạn mức AWS Free Tier áp dụng | Chi phí thực tế ước tính (tài khoản mới, đã áp Free Tier) |
| --- | --- | --- | --- | --- | --- |
| AWS Amplify (Hosting giao diện web) | ~5 lần build, ~0,5 GB lưu trên CDN, ~0,5 GB dữ liệu truyền cho ~30 người dùng | $0,01/phút build, $0,023/GB-tháng, $0,15/GB truyền dữ liệu | ≈ $0,23 | 1.000 phút build + 5 GB lưu trữ + 15 GB truyền dữ liệu/tháng (12 tháng đầu) | $0,00 |
| Amazon Cognito (Xác thực đăng nhập) | ~30 người dùng hoạt động (MAU) | $0,015/MAU | ≈ $0,45 | 10.000 MAU/tháng | $0,00 |
| Amazon API Gateway (REST API) | ~1.800 lượt gọi API | $3,50/1 triệu lượt gọi | ≈ $0,006 | 1.000.000 lượt gọi/tháng (12 tháng đầu) | $0,00 |
| Amazon S3 (Raw Image Bucket) | 245 lượt PUT + 245 lượt GET, ~0,5 GB lưu trữ | $0,005/1.000 PUT, $0,0004/1.000 GET, $0,023/GB-tháng | ≈ $0,004 | 2.000 PUT + 20.000 GET + 5 GB lưu trữ/tháng | $0,00 |
| Amazon SQS (Hàng đợi xử lý) | ~735 request | $0,40/1 triệu request | ≈ $0,0003 | 1.000.000 request/tháng | $0,00 |
| AWS Lambda (3 hàm) | ~800 lượt gọi, ~800 GB-giây | $0,20/1 triệu lượt gọi + $0,0000166667/GB-giây | ≈ $0,013 | 1.000.000 lượt gọi + 400.000 GB-giây/tháng | $0,00 |
| Amazon Rekognition (Phát hiện hư hỏng) | 245 ảnh xử lý | $0,001/ảnh | ≈ $0,245 | 5.000 ảnh/tháng (12 tháng đầu) | $0,00 |
| Amazon Textract (Đọc vận đơn) | 245 trang | $0,0015/trang | ≈ $0,368 | 1.000 trang/tháng (3 tháng đầu) | $0,00 |
| Amazon DynamoDB (Lưu log & lịch sử) | 245 lượt ghi + 300 lượt đọc | $0,625/1 triệu WRU, $0,125/1 triệu RRU | ≈ $0,0002 | 25 WCU/RCU + 25 GB lưu trữ/tháng | $0,00 |
| Amazon SNS (Gửi cảnh báo Email/SMS) | ~25 email cảnh báo | $2,00/100.000 email đã gửi | ≈ $0,0005 | 1.000 email/tháng (12 tháng đầu) | $0,00 |
| Amazon CloudWatch (Log, Metric, Alarm) | ~30 MB log, 3-5 metric, 3-5 alarm | $0,50/GB log, $0,30/metric-tháng, $0,10/alarm-tháng | ≈ $0,10 – $0,40 | 5 GB log + 10 metric + 10 alarm/tháng | $0,00 |
| AWS IAM (Phân quyền least-privilege) | Không tính phí theo lượt sử dụng | Miễn phí | $0,00 | Luôn miễn phí | $0,00 |

---

### 4. Tổng hợp chi phí

**Tổng theo đơn giá chuẩn (chưa áp Free Tier):** khoảng  $1,57 USD

Tổng chi phí thực tế ước tính (tài khoản mới, đã áp Free Tier): **$0,00 USD**

Hai dòng trên phản ánh hai góc nhìn:

- Chi phí theo đơn giá chuẩn nếu không có Free Tier.
- Chi phí thực tế sẽ xuất hiện trên hóa đơn AWS trong tuần thử nghiệm, bằng $0,00 vì toàn bộ khối lượng sử dụng nằm trong hạn mức Free Tier.

---

### 5. Dự báo khi mở rộng quy mô hoặc hết hạn Free Tier

Nếu hệ thống vận hành liên tục trong một tháng đầy đủ, phần lớn dịch vụ vẫn nằm trong hạn mức Free Tier hàng tháng. Điểm cần lưu ý nhất là Amazon Textract vì hạn mức miễn phí chỉ kéo dài 3 tháng đầu. Tuy nhiên, ở quy mô hiện tại, tổng chi phí AWS hàng tháng dự kiến vẫn rất thấp, ngay cả khi không còn Free Tier.

---

### 6. Hạn chế của ước tính và khuyến nghị

- Đây là ước tính dựa trên giả định lưu lượng, không phải số liệu billing thực tế.
- Số liệu chính xác nhất là theo dõi trực tiếp trong AWS Cost Explorer sau khi hệ thống chạy thật.
- Giá tham khảo theo vùng US East (N. Virginia); giá tại vùng khác có thể chênh lệch.
- Chưa bao gồm các chi phí ngoài phạm vi bản vẽ như Support Plan, domain, Route 53, WAF hoặc chi phí nhân sự vận hành.

---

### 7. Nguồn tham khảo

- AWS Lambda Pricing: https://aws.amazon.com/lambda/pricing/
- Amazon API Gateway Pricing: https://aws.amazon.com/api-gateway/pricing/
- Amazon S3 Pricing: https://aws.amazon.com/s3/pricing/
- Amazon SQS Pricing: https://aws.amazon.com/sqs/pricing/
- Amazon Rekognition Pricing: https://aws.amazon.com/rekognition/pricing/
- Amazon Textract Pricing: https://aws.amazon.com/textract/pricing/
- Amazon DynamoDB Pricing: https://aws.amazon.com/dynamodb/pricing/on-demand
- Amazon SNS Pricing: https://aws.amazon.com/sns/pricing/
- Amazon Cognito Pricing: https://aws.amazon.com/cognito/pricing/
- Amazon CloudWatch Pricing: https://aws.amazon.com/cloudwatch/pricing/
- AWS Amplify Pricing: https://aws.amazon.com/amplify/pricing/
- AWS Free Tier: https://aws.amazon.com/free/
