---
title : "Configure GitHub Actions"
date : 2026-07-01
weight : 4
chapter : false
pre : " <b> 5.7.4 </b> "
---
1. Go to GitHub Settings -> Secrets and variables -> Actions.
![overview](../../../images/5-Workshop/5.7-codedeploy/142.png)
2. Click New repository secret.
![overview](../../../images/5-Workshop/5.7-codedeploy/143.png)

3. I need to get `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`. When creating an Access Key, a `.csv` file will be downloaded to the machine, open it and fill in the corresponding values.
![overview](../../../images/5-Workshop/5.7-codedeploy/144.png)
4. Continue like that and fill in all required variables:
- `AWS_ACCESS_KEY_ID` – Access Key of the IAM User.
- `AWS_SECRET_ACCESS_KEY` – Secret Access Key of the IAM User.
- `AWS_REGION` – AWS deployment region.
- `AWS_S3_BUCKET_NAME` – Name of the S3 Bucket storing deployment artifacts.
- `AWS_APPLICATION_NAME` – Name of the CodeDeploy Application.
- `AWS_DEPLOYMENT_GROUP_NAME` – Name of the CodeDeploy Deployment Group.
- `DOCKER_USERNAME` – Docker Hub username.
- `DOCKERHUB_TOKEN` – Docker Hub access token.
- `DOCKERHUB_PROJECT_NAME` – Repository name on Docker Hub.
- `VITE_API_URL` – API address of the application.
- `VITE_GOOGLE_CLIENT_ID` – Google OAuth Client ID.
- `VITE_TINYMCE_API_KEY` – TinyMCE API Key.
- ![overview](../../../images/5-Workshop/5.7-codedeploy/143.png)