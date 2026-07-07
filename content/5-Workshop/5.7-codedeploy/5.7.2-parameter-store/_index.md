---
title : "Create Parameter Store"
date : 2026-07-01
weight : 2
chapter : false
pre : " <b> 5.7.2 </b> "
---
1. Go to AWS Systems Manager -> Parameter Store -> Create
![overview](../../../images/5-Workshop/5.7-codedeploy/120.png)
2. I set a name for it.
![overview](../../../images/5-Workshop/5.7-codedeploy/121.png)
4. Here, for secret values, I tick SecureString to encrypt and enter its value.
![overview](../../../images/5-Workshop/5.7-codedeploy/122.png)
5. For values that do not need security, I just name them normally.
![overview](../../../images/5-Workshop/5.7-codedeploy/123.png)
6. But here the type uses normal String only.
![overview](../../../images/5-Workshop/5.7-codedeploy/124.png)
After creating, I already have all the values.
![overview](../../../images/5-Workshop/5.7-codedeploy/125.png)
7. I continue updating the policy `CodeDeployDemo-EC2-Permissions` to grant EC2 permission to read values stored in AWS Systems Manager Parameter Store.
![overview](../../../images/5-Workshop/5.7-codedeploy/128.png)
8. Click JSON and click Edit again.
```json
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
9. Review the changes and save.
![overview](../../../images/5-Workshop/5.7-codedeploy/130.png)