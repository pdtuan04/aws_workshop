---
title : "Giới thiệu"
date : 2026-07-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Giới thiệu

Workshop này hướng dẫn triển khai một hệ thống Web Application trên AWS theo kiến trúc nhiều tầng (Multi-tier Architecture), đảm bảo khả năng mở rộng, tính sẵn sàng cao và bảo mật.

Hệ thống sử dụng Amazon CloudFront kết hợp AWS WAF để tăng tốc truy cập và bảo vệ ứng dụng, Application Load Balancer để phân phối lưu lượng, Amazon EC2 trong Auto Scaling Group để tự động mở rộng theo tải, Amazon RDS Multi-AZ để đảm bảo an toàn dữ liệu và Amazon ElastiCache nhằm cải thiện hiệu năng truy xuất.

Ngoài ra, workshop còn xây dựng quy trình CI/CD với GitHub Actions, DockerHub, Amazon S3 và AWS CodeDeploy, giúp tự động hóa quá trình build và triển khai ứng dụng.

#### Tổng quan về workshop

Kiến trúc của workshop bao gồm các thành phần chính:

- Amazon CloudFront phân phối nội dung đến người dùng với độ trễ thấp.
- AWS WAF bảo vệ ứng dụng trước các cuộc tấn công web phổ biến.
- Application Load Balancer (ALB) cân bằng tải giữa các EC2.
- Amazon EC2 trong Auto Scaling Group xử lý yêu cầu và tự động mở rộng khi tải tăng.
- Amazon RDS MySQL Multi-AZ lưu trữ dữ liệu với mô hình Primary - Standby.
- Amazon ElastiCache tăng tốc truy xuất dữ liệu bằng cơ chế cache.
- Amazon S3 lưu trữ các tệp media của ứng dụng và deployment artifact.
- GitHub, GitHub Actions, DockerHub và AWS CodeDeploy xây dựng quy trình CI/CD tự động.
- Amazon CloudWatch, CloudWatch Alarm và Amazon SNS giám sát hệ thống, gửi cảnh báo và hỗ trợ kích hoạt Auto Scaling.

![overview](../../images/5-Workshop/5.1-Workshop-overview/architechture.drawio.png)