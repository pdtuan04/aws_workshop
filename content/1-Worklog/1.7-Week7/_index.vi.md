---
title: "Worklog Tuần 7"
date: 2026-06-04
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Thiết kế cơ sở dữ liệu và xây dựng trọn vẹn tính năng lịch sử thi (Backend & UI).
* Tìm hiểu và triển khai hệ thống Cân bằng tải (ALB) kết hợp với các giải pháp Auto Scaling trên AWS.
* Thực hiện kiểm thử sức chịu tải của hệ thống bằng Apache JMeter để xác minh khả năng tự động mở rộng.
* Thiết lập hệ thống thông báo tự động qua email sử dụng Amazon SNS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - **Thực hành:** Thiết kế dữ liệu.<br>&emsp;+ Phân tích yêu cầu về tính năng lịch sử có thể có trong hệ thống.<br>&emsp;+ Thiết kế bảng lưu lịch sử thi của người dùng. | 29/05/2026 | 29/05/2026 | |
| 7 | - **Thực hành:** Phát triển Backend.<br>&emsp;+ Xây dựng API lưu lại lịch sử thi sau khi người dùng hoàn thành.<br>&emsp;+ Xây dựng API truy xuất danh sách lịch sử thi của người dùng. | 30/05/2026 | 30/05/2026 | |
| CN | - **Thực hành:** Phát triển Frontend.<br>&emsp;+ Xây dựng giao diện (UI) hiển thị phần lịch sử làm bài cho người dùng. | 31/05/2026 | 31/05/2026 | |
| 2 | - **Thực hành:** Triển khai ALB & Auto Scaling (Phần 1).<br>&emsp;+ Cấu hình Application Load Balancer kết nối với Auto Scaling Group.<br>&emsp;+ Triển khai Manual Scaling (thêm máy chủ thủ công) và Scheduled Scaling (đặt lịch tự động thêm máy chủ). | 01/06/2026 | 01/06/2026 | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html> <br> <https://000006.awsstudygroup.com/>|
| 3 | - **Thực hành:** Triển khai Auto Scaling (Phần 2) & Cảnh báo.<br>&emsp;+ Triển khai Dynamic Scaling (tự động scale theo tải thực tế của hệ thống).<br>&emsp;+ Cấu hình chức năng tự động gửi email bằng Amazon SNS thông báo khi có một máy chủ mới được khởi tạo. | 02/06/2026 | 02/06/2026 | <https://docs.aws.amazon.com/sns/latest/dg/welcome.html> <br> <https://000006.awsstudygroup.com/>|
| 4 | - **Thực hành:** Chuẩn bị kiểm thử.<br>&emsp;+ Cài đặt công cụ Apache JMeter.<br>&emsp;+ Xây dựng kịch bản kiểm thử (Test Plan) mô phỏng lượng request lớn gửi đến hệ thống. | 03/06/2026 | 03/06/2026 | <https://jmeter.apache.org/usermanual/get-started.html> |
| 5 | - **Thực hành:** Kiểm thử hệ thống thực tế.<br>&emsp;+ Tiến hành chạy JMeter để load test cho giải pháp Auto Scaling đã thiết lập.<br>&emsp;+ Theo dõi quá trình khởi tạo máy chủ trên AWS và xác nhận email thông báo từ SNS. | 04/06/2026 | 04/06/2026 | |

### Kết quả đạt được tuần 7:

* Hoàn thành thiết kế cơ sở dữ liệu, API và giao diện UI cho tính năng lịch sử thi, cho phép người dùng xem lại kết quả bài làm.
* Cấu hình thành công Application Load Balancer (ALB) kết hợp với 3 chiến lược Auto Scaling: Manual, Scheduled và Dynamic.
* Cài đặt và ứng dụng cơ bản JMeter để giả lập tải, qua đó kiểm chứng thành công khả năng tự động mở rộng (scale out) của hệ thống.
* Tích hợp thành công dịch vụ Amazon SNS, đảm bảo hệ thống luôn tự động gửi email thông báo mỗi khi có một EC2 instance mới được tạo ra trong quá trình scale.