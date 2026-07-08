---
title : "Triển khai VPC và Networking"
date : 2026-07-01
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

# Triển khai VPC và Networking

## Tổng quan

Trong phần này, sẽ xây dựng hạ tầng mạng làm nền tảng cho toàn bộ hệ thống Web Application trên AWS. Kiến trúc mạng được thiết kế theo mô hình nhiều tầng (Multi-tier Architecture), trong đó các tài nguyên được phân tách thành Public Subnet và Private Subnet nhằm tăng cường tính bảo mật và khả năng mở rộng.

Các thành phần như Application Load Balancer sẽ được triển khai trong Public Subnet để tiếp nhận lưu lượng từ Internet và cung cấp kết nối ra ngoài cho các tài nguyên nội bộ. Trong khi đó, Amazon EC2, Amazon RDS và Amazon ElastiCache sẽ được đặt trong Private Subnet để hạn chế truy cập trực tiếp từ Internet.
Sử dụng Regional Nat Gateway để đi internet thay vì tạo nhiều Nat Gateway ở nhiều AZ.
Sau khi hoàn thành phần này, bạn sẽ có một hạ tầng mạng sẵn sàng để triển khai các dịch vụ của hệ thống ở các bước tiếp theo.

## Nội dung

1. [Tạo VPC và cấu hình Networking](5.2.1-create-vpc-nat-subnet/)
2. [Tạo Security Group](5.2.2-create-security-group/)