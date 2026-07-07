---
title : "Cấu hình Security Group"
date : 2026-07-01
weight : 3
chapter : false
pre : " <b> 5.2.2 </b> "
---

1. Tạo Secutiry Group cho EC2.
- Vào VPC và chọn Security Group và ấn Create
- Đặt tên
- Chọn VPC
- Chỉ mở Port 8082 để truy cập vào app.
![overview](../../../images/5-Workshop/5.2-vpc-networking/10.png)

2. Tạo Secutiry Group cho Database.
- Vào VPC và chọn Security Group và ấn Create
- Đặt tên
- Chọn VPC
![overview](../../../images/5-Workshop/5.2-vpc-networking/11.png)
- Chỉ mở Port 1433 để truy cập vào database.
- Source thay vì chọn 0.0.0.0/0 thì mình chọn SG EC2 để giới hạn chỉ được EC2 truy cập tới thôi.
![overview](../../../images/5-Workshop/5.2-vpc-networking/12.png)

3. Tạo Secutiry Group cho Elastic Cache.

- Tương tự mình cũng chỉ mở Port 6379 và source mình chọn SG EC2.
![overview](../../../images/5-Workshop/5.2-vpc-networking/13.png)

4. Tạo Secutiry Group cho Application Load Balancer.
- Ở đây mình mở port 80 và source mình đặt 0.0.0.0/0.
![overview](../../../images/5-Workshop/5.2-vpc-networking/14.png)