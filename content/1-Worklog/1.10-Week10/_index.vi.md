---
title: "Worklog Tuần 10"
date: 2026-06-25
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Nghiên cứu lý thuyết về AWS WAF và cơ chế tích hợp cùng Amazon CloudFront.
* Thực hành cấu hình Web ACLs trên AWS WAF để tối ưu bảo mật cho hệ thống.
* Rà soát, kiểm thử diện rộng và khắc phục triệt để các lỗi phát sinh trên các tính năng đã triển khai.
* Nghiên cứu tài liệu và hoàn thiện 03 bài blog.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - Tìm hiểu lý thuyết cơ bản về AWS WAF (Web Application Firewall).<br> - Nghiên cứu cơ chế hoạt động và cách WAF kết hợp với Amazon CloudFront để bảo vệ ứng dụng ở rìa mạng (Edge Location). | 19/06/2026 | 19/06/2026 | <https://docs.aws.amazon.com/waf/latest/developerguide/cloudfront-features.html> |
| 7 | - **Thực hành:** Cấu hình Bảo mật WAF.<br>&emsp;+ Khởi tạo Web ACLs trên bộ quản lý AWS WAF.<br>&emsp;+ Cấu hình các rule bảo mật cơ bản và tiến hành liên kết WAF trực tiếp với CloudFront Distribution của dự án. | 20/06/2026 | 20/06/2026 | |
| CN |Nghỉ| 21/06/2026 | 21/06/2026 | |
| 2 | - **Thực hành:** Kiểm tra lại hệ thống.<br>&emsp;+ Thực hiện kiểm thử lại toàn bộ các chức năng đã triển khai (đề thi, lịch sử thi, flashcard, quản lý tài khoản).<br>&emsp;+ Ghi nhận các lỗi logic và lỗi giao diện phát sinh. <br> - **Thực hành:** Khắc phục lỗi phát sinh.<br>&emsp;+ Tập trung sửa các bug liên quan đến Backend API và Frontend UI từ kết quả kiểm thử.<br>&emsp;+ Đảm bảo các luồng chức năng chính vận hành ổn định, mượt mà. | 22/06/2026 | 22/06/2026 | |
| 3 | - **Thực hành:** Soạn thảo Blog (Bài 1).<br>&emsp;+ Nghiên cứu tài liệu và hoàn thành bài viết: **Tối Ưu Hóa Kiến Trúc Mạng Với Amazon VPC Regional NAT Gateway**. | 23/06/2026 | 23/06/2026 | |
| 4 | - **Thực hành:** Soạn thảo Blog (Bài 2).<br>&emsp;+ Nghiên cứu tài liệu và hoàn thành bài viết: **Thêm HTTP Security Headers Bằng Amazon CloudFront**. | 24/06/2026 | 24/06/2026 | |
| 5 | - **Thực hành:** Soạn thảo Blog (Bài 3).<br>&emsp;+ Nghiên cứu tài liệu và hoàn thành bài viết: **Lợi Ích Khi Kết Hợp Amazon CloudFront với Application Load Balancer**. | 25/06/2026 | 25/06/2026 | |

### Kết quả đạt được tuần 10:

* Nắm cơ bản khái niệm về AWS WAF và cơ chế bảo mật kết hợp giữa WAF và Amazon CloudFront.
* Triển khai thành công AWS WAF cho CloudFront, thiết lập được lớp rào chắn bảo mật ban đầu đơn giản để bảo vệ hệ thống trước các truy cập độc hại.
* Dành 02 ngày để kiểm thử và sửa sạch các lỗi phát sinh.
* Nghiên cứu tài liệu và hoàn thiện đúng tiến độ 03 bài blog kỹ thuật: "Tối Ưu Hóa Kiến Trúc Mạng Với Amazon VPC Regional NAT Gateway", "Thêm HTTP Security Headers Bằng Amazon CloudFront", và "Lợi Ích Khi Kết Hợp Amazon CloudFront với Application Load Balancer".