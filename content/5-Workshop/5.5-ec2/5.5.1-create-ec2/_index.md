---
title : "Create EC2 Instance"
date : 2026-07-01
weight : 1
chapter : false
pre : " <b> 5.5.1 </b> "
---
In this section, we will create a temporary EC2 instance to generate an AMI. This instance will be deleted afterward.
1. Go to the EC2 console, click **Launch instance**, and provide a name for it. 
![overview](../../../images/5-Workshop/5.5-ec2/43.png)

2. For the instance type, select **t3.small** to have sufficient resources, and choose a key pair for it.
![overview](../../../images/5-Workshop/5.5-ec2/44.png)

3. Select your VPC and Subnet (temporarily using **Public Subnet 1** for setup), then set **Auto-assign public IP** to **Enable**.
![overview](../../../images/5-Workshop/5.5-ec2/45.png)

4. Select the Security Group designed for EC2 that we previously created in step 5.2.2.
![overview](../../../images/5-Workshop/5.5-ec2/46.png)

5. Create an IAM Role named `EngExam-EC2-SSM-Role` and attach the `AmazonSSMManagedInstanceCore` policy.
- This allows us to connect to the EC2 instance via AWS Systems Manager Session Manager without needing a Key Pair or opening the SSH port (22). Furthermore, it provides a more convenient way to access EC2 instances located inside Private Subnets.
![overview](../../../images/5-Workshop/5.5-ec2/48.png)

6. Scroll down to the **Advanced details** section, select `EngExam-EC2-SSM-Role` for the IAM instance profile, and click **Launch instance**.
![overview](../../../images/5-Workshop/5.5-ec2/47.png)

7. The EC2 instance is now up and running.
![overview](../../../images/5-Workshop/5.5-ec2/49.png)

8. Click on the newly created instance and select **Connect**.
![overview](../../../images/5-Workshop/5.5-ec2/50.png)

9. Verify that the SSM ping status is online, then click **Connect**.
![overview](../../../images/5-Workshop/5.5-ec2/51.png)

10. We have successfully connected to the EC2 instance and can test the external network connection with a ping command.
![overview](../../../images/5-Workshop/5.5-ec2/52.png)

Through the steps above, a temporary EC2 instance has been successfully created.