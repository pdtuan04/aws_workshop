---
title : "Create CodeDeploy Application"
date : 2026-07-01
weight : 3
chapter : false
pre : " <b> 5.7.3 </b> "
---

1. Go to CodeDeploy, create an application, enter a name, choose Compute platform as EC2/On-premises, and click create.
![overview](../../../images/5-Workshop/5.7-codedeploy/136.png) 
2. Open a new tab, go to IAM, create a role `CodeDeployServiceRole`, and attach permissions to it.
![overview](../../../images/5-Workshop/5.7-codedeploy/131.png)
3. I attach these permissions to the IAM Role: `AmazonS3ReadOnlyAccess`, `AmazonSSMManagedInstanceCore`, `AWSCodeDeployRole`.
4. Add the policy `CodeDeployDemo-EC2-Permissions` that was created and edited in the previous step.
5. I will create an inline policy `CodeDeployFixASGLifecycle`, choose JSON, and add this JSON block.
![overview](../../../images/5-Workshop/5.7-codedeploy/134.png)
```json
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
6. After having all required policies, continue to create a Deployment Group for the application.
- Enter a name and choose the role `CodeDeployServiceRole` just created.
![overview](../../../images/5-Workshop/5.7-codedeploy/127.png)
7. For Deployment type, I choose In-place.
![overview](../../../images/5-Workshop/5.7-codedeploy/137.png)
8. Continue to Deploy configuration, choose AllAtOne, and tick Enable Load Balancing.
![overview](../../../images/5-Workshop/5.7-codedeploy/138.png)
9. Tick Application Load Balancer, choose my target group, and click Create.
![overview](../../../images/5-Workshop/5.7-codedeploy/140.png)
Through the steps above, I now have a Deployment Group.
![overview](../../../images/5-Workshop/5.7-codedeploy/141.png)