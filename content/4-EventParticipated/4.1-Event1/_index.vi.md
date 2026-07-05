---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---


# Bài thu hoạch “FCAJ Community Day - Conference Call”

### Mục Đích Của Sự Kiện

- Chia sẻ best practices trong thiết kế ứng dụng hiện đại
- Giới thiệu phương pháp DDD và event-driven architecture
- Hướng dẫn lựa chọn compute services phù hợp
- Giới thiệu công cụ AI hỗ trợ development lifecycle

### Danh Sách Diễn Giả

- **VY LAM** - Senior Business Systems Analyst (VPBank)
- **THAO NGUYEN** - GenAI Engineer (VIB)
- **MAI NGUYEN** - GenAI Engineer (VIB)
- **UYEN LE** - GenAI Engineer (VIB)
- **ANH PHAM** - Cloud Consultant (G-AsiaPacific Vietnam)
- **THINH NGUYEN** - Devops Engineer (FCAJ)
- **TINH TRUONG** - Platform Enginner (GoTymeX)
- **DUC DAO** - Solutions Architect (Cloud Kinetics)
### Nội Dung Nổi Bật

#### Context Ảnh Hưởng Đến Chất Lượng Câu Trả Lời Của AI

- Cách để đưa context đúng để có kết quả chất lượng hơn.
- Không nói lại những thứ đã được nạp sẵn trong AI khiến tốn tài nguyên hơn.
- Tránh ngữ cảnh không liên quan, dư thừa, hoặc lời nhắc mơ hồ.
- Chỉ nên cung cấp đúng những thứ liên quan và không nên trộn thêm 1 lĩnh vực khác vào.
 
#### Giải Pháp AI Hỗ Trợ Công Việc Doanh Nghiệp

- Giới thiệu Amazon Quick Suite là giải pháp AI thống nhất của AWS cho doanh nghiệp.
- Ứng dụng demo cách để tự động hóa công việc.

#### CloudFront as Your Foundation

- CloudFront giới thiệu mô hình định giá cố định thay vì trước kia dùng pay as you go. Nhằm loại bỏ rủi ro hóa đơn đột biến.
- Những use case thực tế mà khách hàng thường quan tâm như chi phí phát sinh.
- Các tệp khách hàng chính (chủ website nhỏ, doanh nghiệp, doanh nghiệp trung hoặc cao cấp),
- Nói về những thứ CloudFront cung cấp bảo mật cho sản phẩm.
- Nâng cao hiệu suất bằng HTTP/3, nén dữ liệu và kiến trúc cache đa tầng.
- Tối ưu chi phí bằng Data Transfer Out và bằng cách giảm tải CPU cho EC2 bằng cách dùng CF xử lý việc bắt tay giao thức TCP, bắt tay TLS (HTTPS). Điều này giải phóng EC2 khỏi việc phải gồng gánh quá nhiều. Con số giảm được đưa ra có thể từ 5% xuống còn 1%.
- Hỗ trợ cấu hình trang lỗi tùy chỉnh (custom error pages) để cung cấp trải nghiệm thân thiện với người dùng hơn khi máy chủ Origin không khả dụng
#### Chia sẽ hành trình 36 tiếng từ ý tưởng tạo ra 1 sản phẩm thực tế

- Chia sẽ lại hành trình tham gia LotusHacks xây dựng sản phẩm UTMorpho trong 36 giờ.
- UTMorpho giải quyết vấn đề giao diện do AI tạo ra không thể chỉnh sửa trực tiếp, dễ bị trôi dạt thiết kế.
- Quá trình phát triển 36 giờ tập trung vào phân chia vai trò nhanh chóng, xây dựng cốt lõi và cắt giảm tính năng.
- Chia sẽ kiến trúc đã sử dụng từ prompt của user đi qua 3 AI sau đó lưu kết quả vào S3.
- Chú trọng vào tính năng chính của ứng dụng trước, không phải càng nhiều tính năng càng tốt.
- Demo sản phẩm đã làm được vào ngày thi.
#### Tính Xác Định Trong Các Mô Hình Ngôn Ngữ Lớn

- Cài đặt "deterministic" (temp=0) không đảm bảo kết quả LLM luôn nhất quán.
- Hiện tượng này do kiến trúc GPU (số học dấu phẩy động) và tối ưu hóa suy luận
- Các nhà nghiên cứu thấy không mô hình nào nhất quán, độ chính xác có thể khác biệt lớn.
- Dùng nhiều lần chạy và bỏ phiếu đa số để tăng tính xác định, hoặc buộc định dạng có cấu trúc
- Nên thiết kế ứng dụng cho biến thiên và thử temp=0.1 để tránh mô hình bị lặp.

#### Amazon Q Developer

- Nên dùng su

### Những Gì Học Được

#### Tư Duy Thiết Kế

- **Business-first approach**: Luôn bắt đầu từ business domain, không phải technology
- **Ubiquitous language**: Importance của common vocabulary giữa business và tech teams
- **Bounded contexts**: Cách identify và manage complexity trong large systems

#### Kiến Trúc Kỹ Thuật

- **Event storming technique**: Phương pháp thực tế để mô hình hóa quy trình kinh doanh
- Sử dụng **Event-driven communication** thay vì synchronous calls
- **Integration patterns**: Hiểu khi nào dùng sync, async, pub/sub, streaming
- **Compute spectrum**: Criteria chọn từ VM → containers → serverless

#### Chiến Lược Hiện Đại Hóa

- **Phased approach**: Không rush, phải có roadmap rõ ràng
- **7Rs framework**: Nhiều con đường khác nhau tùy thuộc vào đặc điểm của mỗi ứng dụng
- **ROI measurement**: Cost reduction + business agility

### Ứng Dụng Vào Công Việc

- **Áp dụng ...** 

### Trải nghiệm trong event

Tham gia workshop **“GenAI-powered App-DB Modernization”** là một trải nghiệm rất bổ ích, giúp tôi có cái nhìn toàn diện về cách hiện đại hóa ứng dụng và cơ sở dữ liệu bằng các phương pháp và công cụ hiện đại. Một số trải nghiệm nổi bật:

#### Học hỏi từ các diễn giả có chuyên môn cao
- Các diễn giả đến từ AWS và các tổ chức công nghệ lớn đã chia sẻ **best practices** trong thiết kế ứng dụng hiện đại.
- Qua các case study thực tế, tôi hiểu rõ hơn cách áp dụng **Domain-Driven Design (DDD)** và **Event-Driven Architecture** vào các project lớn.

#### Trải nghiệm kỹ thuật thực tế
- Tham gia các phiên trình bày về **event storming** giúp tôi hình dung cách **mô hình hóa quy trình kinh doanh** thành các domain events.
- Học cách **phân tách microservices** và xác định **bounded contexts** để quản lý sự phức tạp của hệ thống lớn.
- Hiểu rõ trade-offs giữa **synchronous và asynchronous communication** cũng như các pattern tích hợp như **pub/sub, point-to-point, streaming**.

#### Ứng dụng công cụ hiện đại
- Trực tiếp tìm hiểu về **Amazon Q Developer**, công cụ AI hỗ trợ SDLC từ lập kế hoạch đến maintenance.
- Học cách **tự động hóa code transformation** và pilot serverless với **AWS Lambda**, từ đó nâng cao năng suất phát triển.

#### Kết nối và trao đổi
- Workshop tạo cơ hội trao đổi trực tiếp với các chuyên gia, đồng nghiệp và team business, giúp **nâng cao ngôn ngữ chung (ubiquitous language)** giữa business và tech.
- Qua các ví dụ thực tế, tôi nhận ra tầm quan trọng của **business-first approach**, luôn bắt đầu từ nhu cầu kinh doanh thay vì chỉ tập trung vào công nghệ.

#### Bài học rút ra
- Việc áp dụng DDD và event-driven patterns giúp giảm **coupling**, tăng **scalability** và **resilience** cho hệ thống.
- Chiến lược hiện đại hóa cần **phased approach** và đo lường **ROI**, không nên vội vàng chuyển đổi toàn bộ hệ thống.
- Các công cụ AI như Amazon Q Developer có thể **boost productivity** nếu được tích hợp vào workflow phát triển hiện tại.

#### Một số hình ảnh khi tham gia sự kiện
* Thêm các hình ảnh của các bạn tại đây
> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp tôi thay đổi cách tư duy về thiết kế ứng dụng, hiện đại hóa hệ thống và phối hợp hiệu quả hơn giữa các team.
