---
title: "Worklog Tuần 1"
date: 2026-04-23
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---


### Mục tiêu tuần 1:

* Kết nối, làm quen với các thành viên mới trong First Cloud Journey.
* Hiểu dịch vụ AWS cơ bản, cách dùng các dịch vụ cơ bản.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 6   |- Làm quen với các thành viên FCJ và tìm kiếm thành viên cho nhóm. <br> - Đọc và lưu ý các nội quy, quy định tại đơn vị thực tập<br> - Tạo AWS Free Tier account <br> - Tìm hiểu AWS Console <br>- Chuẩn bị các tài nguyên cần thiết để thực hiện các bài lab với nhiệm vụ để nhận 200$ credit.<br> - Xem cách vẽ sơ đồ kiến trúc AWS với draw.io.                                                                                  | 17/04/2026   | 17/04/2026      | <https://000001.awsstudygroup.com/> <br> <https://youtu.be/l8isyDe-GwY>|
| 7   |- Thực hành: Thiết lập các Billing Alerts cơ bản để kiểm soát số credit trong tài khoản.<br>&emsp; + Gửi mail bill về hàng ngày, tháng. <br>&emsp; + Gửi mail cảnh báo vượt mức đã quy định| 18/04/2026   | 18/04/2026      | <https://000007.awsstudygroup.com/> <br> <https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html> |
| CN   |- Thực hành: Quản trị quyền truy cập với AWS Identity and Access Management (IAM)<br>&emsp; + Tạo IAM Group và IAM User.<br>&emsp; + Tạo IAM Role và IAM User.<br>| 19/04/2026   | 19/04/2026      | <https://000002.awsstudygroup.com/> |
| 2   |- Nghiên cứu lý thuyết về hạ tầng mạng cơ bản của AWS <br>&emsp; + Region <br>&emsp; + VPC <br>&emsp; + Subnet <br>&emsp; + Internet Gateway <br>&emsp; + Route Table <br>&emsp; + Security Group<br>                                            | 20/04/2026   | 20/04/2026      | <https://000003.awsstudygroup.com/> |
| 3   | - **Thực hành:** Cấu hình các thành phần mạng  <br>&emsp; + VPC <br>&emsp; + Subnet <br>&emsp; + Internet Gateway <br>&emsp; + Route Table <br>&emsp; + Security Group<br> - Tìm hiểu về NAT Gateway | 21/04/2026   | 21/04/2026      | <https://000003.awsstudygroup.com/> |
| 4   | - Tìm hiểu EC2 cơ bản: <br>&emsp; + Instance types <br>&emsp; + AMI <br>&emsp; + Launch Instance| 22/04/2026   | 22/04/2026      | <https://000003.awsstudygroup.com/> |
| 5   | - **Thực hành:** <br>&emsp; + Tạo EC2 instance bên trong các public subnet, private subnet. <br>&emsp;+ SSH vào EC2 bên trong public subnet để kiểm tra kết nối. <br>&emsp; + Cấu hình NAT Gateway để máy chủ EC2 Private trong private subnet đi ra internet. <br>&emsp; + SSH gián tiếp từ EC2 ở public subnet sang EC2 ở private subnet bằng file .pem để kiểm tra kết nối đi ra internet.                                                                                          | 23/04/2026   | 23/04/2026      | <https://000003.awsstudygroup.com/> |


### Kết quả đạt được tuần 1:

* Hoàn thiện môi trường thực hành: Tạo thành công tài khoản AWS (với 200$ credit), làm quen AWS Console, draw.io và lập nhóm làm việc.

* Tối ưu hóa quản trị rủi ro chi phí bằng cách cấu hình chi tiết hệ thống Billing Alerts (gửi mail báo cáo hàng ngày/tháng và cảnh báo vượt hạn mức).

* Đảm bảo nguyên tắc đặc quyền tối thiểu (Least Privilege) trong phân quyền thông qua việc thiết lập và quản lý các tài nguyên AWS IAM (Group, User, Role).

* Xây dựng thành công hạ tầng mạng AWS VPC cốt lõi, bao gồm việc quy hoạch Public/Private Subnet, cấu hình Route Table, Internet Gateway và Security Group.

* Triển khai mô hình máy chủ an toàn: Tạo EC2 instance trên cả 2 Subnet, thiết lập NAT Gateway cấp quyền truy cập Internet cho Private subnet và kiểm thử thành công luồng SSH gián tiếp từ Public sang Private bằng file .pem.


