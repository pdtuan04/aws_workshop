---
title : "Tạo CodeDeploy Application"
date : 2026-07-01
weight : 3
chapter : false
pre : " <b> 5.7.3 </b> "
---

1. Vào CodeDeploy ấn tạo application đặt tên và chọn Compute platform là EC2/On-premises và ấn tạo.
![overview](../../../images/5-Workshop/5.7-codedeploy/136.png) 
2. Mở tab mới mình vào IAM tạo 1 role `CodeDeployServiceRole` và attach cho nó các permission.
![overview](../../../images/5-Workshop/5.7-codedeploy/131.png)
3. Mình attach cho IAM Role các permission `AmazonS3ReadOnlyAccess`, `AmazonSSMManagedInstanceCore`, `AWSCodeDeployRole`.
4. Thêm policy `CodeDeployDemo-EC2-Permissions` đã tạo và được edit lại ở bước trước.
5. Mình sẽ create inline policy `CodeDeployFixASGLifecycle` chọn JSON và thêm đoạn JSON này vào.
![overview](../../../images/5-Workshop/5.7-codedeploy/134.png)
```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "CodeDeployASGIntegrationStrictPermissions",
			"Effect": "Allow",
			"Action": [
				"iam:PassRole",
				"ec2:CreateTags",
				"ec2:RunInstances",
				"autoscaling:CompleteLifecycleAction",
				"autoscaling:DeleteLifecycleHook",
				"autoscaling:PutLifecycleHook",
				"autoscaling:RecordLifecycleActionHeartbeat",
				"autoscaling:DescribeAutoScalingGroups",
				"autoscaling:DescribeLifecycleHooks"
			],
			"Resource": "*"
		}
	]
}
```
![overview](../../../images/5-Workshop/5.7-codedeploy/135.png)
![overview](../../../images/5-Workshop/5.7-codedeploy/132.png)
6. Sau khi có đầy đủ các policy rồi. Tiếp tục tạo Deployment Group cho application.
- Đặt tên và chọn Role `CodeDeployServiceRole` vừa tạo.
![overview](../../../images/5-Workshop/5.7-codedeploy/127.png)
7. Deployment type mình chọn In-place.
![overview](../../../images/5-Workshop/5.7-codedeploy/137.png)
8. Mình tiếp tục phần Deploy configuration chọn AllAtOne và tick vào Enable Load Balancing.
![overview](../../../images/5-Workshop/5.7-codedeploy/138.png)
9. Mình  tick vào Application Load Balancer và chọn target group của mình và ấn Create.
![overview](../../../images/5-Workshop/5.7-codedeploy/140.png)
Qua các bước trên mình đã có 1 Deployment Group rồi.
![overview](../../../images/5-Workshop/5.7-codedeploy/141.png)