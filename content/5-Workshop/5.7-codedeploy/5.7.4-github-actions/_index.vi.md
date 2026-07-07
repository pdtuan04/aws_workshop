---
title : "Cấu hình GitHub Actions"
date : 2026-07-01
weight : 4
chapter : false
pre : " <b> 5.7.4 </b> "
---
1. Vào Github phần Setting -> Secrets and variables -> Action 
![overview](../../../images/5-Workshop/5.7-codedeploy/142.png)
2. Ấn vào New repository secret.
![overview](../../../images/5-Workshop/5.7-codedeploy/143.png)

3. Mình cần lấy `AWS_ACCESS_KEY_ID` và `AWS_SECRET_ACCESS_KEY` khi tạo Access Key sẽ được 1 file .csv gửi về máy mở nó lên và điền tương ứng vào
![overview](../../../images/5-Workshop/5.7-codedeploy/144.png)
4. Cứ như vậy điền hết các biến cần thiết vào
- `AWS_ACCESS_KEY_ID` – Access Key của IAM User.
- `AWS_SECRET_ACCESS_KEY` – Secret Access Key của IAM User.
- `AWS_REGION` – Region triển khai AWS.
- `AWS_S3_BUCKET_NAME` – Tên S3 Bucket lưu deployment artifact.
- `AWS_APPLICATION_NAME` – Tên CodeDeploy Application.
- `AWS_DEPLOYMENT_GROUP_NAME` – Tên Deployment Group của CodeDeploy.
- `DOCKER_USERNAME` – Tên đăng nhập Docker Hub.
- `DOCKERHUB_TOKEN` – Access Token của Docker Hub.
- `DOCKERHUB_PROJECT_NAME` – Tên repository trên Docker Hub.
- `VITE_API_URL` – Địa chỉ API của ứng dụng.
- `VITE_GOOGLE_CLIENT_ID` – Google OAuth Client ID.
- `VITE_TINYMCE_API_KEY` – API Key của TinyMCE.
- ![overview](../../../images/5-Workshop/5.7-codedeploy/143.png)