---
title: "Worklog Tuần 13"
date: 2026-07-10
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Mục tiêu tuần 13:
* Tiếp tục phát triển và hoàn thiện các tính năng của hệ thống EngExam (do thời gian thực tập được gia hạn).
* Cải thiện trải nghiệm người dùng (UI/UX) cho các trang thông tin cá nhân và danh mục đề.
* Khắc phục các lỗi liên quan đến đồng bộ dữ liệu (CQRS) và bổ sung tính năng thống kê.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - Làm lại trang thông tin tài khoản cá nhân. | 10/07/2026 | 10/07/2026 | |
| 7 | - Sửa lỗi đồng bộ dữ liệu tài khoản ở Read Side khi người dùng đăng ký bằng Google. | 11/07/2026 | 11/07/2026 | |
| CN | Nghỉ | 12/07/2026 | 12/07/2026 | |
| 2 | - Thêm tính năng search bài làm theo tên. | 13/07/2026 | 13/07/2026 | |
| 3 | - Thêm thống kê bằng biểu đồ số lượng tài khoản được tạo theo tháng, năm. | 14/07/2026 | 14/07/2026 | |
| 4 | - Thêm thống kê bằng biểu đồ số lượt làm bài theo tháng, năm. | 15/07/2026 | 15/07/2026 | |
| 5 | - Fix giao diện upload ảnh cho danh mục đề. | 16/07/2026 | 16/07/2026 | |

### Kết quả đạt được:
* Giao diện trang thông tin cá nhân và phần upload ảnh danh mục đề đã được cập nhật thân thiện và dễ sử dụng hơn.
* Lỗi đồng bộ dữ liệu khi đăng nhập bằng tài khoản Google (OAuth2) sang Read Side đã được khắc phục triệt để, đảm bảo tính nhất quán của dữ liệu.
* Người dùng có thể tìm kiếm lịch sử bài làm nhanh chóng theo tên.
* Hệ thống đã có biểu đồ thống kê trực quan hỗ trợ theo dõi lượng tài khoản mới và lượt làm bài thi theo từng tháng, năm.