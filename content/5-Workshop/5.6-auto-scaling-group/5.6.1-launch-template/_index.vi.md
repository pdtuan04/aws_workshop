---
title : "Tạo Launch Template"
date : 2026-07-01 
weight : 1
chapter : false
pre : " <b> 5.6.1 </b> "
---
1. Vào Launch Template ấn tạo.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/64.png)
2. Đặt tên cho nó.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/65.png)
3. Chọn My AMIs -> Owned ny me và chọn cái đã tạo ở bước trước.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/66.png)
4. Ở instance type mình vẫn chọn t3.small và key pair cho nó. Ở subnet mình không chọn gì cả. 
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/67.png)
5. Chọn Security Group dành cho EC2 mình đã tạo từ bước trước.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/68.png)
6. Mình mở tab mới tạo 1 Policy mới để có quyền truy cập S3 lấy file về.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/73.png)
7. Mình lại tiếp tục tạo 1 Role mới
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/74.png)
8. Sau đó mình thêm các permissions phục vụ cho luồng CI/CD sau này. Ở đây mình attach AmazonSSMManagedInstanceCore, AWSCodeDeployRole, và cái policy vừa mới tạo.   
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/75.png)
9. Sau đó quay trở lại Launch Template tiếp tục chọn Advanced details ở IAM Instance profile chọn cái mình vừa mới tạo.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/69.png)
10. Kéo xuống phần user data thêm đoạn sau để mỗi lần 1 máy mới đẻ ra đều lấy phiên bản mới nhất và ấn create.
```
#!/bin/bash
cd /home/ssm-user/engexam
docker compose pull
docker compose up -d --force-recreate
```
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/72.png)
Qua các bước trên mình đã có launch template