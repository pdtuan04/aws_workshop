---
title: "Worklog Tuần 9"
date: 2026-06-18
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Tìm hiểu và cấu hình bộ nhớ đệm Amazon ElastiCache (Valkey).
* Khắc phục các vấn đề trong quy trình CI/CD với AWS CodeDeploy.
* Triển khai cơ chế In-Place Deployment và tự động lấy bản mới nhất về chạy trong Auto Scaling Group.
* Nghiên cứu lý thuyết và tối ưu hóa chi phí hạ tầng mạng với Region NAT Gateway.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - Tìm hiểu lý thuyết về Amazon ElastiCache.<br> - Nghiên cứu cách cấu hình ElastiCache với engine Valkey. | 12/06/2026 | 12/06/2026 | <https://aws.amazon.com/elasticache/valkey/> <https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/WhatIs.html>|
| 7 | - **Thực hành:** Cấu hình ElastiCache.<br>&emsp;+ Khởi tạo và cấu hình Amazon ElastiCache với Valkey trên AWS. | 13/06/2026 | 13/06/2026 | <https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/SubnetGroups.designing-cluster-pre.valkey.html> |
| CN | - **Thực hành:** Khắc phục lỗi CI/CD.<br>&emsp;+ Kiểm tra log và khắc phục các lỗi phát sinh trong quá trình cấu hình AWS CodeDeploy cho hệ thống CI/CD. | 14/06/2026 | 14/06/2026 | |
| 2 | - Tìm hiểu lý thuyết về cơ chế triển khai In-Place Deployment của AWS CodeDeploy.<br> - Nghiên cứu cách Auto Scaling Group hoạt động chung với Codeploy ra sao. | 15/06/2026 | 15/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/integrations-aws-auto-scaling.html> <br> <https://docs.aws.amazon.com/codedeploy/latest/userguide/tutorials-auto-scaling-group.html>|
| 3 | - **Thực hành:** Triển khai In-Place Deployment.<br>&emsp;+ Tạo Application và Deployment Group trên CodeDeploy cho luồng Inplace.<br>&emsp;+ Tiến hành lấy bản cập nhật mới nhất về theo cơ chế In-Place trong Auto Scaling Group. | 16/06/2026 | 16/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/deployment-groups.html> |
| 4 | - Nghiên cứu lý thuyết về NAT Gateway và các phương án thiết kế kiến trúc mạng tối ưu chi phí trên AWS. | 17/06/2026 | 17/06/2026 | <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html> |
| 5 | - **Thực hành:** Tối ưu chi phí hạ tầng mạng.<br>&emsp;+ Chuyển đổi các NAT Gateway truyền thống đang phân tán trên các public subnet sang sử dụng chung một Region NAT Gateway. | 18/06/2026 | 18/06/2026 | |

### Kết quả đạt được tuần 9:

* Tìm hiểu và cấu hình thành công Amazon ElastiCache với engine Valkey.
* Khắc phục các lỗi cấu hình AWS CodeDeploy, đảm bảo hệ thống CI/CD hoạt động ổn định.
* Nắm được cơ chế In-Place Deployment, khởi tạo thành công Application và Deployment Group trên CodeDeploy.
* Thực hiện zip file đưa lên S3 thành công để toàn bộ EC2 Instances trong Auto Scaling Group có thể có code mới.
* Nắm kiến thức lý thuyết về NAT Gateway và thực hiện chuyển đổi thành công sang Region NAT Gateway thay vì phải tạo 2 NAT Gateway để tối ưu hóa chi phí vận hành.