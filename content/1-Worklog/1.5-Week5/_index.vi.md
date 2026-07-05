---
title: "Worklog Tuần 5"
date: 2026-05-21
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu và tích hợp dịch vụ lưu trữ AWS S3 cùng mạng phân phối nội dung CloudFront.
* Xây dựng chức năng gửi thư điện tử (email) và tính năng flashcard hỗ trợ học tập.
* Áp dụng CI/CD cơ bản để tự động hóa quy trình build và lưu trữ Docker image trên AWS ECR.
* Triển khai cơ sở dữ liệu trên AWS RDS và tìm hiểu về Auto Scaling.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - Tìm hiểu lý thuyết cơ bản về dịch vụ lưu trữ Object Storage của AWS S3.<br> - Nghiên cứu cách hoạt động của mạng phân phối nội dung (CDN) CloudFront và cách kết hợp với S3. | 15/05/2026 | 15/05/2026 | <https://aws.amazon.com/blogs/networking-and-content-delivery/amazon-s3-amazon-cloudfront-a-match-made-in-the-cloud/> |
| 7 | - **Thực hành:** Tích hợp S3 và CloudFront.<br>&emsp;+ Xây dựng API upload file tĩnh (hình ảnh, tài liệu) lên AWS S3.<br>&emsp;+ Cấu hình kết hợp CloudFront để người dùng truy cập qua đó mà không truy cập trực tiếp S3. | 16/05/2026 | 16/05/2026 | <https://000094.awsstudygroup.com/> |
| CN | - **Thực hành:** Chức năng Email.<br>&emsp;+ Tìm hiểu các thư viện hỗ trợ gửi mail trong ứng dụng backend.<br>&emsp;+ Xây dựng API gửi mail (mail chào mừng, mail thông báo). | 17/05/2026 | 17/05/2026 | |
| 2 | - **Thực hành:** Chức năng Flashcard.<br>&emsp;+ Thiết kế cấu trúc bảng và quan hệ dữ liệu cho tính năng flashcard.<br>&emsp;+ Xây dựng các API cơ bản (CRUD) để quản lý flashcard. | 18/05/2026 | 18/05/2026 |  |
| 3 | - **Thực hành:** CI/CD và Container Registry.<br>&emsp;+ Triển khai quy trình CI/CD cho dự án để tự động hóa các bước build và test mã nguồn cơ bản bằng cách SSH vào EC2. | 19/05/2026 | 19/05/2026 | |
| 4 | - **Thực hành:** Triển khai Database và sử dụng ECR.<br>&emsp;+ Kết nối ứng dụng với cơ sở dữ liệu đã được khởi tạo trên AWS RDS.<br>&emsp;+ Cấu hình chuỗi kết nối an toàn và chạy migration để cập nhật các bảng dữ liệu mới.<br>&emsp;+ Viết file Seed data cơ bản cho ứng dụng khi mới khởi tạo. <br>&emsp;+ Thực hiện build và push Docker image lên AWS ECR với AWS CLI.| 20/05/2026 | 20/05/2026 |  |
| 5 | - Ôn lại lý thuyết về cơ chế hoạt động của Auto Scaling trên AWS.<br> - Nghiên cứu các bước cơ bản để cấu hình nhóm Auto Scaling nhằm tự động thêm/bớt máy chủ theo mức độ sử dụng với 3 cơ chế Scale (Manual Scale, Dynamic Scaling, Scheduled Scaling). | 21/05/2026 | 21/05/2026 | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html> |

### Kết quả đạt được tuần 5:

* Hoàn thành việc tìm hiểu và tích hợp API cho phép upload file lên AWS S3, kết hợp với CloudFront để trả về nội dung tĩnh.
* Hoàn thành xây dựng API gửi email và các API quản lý tính năng flashcard theo đúng thiết kế ban đầu.
* Thực hiện được quy trình CI/CD cơ bản với SSH để pull images mới về.
* Test và push thử Docker image lên kho lưu trữ AWS ECR.
* Kết nối thành công backend với cơ sở dữ liệu trên AWS RDS và thực thi cấu trúc dữ liệu mới.
* Bước đầu tiếp cận và có khái niệm cơ bản về cách AWS Auto Scaling hoạt động để chuẩn bị cho các bài toán mở rộng hệ thống sau này.