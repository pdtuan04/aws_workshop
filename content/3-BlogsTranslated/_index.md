---
title: "Published Blogs"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

### [Blog 1 - Optimizing Network Architecture with Amazon VPC Regional NAT Gateway](3.1-Blog1/)

This blog introduces the solution of using a single, shared NAT Gateway for the entire VPC network (Regional NAT Gateway) instead of having to create multiple scattered NAT Gateways for each Availability Zone. This architecture helps simplify the network, provides better security by eliminating the need to expose resources to public subnets, and automatically manages IPs to prevent port exhaustion and optimize operational costs.

### [Blog 2 - Adding HTTP Security Headers with Amazon CloudFront](3.2-Blog2/)

This blog proposes a way to protect web applications from common attacks (such as XSS) by attaching security codes (HTTP security headers) right at the network edge via CloudFront. The article presents 3 deployment methods (Response Headers Policies, CloudFront Functions, Lambda@Edge) that help automate this defense layer without requiring modifications to the source code on the origin server.

### [Blog 3 - Benefits of Combining Amazon CloudFront with Application Load Balancer](3.3-Blog3/)

This blog analyzes the outstanding benefits of placing a content delivery network (CloudFront) as a shield in front of an Application Load Balancer (ALB), instead of letting users access the application servers directly. This architecture significantly increases response speeds for distant users, easily integrates security layers (WAF, Shield), and saves bandwidth costs (Data Transfer Out) from the origin system.