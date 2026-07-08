---
title: "Week 5 Worklog"
date: 2026-05-21
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Learn about and integrate the AWS S3 storage service along with the CloudFront content delivery network.
* Build an email sending function and a learning flashcard feature.
* Apply basic CI/CD to automate the build process and store Docker images on AWS ECR.
* Deploy the database on AWS RDS and learn about Auto Scaling.

### Tasks to be implemented this week:

| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri | - Learn basic theory about the AWS S3 Object Storage service.<br> - Research how the CloudFront Content Delivery Network (CDN) works and how to integrate it with S3. | 15/05/2026 | 15/05/2026 | <https://aws.amazon.com/blogs/networking-and-content-delivery/amazon-s3-amazon-cloudfront-a-match-made-in-the-cloud/> |
| Sat | - **Practice:** Integrate S3 and CloudFront.<br>&emsp;+ Build an API to upload static files (images, documents) to AWS S3.<br>&emsp;+ Configure CloudFront integration so users access files through it instead of directly accessing S3. | 16/05/2026 | 16/05/2026 | <https://000094.awsstudygroup.com/> |
| Sun | Day Off | 17/05/2026 | 17/05/2026 | |
| Mon | - **Practice:** Email Function.<br>&emsp;+ Learn about libraries that support sending emails in the backend application.<br>&emsp;+ Build an email sending API (welcome email, notification email). - **Practice:** Flashcard Function.<br>&emsp;+ Design the table structure and data relationships for the flashcard feature.<br>&emsp;+ Build basic APIs (CRUD) to manage flashcards. | 18/05/2026 | 18/05/2026 | |
| Tue | - **Practice:** CI/CD and Container Registry.<br>&emsp;+ Implement a CI/CD pipeline for the project to automate basic source code build and test steps by SSH-ing into EC2. | 19/05/2026 | 19/05/2026 | |
| Wed | - **Practice:** Database Deployment and ECR Usage.<br>&emsp;+ Connect the application to the initialized database on AWS RDS.<br>&emsp;+ Configure a secure connection string and run migrations to update new data tables.<br>&emsp;+ Write a basic Seed data file for the application upon initialization.<br>&emsp;+ Build and push the Docker image to AWS ECR using the AWS CLI. | 20/05/2026 | 20/05/2026 | |
| Thu | - Review the theory on how Auto Scaling works on AWS.<br> - Research basic steps to configure an Auto Scaling group to automatically add/remove servers based on utilization, covering 3 scaling mechanisms (Manual Scale, Dynamic Scaling, Scheduled Scaling). | 21/05/2026 | 21/05/2026 | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html> |

### Week 5 Achievements:

* Completed learning about and integrating the API to upload files to AWS S3, combined with CloudFront to deliver static content.
* Successfully built the email sending API and flashcard management APIs according to the initial design.
* Implemented a basic CI/CD pipeline using SSH to pull new images.
* Tested and pushed a Docker image to the AWS ECR repository.
* Successfully connected the backend to the AWS RDS database and executed the new data structure.
* Took initial steps and gained basic concepts on how AWS Auto Scaling works in preparation for future system scaling challenges.