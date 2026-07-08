---
title: "Introduction"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

#### Introduction

This workshop guides you through deploying a Web Application system on AWS, ensuring scalability, high availability, and security.

The system utilizes Amazon CloudFront combined with AWS WAF to accelerate access and protect the application, an Application Load Balancer to distribute traffic, Amazon EC2 instances within an Auto Scaling Group to automatically scale based on load, Amazon RDS Multi-AZ to ensure data safety, and Amazon ElastiCache to improve data retrieval performance.

In addition, the workshop establishes a CI/CD pipeline using GitHub Actions, DockerHub, Amazon S3, and AWS CodeDeploy to automate the application building and deployment processes.

#### Workshop Overview

The architecture of this workshop consists of the following main components:

- Amazon CloudFront distributes content to users with low latency.
- AWS WAF protects the application against common web attacks.
- Application Load Balancer (ALB) balances traffic load across EC2 instances.
- Amazon EC2 inside an Auto Scaling Group processes requests and automatically scales out when load increases.
- Amazon RDS SQL Server Multi-AZ stores data using a Primary - Standby model.
- Amazon ElastiCache accelerates data retrieval using a caching mechanism.
- Amazon S3 stores application media files and deployment artifacts.
- GitHub, GitHub Actions, DockerHub, and AWS CodeDeploy construct an automated CI/CD pipeline.
- Amazon CloudWatch, CloudWatch Alarm, and Amazon SNS monitor the system, send alerts, and support triggering Auto Scaling actions.

![overview](../../images/5-Workshop/5.1-Workshop-overview/architechture.drawio.png)