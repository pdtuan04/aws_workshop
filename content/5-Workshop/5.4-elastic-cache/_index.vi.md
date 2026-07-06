---
title : "Triển khai Amazon ElastiCache"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

#### Triển khai Amazon ElastiCache

Trong phần này, mình sẽ tạo Amazon ElastiCache for Valkey để lưu trữ dữ liệu bộ nhớ đệm (cache) cho ứng dụng. ElastiCache sẽ được triển khai với mô hình Primary Node và Replica Node nhằm tăng khả năng đọc dữ liệu, giảm tải cho cơ sở dữ liệu Amazon RDS và hỗ trợ tự động chuyển đổi (Failover) khi Primary Node gặp sự cố.

Để đảm bảo an toàn, ElastiCache sẽ được triển khai trong Private Subnet thông qua Subnet Group và chỉ cho phép các EC2 trong hệ thống kết nối bằng Security Group.

#### Nội dung

- [Tạo ElastiCache Subnet Group](5.4.1-subnet-group/)
- [Tạo Amazon ElastiCache for Valkey](5.4.2-create-elasticache/)