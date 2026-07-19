---
title: "Workshop"
date: 2026-07-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# English Learning Platform On AWS

#### Overview
In modern web systems, ensuring High Availability, Scalability, and Security are critical requirements. AWS provides many services to build an architecture that meets these requirements with optimized cost and high automation capability.

In this workshop, we will build a website deployment system on AWS using a multi-tier architecture model. The system uses CloudFront combined with AWS WAF to accelerate access and protect the application from common attacks. Traffic will be routed to an Application Load Balancer (ALB), then distributed to EC2 servers in an Auto Scaling Group to ensure load tolerance and automatic scaling.

Application data is stored on Amazon RDS with a Primary - Standby (Multi-AZ) model to ensure high availability. At the same time, Amazon ElastiCache for Valkey/Redis is used to speed up data retrieval and reduce database load.

The application deployment process is automated through GitHub Actions, DockerHub, Amazon S3, and AWS CodeDeploy, helping shorten new release time and minimize manual operations.

#### Contents

1. [System architecture overview](5.1-Workshop-overview/)
2. [Deploy VPC and Networking](5.2-vpc-networking/)
3. [Deploy Amazon RDS](5.3-rds/)
4. [Deploy Amazon ElastiCache](5.4-elastic-cache/)
5. [Deploy EC2 to create AMI](5.5-ec2/)
6. [Deploy Auto Scaling Group](5.6-auto-scaling-group/)
7. [Deploy CI/CD with CodeDeploy](5.7-codedeploy/)
8. [Deploy CloudFront](5.8-cloudfont/)
9. [Video Demo](5.9-demo/)