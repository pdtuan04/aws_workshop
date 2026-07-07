---
title : "Tạo Parameter Store"
date : 2026-07-01
weight : 2
chapter : false
pre : " <b> 5.7.2 </b> "
---
1. Vào AWS Systems Manager -> Parameter Store -> Create
![overview](../../../images/5-Workshop/5.7-codedeploy/120.png)
2. Mình đặt tên cho nó.
![overview](../../../images/5-Workshop/5.7-codedeploy/121.png)
4. Ở đây với những cái secret thì mình tick vào SecureString để mã hóa và nhập giá trị cho nó.
![overview](../../../images/5-Workshop/5.7-codedeploy/122.png)
5. Đối với các giá trị không cần bảo mật mình cứ đặt tên bình thường
![overview](../../../images/5-Workshop/5.7-codedeploy/123.png)
6. Nhưng ở đây type dùng String bình thường thôi.
![overview](../../../images/5-Workshop/5.7-codedeploy/124.png)
Sau khi tạo xong mình đã các các giá trị rồi.
![overview](../../../images/5-Workshop/5.7-codedeploy/125.png)
7. Mình tiếp tục cập nhật lại policy `CodeDeployDemo-EC2-Permissions` để cấp quyền cho các EC2 đọc các giá trị được lưu trong AWS Systems Manager Parameter Store
![overview](../../../images/5-Workshop/5.7-codedeploy/128.png)
8. Ấn JSON và ấn Edit lại
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "s3:Get*",
        "s3:List*"
      ],
      "Effect": "Allow",
      "Resource": "*"
    },
    {
      "Sid": "AllowParameterStoreRead",
      "Effect": "Allow",
      "Action": [
        "ssm:GetParameters",
        "ssm:GetParameter",
        "ssm:GetParametersByPath"
      ],
      "Resource": "*"
    }
  ]
}
```
![overview](../../../images/5-Workshop/5.7-codedeploy/129.png)
9. Xem lại thay đổi và lưu.
![overview](../../../images/5-Workshop/5.7-codedeploy/130.png)