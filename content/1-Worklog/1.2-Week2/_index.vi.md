---
title: "Worklog Tuần 2"
date: 2026-04-30
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:
* Làm quen và sử dụng được AWS CLI.
* Triển khai thành công ứng dụng web mẫu (Node.js) kết nối với cơ sở dữ liệu quan hệ (RDS) trên AWS.
* Xây dựng kiến trúc hệ thống có tính sẵn sàng cao (High Availability) và khả năng tự động mở rộng (Auto Scaling).
* Đảm bảo an toàn dữ liệu và tối ưu hóa luồng công việc vận hành với AWS CLI và AWS Backup.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - Cài đặt AWS Command Line Interface <br> - Học và sử dụng AWS CLI để tương tác, truy xuất thông tin và quản lý các dịch vụ AWS thay vì chỉ dùng Console. | 24/04/2026 | 24/04/2026 | <https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html> <https://000011.awsstudygroup.com/>|
| 7 | - **Thực hành:**  Thiết lập ứng dụng mẫu cơ bản trên dịch vụ EC2<br>&emsp; + Cấu hình mạng cho hệ thống <br>&emsp; +Thiết lập EC2 instance sử dụng hệ điều hành Amazon Linux.  <br>&emsp; +  Cấu hình Security Group cho EC2  <br>&emsp; +  Triển khai ứng dụng Node.js cơ bản lên máy chủ EC2  <br>&emsp; +  Kiểm tra ứng dụng đã hoạt động hay chưa. | 25/04/2026 | 25/04/2026 | <https://000004.awsstudygroup.com/> |
| CN | - **Thực hành:** Thiết lập database với RDS cho ứng dụng mẫu<br>&emsp; + Cấu hình lại ứng dụng mẫu hôm trước. <br>&emsp; + Cấu hình Subnet Group cho database <br>&emsp; + Thiết lập RDS Database instance cho ứng dụng. <br>&emsp; + Cấu hình Security Group để cho phép EC2 kết nối an toàn vào RDS. | 26/04/2026 | 26/04/2026 | <https://000005.awsstudygroup.com/> |
| 2 |- Tìm hiểu lý thuyết về khả năng mở rộng khi có lưu lượng cao <br>&emsp; + Target Group <br>&emsp; + Elastic Load Balancing <br>&emsp; + Auto Scaling Group| 27/04/2026 | 27/04/2026 | <https://000006.awsstudygroup.com/> |
| 3 | - **Thực hành:** Thiết lập Launch Templates<br>&emsp; + Cấu hình lại ứng dụng cũ đã làm hôm trước. <br>&emsp; + Đóng gói cấu hình của EC2 instance (AMI có sẵn Node.js app, Instance type, Key pair, Security Group) để chuẩn bị cho Auto Scaling. | 28/04/2026 | 28/04/2026 | <https://000006.awsstudygroup.com/> |
| 4 | - **Thực hành:** Load Banlancer, Auto Scaling & Notification (SNS) <br>&emsp; + Cấu hình Elastic Load Balancing <br>&emsp; + Thiết lập Elastic Load Balancing.<br>&emsp; + Cấu hình Target Group và Routing để tự động phân phối lưu lượng truy cập từ người dùng đến nhiều EC2 targets. <br>&emsp; + Thiết lập Auto Scaling Group (ASG) để tự động điều chỉnh số lượng EC2 instance manual scale theo nhu cầu thực tế. <br>&emsp; + Tích hợp Amazon SNS để gửi thông báo (email) mỗi khi ASG thực hiện hành động mở rộng hoặc thu hẹp. | 29/04/2026 | 29/04/2026 | <https://000006.awsstudygroup.com/> |
| 5 | - Học lý thuyết về AWS Backup <br> - **Thực hành:** AWS Backup. <br>&emsp; + Thiết lập Backup Plan để tạo ra một kế hoạch sao lưu định kỳ (chụp Snapshot tự động) cho các tài nguyên đang hoạt động (EC2, RDS). | 30/04/2026 | 30/04/2026 | <https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html> |


### Kết quả đạt được tuần 2:
* Học và làm quen các thao tác quản lý dịch vụ đám mây thông qua giao diện dòng lệnh AWS CLI.
* Triển khai thành công ứng dụng Node.js trên EC2 và cấu hình kết nối an toàn với cơ sở dữ liệu RDS thông qua Security Group.
* Đóng gói cấu hình hệ thống bằng Launch Templates và triển khai thành công mô hình Cân bằng tải (Elastic Load Balancing) để phân phối traffic.
* Xây dựng hệ thống tự động mở rộng (Auto Scaling Group), cho phép tự động tăng/giảm số lượng EC2 instance, kết hợp gửi thông báo qua email (Amazon SNS).
* Đảm bảo an toàn dữ liệu hệ thống bằng cách cấu hình AWS Backup Plan, thiết lập lịch tự động snapshot cho EC2 và RDS.