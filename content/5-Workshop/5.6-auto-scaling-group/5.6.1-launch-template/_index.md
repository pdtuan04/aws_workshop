---
title : "Create Launch Template"
date : 2026-07-01 
weight : 1
chapter : false
pre : " <b> 5.6.1 </b> "
---

1. Go to the Launch Templates console and click **Create launch template**.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/64.png)

2. Provide a name for the launch template.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/65.png)

3. Navigate to **My AMIs** -> **Owned by me** and select the AMI generated in the previous step.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/66.png)

4. For the instance type, select **t3.small** and choose a key pair. Leave the subnet selection blank. 
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/67.png)

5. Select the EC2 Security Group created in the previous step.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/68.png)

6. Open a new browser tab to create a new IAM Policy that grants access permissions to fetch files from S3.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/73.png)

7. Proceed to create a new IAM Role.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/74.png)

8. Attach the required permissions to support the upcoming CI/CD pipeline. Here, attach `AmazonSSMManagedInstanceCore`, `AWSCodeDeployRole`, and the custom policy just created.   
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/75.png)

9. Return to the Launch Template setup wizard, expand the **Advanced details** section, and select the newly created role under **IAM instance profile**.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/69.png)

10. Scroll down to the User Data field, insert the following script to ensure each newly provisioned instance pulls the latest deployment version, and click **Create launch template**.
```bash
#!/bin/bash
cd /home/ssm-user/engexam
docker compose pull
docker compose up -d --force-recreate
```
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/72.png)
Through the steps above, the launch template has been successfully created.