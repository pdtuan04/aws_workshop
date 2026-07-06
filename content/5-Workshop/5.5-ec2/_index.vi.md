---
title : "Triển khai EC2 để tạo AMI"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

#### Triển khai EC2 để tạo AMI

Trong phần này, mình sẽ tạo một Amazon EC2 tạm thời để chuẩn bị môi trường chạy ứng dụng. Trên EC2 sẽ cài đặt các thành phần cần thiết như Docker, Docker Compose và AWS CodeDeploy Agent. Sau khi hoàn tất cài đặt, mình sẽ triển khai thử ứng dụng bằng Docker để kiểm tra môi trường đã được cấu hình chính xác và ứng dụng có thể hoạt động bình thường.

Sau khi xác nhận EC2 đã sẵn sàng, mình sẽ tạo một Amazon Machine Image (AMI) từ instance này. AMI sẽ được sử dụng làm Launch Template cho Auto Scaling Group ở các bước tiếp theo, giúp các EC2 mới khởi tạo đều có sẵn môi trường cần thiết và rút ngắn thời gian triển khai.

#### Nội dung

- [Tạo EC2 Instance](5.2.1-create-ec2/)
- [Cài đặt Docker và Docker Compose](5.2.2-install-docker/)
- [Triển khai và kiểm tra ứng dụng](5.2.3-test-application/)
- [Cài đặt AWS CodeDeploy Agent](5.2.4-install-codedeploy-agent/)
- [Tạo Amazon Machine Image (AMI)](5.2.5-create-ami/)