---
title: "Các bài blogs đã đăng"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---
### [Blog 1 - Lợi Ích Khi Kết Hợp Amazon CloudFront với Application Load Balancer](3.1-Blog1/)

Blog này phân tích những lợi ích vượt trội khi đặt mạng phân phối nội dung (CloudFront) làm lớp chắn phía trước bộ cân bằng tải (ALB), thay vì để người dùng truy cập thẳng vào máy chủ ứng dụng. Kiến trúc này giúp tăng tốc độ phản hồi đáng kể cho người dùng ở xa, dễ dàng tích hợp các lớp bảo mật (WAF, Shield) và tiết kiệm chi phí băng thông (Data Transfer Out) từ hệ thống gốc.

### [Blog 2 - Thêm HTTP Security Headers Bằng Amazon CloudFront](3.2-Blog2/)

Blog này đề xuất cách bảo vệ ứng dụng web khỏi các cuộc tấn công phổ biến (như XSS) bằng cách gắn các mã bảo mật (HTTP security headers) ở ngay rìa mạng (Edge) thông qua CloudFront. Bài viết trình bày 3 phương pháp triển khai (Response Headers Policies, CloudFront Functions, Lambda@Edge) giúp tự động hóa lớp phòng thủ này mà không cần phải can thiệp sửa đổi mã nguồn trên máy chủ gốc.



### [Blog 3 - Tối Ưu Hóa Kiến Trúc Mạng Với Amazon VPC Regional NAT Gateway](3.3-Blog3/)

Blog này giới thiệu giải pháp sử dụng một NAT Gateway chung cho toàn bộ hệ thống mạng VPC (Regional NAT Gateway) thay vì phải tạo nhiều NAT Gateway lẻ tẻ cho từng khu vực (Availability Zone). Đây là kiến trúc giúp đơn giản hóa mạng lưới, bảo mật tốt hơn khi không cần đưa tài nguyên ra public subnet, đồng thời tự động quản lý IP để chống cạn kiệt cổng kết nối và tối ưu chi phí vận hành.