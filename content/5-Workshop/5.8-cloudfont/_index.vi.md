---
title : "Triển khai CloudFront"
date : 2026-07-01
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---

#### Triển khai Amazon CloudFront

Trong phần này, mình sẽ triển khai Amazon CloudFront để phân phối nội dung đến người dùng với độ trễ thấp và tăng hiệu năng truy cập. Đồng thời, Cloudfont Free Tier có AWS WAF cơ bản nhằm ngăn chặn các cuộc tấn công trước khi lưu lượng truy cập đến hệ thống.

Khác với kiến trúc ban đầu khi người dùng truy cập trực tiếp vào Application Load Balancer (ALB), CloudFront sẽ được cấu hình sử dụng ALB làm Origin. Mọi yêu cầu từ người dùng sẽ được chuyển tiếp đến CloudFront, sau đó CloudFront sẽ forward các request động đến ALB để phân phối đến các EC2 trong Auto Scaling Group.

#### Nội dung

- [Tạo CloudFront Distribution](5.8.1-create-cloudfront/)
- [Cấu hình Origin và Behavior](5.8.2-origin/)
- [Kiểm tra truy cập qua CloudFront](5.8.3-test-cloudfront/)