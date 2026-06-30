---
title: "Worklog Tuần 2"
date: 2026-04-30
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:

* Triển khai thành công ứng dụng web (Node.js) kết nối với cơ sở dữ liệu quan hệ (RDS) trên AWS.
* Xây dựng kiến trúc hệ thống có tính sẵn sàng cao (High Availability) và khả năng tự động mở rộng (Auto Scaling).
* Đảm bảo an toàn dữ liệu và tối ưu hóa luồng công việc vận hành với AWS CLI và AWS Backup.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - **Vận hành & Quản lý:** <br> - Nghiên cứu sâu và sử dụng AWS CLI để tương tác, truy xuất thông tin và quản lý các dịch vụ AWS thay vì chỉ dùng Console. | 24/04/2026 | 24/04/2026 | Nội bộ/AWS Docs |
| 7 | - **Thực hành Compute:** <br> - Thiết lập EC2 instance sử dụng hệ điều hành Amazon Linux. <br> - Triển khai ứng dụng Node.js cơ bản lên máy chủ EC2 và kiểm tra hoạt động. | 25/04/2026 | 25/04/2026 | Nội bộ/AWS Docs |
| CN | - **Thực hành Database:** <br> - Thiết lập RDS Database instance cho ứng dụng. <br> - Cấu hình Security Group để cho phép EC2 kết nối an toàn vào RDS. | 26/04/2026 | 26/04/2026 | Nội bộ/AWS Docs |
| 2 | - **Chuẩn bị mở rộng:** <br> - Thiết lập Launch Templates: Đóng gói cấu hình của EC2 instance (AMI có sẵn Node.js app, Instance type, Key pair, Security Group) để chuẩn bị cho Auto Scaling. | 27/04/2026 | 27/04/2026 | Nội bộ/AWS Docs |
| 3 | - **Thực hành Load Balancing:** <br> - Thiết lập Elastic Load Balancing (ELB/ALB). <br> - Cấu hình Target Group và Routing để tự động phân phối lưu lượng truy cập từ người dùng đến nhiều EC2 targets. | 28/04/2026 | 28/04/2026 | Nội bộ/AWS Docs |
| 4 | - **Thực hành Auto Scaling & Notification:** <br> - Thiết lập Auto Scaling Group (ASG) để tự động điều chỉnh số lượng EC2 instance (Scale in/Scale out) theo nhu cầu thực tế (CPU/Memory utilization). <br> - Tích hợp Amazon SNS để gửi thông báo (email) mỗi khi ASG thực hiện hành động mở rộng hoặc thu hẹp. | 29/04/2026 | 29/04/2026 | Nội bộ/AWS Docs |
| 5 | - **Bảo vệ dữ liệu:** <br> - Nghiên cứu AWS Backup. <br> - Thiết lập Backup Plan để tạo ra một kế hoạch sao lưu định kỳ (chụp Snapshot tự động) cho các tài nguyên đang hoạt động (EC2, RDS). | 30/04/2026 | 30/04/2026 | Nội bộ/AWS Docs |


### Kết quả đạt được tuần 2:

**1. Triển khai Ứng dụng & Dữ liệu:**
* Khởi tạo thành công máy chủ Amazon Linux và cấu hình môi trường chạy ứng dụng Node.js ổn định.
* Thiết lập và kết nối thành công cơ sở dữ liệu quan hệ (RDS), đảm bảo các quy tắc bảo mật (Security Group) giữa App Server và Database Server.

**2. Khả năng mở rộng & Cân bằng tải (Scalability & HA):**
* Tạo thành công Launch Templates để tiêu chuẩn hóa cấu hình máy chủ, giúp việc nhân bản EC2 trở nên tự động và nhất quán.
* Triển khai Elastic Load Balancing (ELB) giúp phân phối đều traffic người dùng, tránh tình trạng quá tải cục bộ trên một máy chủ.
* Thiết lập Auto Scaling Group (ASG) hoạt động trơn tru, giúp hệ thống tự động tăng/giảm số lượng node dựa trên tải thực tế, đồng thời cấu hình SNS để nhận cảnh báo theo thời gian thực về trạng thái mở rộng.

**3. Vận hành & Bảo vệ hệ thống:**
* Làm quen và ứng dụng hiệu quả AWS CLI vào việc tương tác với các tài nguyên AWS, tăng tốc độ quản trị.
* Hoàn thiện cơ chế an toàn dữ liệu thông qua việc tạo Backup Plan, tự động sao lưu dự phòng cho hệ thống theo lịch trình cụ thể.