---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Triển khai hệ thống Web Application có khả năng mở rộng và bảo mật trên AWS

#### Tổng quan
Trong các hệ thống web hiện đại, việc đảm bảo tính sẵn sàng (High Availability), khả năng mở rộng (Scalability) và bảo mật (Security) là những yêu cầu quan trọng. AWS cung cấp nhiều dịch vụ giúp xây dựng kiến trúc đáp ứng các yêu cầu này với chi phí tối ưu và khả năng tự động hóa cao.

Trong workshop này, chúng ta sẽ xây dựng một hệ thống triển khai website trên AWS theo mô hình nhiều tầng (Multi-tier Architecture). Hệ thống sử dụng CloudFront kết hợp AWS WAF để tăng tốc truy cập và bảo vệ ứng dụng khỏi các cuộc tấn công phổ biến. Lưu lượng truy cập sẽ được chuyển đến Application Load Balancer (ALB), sau đó phân phối đến các máy chủ EC2 nằm trong Auto Scaling Group để đảm bảo khả năng chịu tải và tự động mở rộng.

Dữ liệu của ứng dụng được lưu trữ trên Amazon RDS với mô hình Primary - Standby (Multi-AZ) nhằm đảm bảo tính sẵn sàng cao. Đồng thời, Amazon ElastiCache for Valkey/Redis được sử dụng để tăng tốc độ truy xuất dữ liệu và giảm tải cho cơ sở dữ liệu.

Quá trình triển khai ứng dụng được tự động hóa thông qua GitHub Actions, DockerHub, Amazon S3 và AWS CodeDeploy, giúp rút ngắn thời gian phát hành phiên bản mới và giảm thiểu thao tác thủ công.

#### Nội dung

1. [Tổng quan kiến trúc hệ thống](5.1-Architecture/)
2. [VPC ](5.2-vpc-networking/)
3. [Triển khai VPC và Networking](5.3-Network/)
4. [Triển khai EC2 và Auto Scaling Group](5.4-Compute/)
5. [Cấu hình Application Load Balancer](5.5-ALB/)
6. [Triển khai Amazon RDS Multi-AZ](5.6-RDS/)
7. [Triển khai Amazon ElastiCache](5.7-ElastiCache/)
8. [Cấu hình CloudFront và AWS WAF](5.8-CloudFront-WAF/)
9. [Thiết lập CI/CD với GitHub Actions, DockerHub và CodeDeploy](5.9-CICD/)
10. [Giám sát hệ thống với CloudWatch](5.10-Monitoring/)
11. [Kiểm thử khả năng Scale và Deployment](5.11-Testing/)
12. [Dọn dẹp tài nguyên](5.12-Cleanup/)