---
title : "Deploy EC2 to Create AMI"
date : 2026-07-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

#### Deploy EC2 to Create AMI

In this section, we will create a temporary Amazon EC2 instance to prepare the application environment. Essential components including Docker, Docker Compose, and the AWS CodeDeploy Agent will be installed on the instance. Once the installations are complete, we will perform a test deployment of the application using Docker to ensure that the environment is correctly configured and the application functions properly.

After validating that the EC2 instance is fully prepared, we will generate an Amazon Machine Image (AMI) from it. This AMI will serve as the Launch Template for the Auto Scaling Group in the upcoming steps, ensuring that all newly provisioned EC2 instances come pre-configured with the required environment, thereby optimizing deployment times.

#### Table of Contents

- [Create EC2 Instance](5.5.1-create-ec2/)
- [Install Docker and Docker Compose](5.5.2-install-docker/)
- [Deploy and Verify Application](5.5.3-test-application/)
- [Install AWS CodeDeploy Agent](5.5.4-install-codedeploy-agent/)
- [Create Amazon Machine Image (AMI)](5.5.5-create-ami/)