---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch "FCAJ Community Day - Conference Call - May"

### Mục Đích Của Sự Kiện

- Kết nối cộng đồng thực tập sinh FCAJ (First Cloud AI Journey) thông qua các buổi chia sẻ trực tiếp tại Bitexco Financial Tower
- Cập nhật xu hướng ứng dụng AI vào xây dựng sản phẩm và vận hành hệ thống
- Giới thiệu các dịch vụ nền tảng của AWS (CloudFront, Amazon Quick) và cách khai thác trong thực tế
- Chia sẻ kinh nghiệm thực chiến từ các dự án hackathon và bài toán doanh nghiệp (credit scoring cho startup)

### Danh Sách Diễn Giả

- Đại diện đội ngũ AWS và cộng đồng FCAJ phụ trách các chủ đề: Context Engineering & AI, CloudFront, Amazon Quick, LLM Determinism, Multi-Agent System
- Đội thi đến từ LotusHacks Hackathon chia sẻ hành trình xây dựng sản phẩm UTMorpho
- *(Thông tin tên cụ thể của từng diễn giả sẽ được bổ sung theo tài liệu chương trình chính thức của sự kiện)*

### Nội Dung Nổi Bật

#### Context Is Everything: Making AI Actually Work for You

- Lý do vì sao AI "thất bại" khi thiếu context, và context thực sự có nghĩa là gì trong tương tác với AI
- Sự chuyển dịch từ prompt engineering đơn thuần sang khái niệm "Second AI Brain" - AI có khả năng ghi nhớ và học hỏi theo thời gian
- Mối liên hệ giữa chất lượng context đầu vào và chất lượng kết quả đầu ra của AI
- Định hướng nghề nghiệp cho sinh viên muốn bắt đầu xây dựng sản phẩm với AI

#### 36 hrs với LotusHacks – Building UTMorpho from Idea to Reality

- Hành trình từ ý tưởng ban đầu đến khi định hình rõ bài toán mà UTMorpho giải quyết
- Áp lực và kỷ luật cần có khi phát triển sản phẩm trong 36 giờ liên tục
- Những thất bại, điểm nghẽn và các bước ngoặt (turning points) trong quá trình phát triển
- Demo tổng quan sản phẩm UTMorpho và các bài học rút ra sau cuộc thi

#### From Edge To Origin: CloudFront as Your Foundation

- Amazon CloudFront phù hợp với nhiều loại workload khác nhau, không chỉ dừng ở phân phối nội dung tĩnh
- Chiến lược tối ưu chi phí (cost optimization) khi sử dụng CloudFront
- Các khả năng bảo mật tích hợp sẵn giúp bảo vệ ứng dụng ở lớp edge
- Cải thiện độ tin cậy (reliability) và hiệu năng (performance) cho hệ thống nhờ kiến trúc phân tán toàn cầu

#### Friendly AI Assistant with Amazon Quick

- **Quick Chat Agent**: trợ lý AI hỗ trợ khai thác dữ liệu và phân tích insight
- **Quick Flows**: tạo workflow thông minh bằng ngôn ngữ tự nhiên, không cần viết code
- **Quick Spaces**: không gian cộng tác giúp biến insight cá nhân thành tri thức chung của team
- **Quick Sight**: xây dựng dashboard và báo cáo từ dữ liệu thô bằng ngôn ngữ tự nhiên

#### Non-Determinism of "Deterministic" LLM Settings

- Cách LLM lựa chọn token tiếp theo trong quá trình sinh văn bản
- Giả định phổ biến: Temperature = 0 sẽ đảm bảo tính xác định (determinism) tuyệt đối
- Thực tế: các tối ưu hóa ở tầng inference (batching, phần cứng, floating-point) khiến kết quả vẫn có thể khác nhau
- Tác động thực tế đến các hệ thống production và chiến lược giảm thiểu rủi ro này

#### Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring

- Sự lệch pha giữa cấu trúc dữ liệu ngân hàng truyền thống và đặc thù dữ liệu của startup
- Khi nào nên dùng single agent và khi nào cần chuyển sang multi-agent
- Mô hình "Virtual Credit Committee" - nhiều agent đóng vai trò khác nhau trong quy trình thẩm định tín dụng
- Các rào chắn (guardrails) và yêu cầu tuân thủ (compliance) cần thiết khi triển khai AI trong lĩnh vực tài chính
- ROI vận hành và lộ trình triển khai thực tế

### Những Gì Học Được

#### Tư Duy Về AI & Sản Phẩm

- Context là yếu tố quyết định chất lượng output của AI, không chỉ đơn thuần là prompt hay hơn
- Sản phẩm tốt thường ra đời từ áp lực thời gian và khả năng ra quyết định nhanh (bài học từ LotusHacks)
- AI đang dịch chuyển từ công cụ hỗ trợ đơn lẻ sang hệ thống có trí nhớ và khả năng suy luận liên tục

#### Kiến Trúc & Hạ Tầng

- CloudFront không chỉ là CDN mà còn là lớp nền tảng cho bảo mật, hiệu năng và tối ưu chi phí
- Hiểu rõ hơn về rủi ro non-determinism trong LLM, đặc biệt quan trọng khi xây dựng hệ thống cần khả năng tái lặp (reproducibility)
- Multi-agent system là hướng tiếp cận phù hợp cho các bài toán nghiệp vụ phức tạp, nhiều bước ra quyết định như credit scoring

#### Ứng Dụng AI Trong Doanh Nghiệp

- Amazon Quick cho thấy xu hướng "AI hóa" các tác vụ vận hành và phân tích dữ liệu mà không cần kỹ năng lập trình
- Việc thiết kế guardrails và compliance là bắt buộc khi đưa AI vào các lĩnh vực nhạy cảm như tài chính

### Ứng Dụng Vào Công Việc

- Áp dụng tư duy "context-first" khi thiết kế prompt và pipeline AI cho các tác vụ hiện tại
- Cân nhắc sử dụng CloudFront cho các workload cần tối ưu chi phí và độ trễ trong dự án đang thực tập
- Lưu ý về non-determinism khi kiểm thử và đánh giá kết quả từ LLM, tránh giả định kết quả luôn giống nhau dù cùng cấu hình
- Tham khảo mô hình multi-agent khi thiết kế các workflow tự động hóa nhiều bước
- Tìm hiểu thêm Amazon Quick như một công cụ tiềm năng hỗ trợ báo cáo và phân tích dữ liệu nội bộ

### Trải nghiệm trong event

Tham gia **FCAJ Community Day - Conference Call** tại Bitexco Financial Tower là một trải nghiệm đáng nhớ, giúp tôi được tiếp cận trực tiếp với các xu hướng công nghệ mới nhất từ AWS cũng như những câu chuyện thực chiến từ cộng đồng.

#### Kết nối cộng đồng

- Được gặp gỡ và trao đổi trực tiếp với các bạn thực tập sinh khác trong chương trình FCAJ, cũng như đội ngũ mentor và diễn giả
- Không khí sự kiện cởi mở, tạo cảm hứng cho việc học hỏi và chia sẻ kinh nghiệm

#### Trải nghiệm học thuật và kỹ thuật

- Buổi chia sẻ về "Context Is Everything" giúp tôi thay đổi cách tiếp cận khi làm việc với AI, không chỉ dừng ở việc viết prompt mà còn quan tâm đến cách cung cấp và quản lý context
- Câu chuyện từ đội LotusHacks về UTMorpho là nguồn cảm hứng lớn về tinh thần "làm thật, học thật" trong môi trường áp lực cao
- Phần trình bày về non-determinism của LLM khiến tôi nhìn nhận lại các giả định trước đây về tính ổn định của mô hình AI

#### Bài học rút ra

- AI không chỉ là công cụ mà đang dần trở thành một phần hạ tầng cần được thiết kế cẩn trọng, từ context, độ tin cậy cho đến compliance
- Việc kết hợp kiến thức nền tảng (cloud, kiến trúc hệ thống) với AI mới thực sự tạo ra giá trị bền vững cho doanh nghiệp

#### Một số hình ảnh khi tham gia sự kiện
* Thêm các hình ảnh của các bạn tại đây

> Nhìn chung, sự kiện đã mang lại cho tôi góc nhìn toàn diện hơn về việc ứng dụng AI trong thực tế doanh nghiệp, đồng thời tạo động lực để tiếp tục học hỏi và thử nghiệm các công nghệ mới trong quá trình thực tập.
