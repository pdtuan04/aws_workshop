---
title: "Worklog Tuần 6"
date: 2026-05-28
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Khắc phục các lỗi (bugs) còn tồn đọng liên quan đến đề thi và lưu trữ file S3.
* Bổ sung các tính năng cơ bản cho người dùng: Quản lý tài khoản và Reset mật khẩu.
* Xây dựng tính năng bình luận phân cấp.
* Tìm hiểu và ứng dụng Message Queue (RabbitMQ) kết hợp Outbox Pattern để đồng bộ dữ liệu giữa các cơ sở dữ liệu.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - **Thực hành:** Sửa lỗi hệ thống.<br>&emsp;+ Khắc phục lỗi trong chức năng tạo đề thi.<br>&emsp;+ Xử lý lỗi phát sinh khi upload file lên Amazon S3 để đảm bảo luồng file hoạt động ổn định. | 22/05/2026 | 22/05/2026 |  |
| 7 | - **Thực hành:** Tính năng người dùng.<br>&emsp;+ Xây dựng API chức năng quản lý tài khoản.<br>&emsp;+ Xây dựng tính năng reset password cho người dùng (tích hợp với API gửi mail đã làm ở tuần trước). | 23/05/2026 | 23/05/2026 |  |
| CN | - Tìm hiểu lý thuyết về Message Broker và RabbitMQ.<br> - Nghiên cứu thư viện MassTransit trong .NET.<br> - Tìm hiểu cơ chế hoạt động của Outbox Pattern trong việc giải quyết bài toán đồng bộ dữ liệu phân tán. | 24/05/2026 | 24/05/2026 | <https://masstransit.io/documentation/concepts> |
| 2 | - **Thực hành:** Tối ưu Database & Cài đặt Queue.<br>&emsp;+ Phân tích và tối ưu lại read database phục vụ riêng cho các tác vụ đọc dữ liệu.<br>&emsp;+ Cài đặt RabbitMQ và cấu hình MassTransit vào dự án. | 25/05/2026 | 25/05/2026 |  |
| 3 | - **Thực hành:** Đồng bộ dữ liệu CQRS.<br>&emsp;+ Cấu hình Outbox Pattern để lưu trữ các sự kiện (events) an toàn.<br>&emsp;+ Sử dụng MassTransit và RabbitMQ để publish/consume messages, thực hiện đồng bộ dữ liệu từ write database sang read database. <br>&emsp;+ Đồng bộ lại dữ liệu cache khi dữ liệu có thay đổi.| 26/05/2026 | 26/05/2026 | <https://masstransit.io/documentation/patterns/outbox> |
| 4 | - **Thực hành:** Tính năng Comment.<br>&emsp;+ Phân tích thiết kế bảng dữ liệu cho tính năng comment phân cấp.<br>&emsp;+ Xây dựng các API cơ bản (thêm, sửa, xóa comment). | 27/05/2026 | 27/05/2026 | |
| 5 | - **Thực hành:** Tính năng Comment & Kiểm thử.<br>&emsp;+ Hoàn thiện luồng truy vấn để lấy danh sách comment phân cấp.<br>&emsp;+ Kiểm thử lại toàn bộ luồng đồng bộ dữ liệu qua RabbitMQ và các tính năng mới xây dựng. | 28/05/2026 | 28/05/2026 |  |

### Kết quả đạt được tuần 6:

* Sửa lỗi thành công cho chức năng tạo đề thi và upload file lên AWS S3, giúp hệ thống hoạt động.
* Hoàn thành API quản lý tài khoản và luồng reset mật khẩu an toàn qua email.
* Tìm hiểu được các khái niệm cơ bản về Message Broker (RabbitMQ) và Outbox Pattern.
* Tối ưu lại read database.
* Bước đầu cấu hình thành công MassTransit và RabbitMQ để đồng bộ dữ liệu từ Write Database sang Read Database, giảm thiểu rủi ro mất mát dữ liệu khi hệ thống có sự cố.
* Thiết kế và xây dựng được cấu trúc dữ liệu cùng API cho tính năng bình luận phân cấp.