---
title : "Triển khai Auto Scaling Group"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

#### Triển khai Auto Scaling Group

Trong phần này, mình sẽ triển khai Amazon EC2 Auto Scaling để tự động quản lý số lượng EC2 Instance theo nhu cầu sử dụng của hệ thống. Trước tiên, mình sẽ tạo Launch Template từ AMI đã chuẩn bị ở các bước trước để làm mẫu khởi tạo EC2. Sau đó, mình sẽ cấu hình Target Group và liên kết với Application Load Balancer (ALB) nhằm phân phối lưu lượng truy cập đến các EC2 trong Auto Scaling Group.

#### Nội dung

- [Tạo Launch Template](5.6.1-launch-template/)
- [Tạo Target Group](5.6.2-target-group/)
- [Tạo Application Load Balancer](5.6.3-load-balancer/)
- [Tạo Auto Scaling Group](5.6.4-auto-scaling-group/)