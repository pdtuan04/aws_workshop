---
title : "Deploy CI/CD with CodeDeploy"
date : 2026-07-01
weight : 7
chapter : false
pre : " <b> 5.7. </b> "
---

#### Deploy CI/CD with CodeDeploy

In this section, I will build a CI/CD process to automatically deploy the application to EC2 instances in the Auto Scaling Group using AWS CodeDeploy.

First, I will create an Amazon S3 Bucket to store deployment artifacts for the deployment process.

I will use AWS Systems Manager Parameter Store to store the application's environment variables. Instead of having to SSH into each EC2 to edit the `.env` file, the environment variables will be fetched automatically from Parameter Store during deployment, making configuration management more centralized, secure, and easier.

Next, I will create a CodeDeploy Application and Deployment Group, and configure the In-place Deployment mechanism to update the new version directly on existing EC2 instances in the Auto Scaling Group.

Finally, I will perform a test deployment to verify the entire CI/CD process, from fetching environment variables, downloading deployment artifacts, pulling the latest Docker image from Docker Hub, to restarting the application on EC2 instances.

#### Contents
- [Create S3 Bucket to store Deployment Artifact](5.7.1-create-s3/)
- [Create Parameter Store](5.7.2-parameter-store/)
- [Create Application & Deployment Group](5.7.3-codedeploy-application/)
- [Configure GitHub Actions](5.7.4-github-actions/)
- [Check Results](5.7.5-test-cicd/)