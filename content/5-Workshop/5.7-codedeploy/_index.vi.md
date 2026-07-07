---
title : "Triển khai CI/CD với CodeDeploy"
date : 2026-07-01
weight : 7
chapter : false
pre : " <b> 5.7. </b> "
---

#### Triển khai CI/CD với CodeDeploy

Trong phần này, mình sẽ xây dựng quy trình CI/CD để tự động triển khai ứng dụng lên các EC2 trong Auto Scaling Group bằng AWS CodeDeploy.

Đầu tiên, mình sẽ tạo một Amazon S3 Bucket để lưu trữ deployment artifact phục vụ cho quá trình triển khai.

Mình sẽ sử dụng AWS Systems Manager Parameter Store để lưu trữ các biến môi trường của ứng dụng. Thay vì phải đăng nhập SSH vào từng EC2 để chỉnh sửa file `.env`, các biến môi trường sẽ được lấy tự động từ Parameter Store trong quá trình triển khai, giúp việc quản lý cấu hình trở nên tập trung, an toàn và dễ dàng hơn.

Tiếp theo, mình sẽ tạo CodeDeploy Application và Deployment Group, đồng thời cấu hình cơ chế triển khai In-place Deployment để cập nhật phiên bản mới trực tiếp trên các EC2 hiện có trong Auto Scaling Group.

Cuối cùng, mình sẽ thực hiện một lần triển khai thử nhằm kiểm tra toàn bộ quy trình CI/CD, từ việc lấy biến môi trường, tải deployment artifact, pull Docker image mới nhất từ Docker Hub đến khởi động lại ứng dụng trên các EC2.

#### Nội dung
- [Tạo S3 Bucket lưu Deployment Artifact](5.7.1-create-s3/)
- [Tạo Parameter Store](5.7.2-parameter-store/)
- [Tạo Application & Deployment Group](5.7.3-codedeploy-application/)
- [Cấu hình GitHub Actions](5.7.4-github-actions/)
- [Kiểm tra kết quả](5.7.5-test-cicd/)