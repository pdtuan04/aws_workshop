---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---


# Bài thu hoạch “AWS First Cloud AI Journey Community Day 2026”

### Mục Đích Của Sự Kiện
Tham gia buổi gặp gỡ cộng đồng để kết nối với các chuyên gia Cloud, khám phá những ứng dụng mới của Cloud & Generative AI, cùng trải nghiệm các demo thực tế và mở rộng networking trong hệ sinh thái công nghệ.

### Danh Sách Diễn Giả

- VY LAM - Senior Business Systems Analyst (VPBank)
- THAO NGUYEN - GenAI Engineer (VIB)
- MAI NGUYEN - GenAI Engineer (VIB)
- UYEN LE - GenAI Engineer (VIB)
- ANH PHAM - Cloud Consultant (G-AsiaPacific Vietnam)
- THINH NGUYEN - Devops Engineer (FCAJ)
- TINH TRUONG - Platform Enginner (GoTymeX)
- DUC DAO - Solutions Architect (Cloud Kinetics)
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

#### Enterprise-Grade Multi-Agent System
- Những case khi làm việc tại ngân hàng.
- Đưa ra giải pháp đánh giá tín dụng tốt hơn.
- Hệ thống giúp tối ưu hóa chi phí và thời gian so với quy trình đánh giá tín dụng startup truyền thống.
### Những Gì Học Được

- Nắm được tầm quan trọng của việc xây dựng context phù hợp khi sử dụng AI nhằm nâng cao chất lượng kết quả.
- Hiểu thêm về cách tối ưu hiệu năng, chi phí và bảo mật cho ứng dụng thông qua Amazon CloudFront với Free Tier.
- Biết được quy trình phát triển sản phẩm trong thời gian ngắn, từ ý tưởng đến triển khai và trình diễn sản phẩm.

### Ứng Dụng Vào Công Việc

- Áp dụng kiến thức về Amazon CloudFront vào dự án thực tập để tăng tốc độ truy cập, tối ưu hiệu năng và tích hợp AWS WAF nhằm tăng cường bảo mật.
- Sử dụng AI hiệu quả hơn trong quá trình học tập và lập trình bằng cách xây dựng prompt và cung cấp context phù hợp.
- Tham khảo các kinh nghiệm triển khai hệ thống thực tế.

### Trải nghiệm trong event

#### Học hỏi từ các diễn giả có chuyên môn cao

Buổi sự kiện mang đến nhiều góc nhìn thực tế từ các diễn giả đang làm việc tại các doanh nghiệp và tổ chức công nghệ. Những chia sẻ không chỉ tập trung vào kiến thức kỹ thuật mà còn giúp mình hiểu hơn cách các công nghệ Cloud và AI được áp dụng để giải quyết các bài toán trong doanh nghiệp.

#### Bài học rút ra

- Luôn lựa chọn giải pháp phù hợp với yêu cầu thực tế thay vì chạy theo công nghệ mới.
- Thiết kế hệ thống cần cân bằng giữa hiệu năng, chi phí và khả năng mở rộng.
- AI là công cụ hỗ trợ rất hiệu quả nhưng cần biết cách đặt ngữ cảnh và kiểm chứng kết quả trước khi sử dụng.
- Muốn phát triển trong lĩnh vực Cloud cần không ngừng cập nhật kiến thức và học hỏi từ những kinh nghiệm thực tế.

#### Một số hình ảnh và video khi tham gia sự kiện
![Security](../../images/4-events/event1.jpg)
