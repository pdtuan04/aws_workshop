---
title : "Deploy Auto Scaling Group"
date : 2026-07-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

#### Deploy Auto Scaling Group

In this section, I will deploy Amazon EC2 Auto Scaling to automatically manage the number of EC2 Instances based on the system usage demand. First, I will create a Launch Template from the AMI prepared in the previous steps to use as an EC2 initialization template. Then, I will configure a Target Group and link it with an Application Load Balancer (ALB) to distribute traffic to EC2 instances in the Auto Scaling Group.

#### Contents

- [Create Launch Template](5.6.1-launch-template/)
- [Create Target Group](5.6.2-target-group/)
- [Create Application Load Balancer](5.6.3-load-balancer/)
- [Create Auto Scaling Group](5.6.4-auto-scaling-group/)