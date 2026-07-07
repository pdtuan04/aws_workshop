---
title : "Deploy CloudFront"
date : 2026-07-01
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---

#### Deploy Amazon CloudFront

In this section, I will deploy Amazon CloudFront to deliver content to users with low latency and improved access performance. At the same time, the CloudFront Free Tier includes basic AWS WAF to help block attacks before traffic reaches the system.

Unlike the initial architecture where users access the Application Load Balancer (ALB) directly, CloudFront will be configured to use ALB as the Origin. All user requests will be routed to CloudFront, then CloudFront will forward dynamic requests to ALB to distribute traffic to EC2 instances in the Auto Scaling Group.

#### Contents

- [Create CloudFront Distribution](5.8.1-create-cloudfront/)
- [Configure Origin and Behavior](5.8.2-origin/)
- [Check access via CloudFront](5.8.3-test-cloudfront/)