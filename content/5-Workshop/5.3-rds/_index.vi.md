---
title : "Triển khai Amazon RDS"
date : 2026-07-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

#### Triển khai Amazon RDS

Trong phần này, mình sẽ tạo một Amazon RDS SQL Server để lưu trữ dữ liệu cho ứng dụng. Cơ sở dữ liệu sẽ được triển khai theo mô hình Multi-AZ, bao gồm một Primary DB Instance và một Standby DB Instance ở hai Availability Zone khác nhau nhằm tăng tính sẵn sàng và khả năng phục hồi khi xảy ra sự cố.

Để tăng cường bảo mật, RDS sẽ được đặt trong Private Subnet, sử dụng DB Subnet Group và chỉ cho phép truy cập từ Security Group của EC2.

#### Nội dung

- [Tạo DB Subnet Group](5.3.1-subnet-group/)
- [Tạo Amazon RDS MySQL Multi-AZ](5.3.2-create-rds/)