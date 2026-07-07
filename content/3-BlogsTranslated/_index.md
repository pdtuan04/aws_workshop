---
title: "Blogs Posted"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---
### [Blog 1 - Benefits of Combining Amazon CloudFront with Application Load Balancer](3.1-Blog1/)

This blog analyzes the outstanding benefits of placing a content delivery network (CloudFront) as a protective layer in front of a load balancer (ALB), instead of letting users access the application server directly. This architecture significantly accelerates response times for remote users, easily integrates security layers (WAF, Shield), and saves bandwidth costs (Data Transfer Out) from the origin system.

### [Blog 2 - Adding HTTP Security Headers Using Amazon CloudFront](3.2-Blog2/)

This blog proposes a way to protect web applications from common attacks (such as XSS) by attaching HTTP security headers right at the network edge through CloudFront. The article presents 3 deployment methods (Response Headers Policies, CloudFront Functions, Lambda@Edge) that help automate this defense layer without needing to modify the source code on the origin server.

### [Blog 3 - Optimizing Network Architecture with Amazon VPC Regional NAT Gateway](3.3-Blog3/)

This blog introduces the solution of using a single shared NAT Gateway for the entire VPC network system (Regional NAT Gateway) instead of creating multiple scattered NAT Gateways for each Availability Zone. This architecture simplifies the network grid, improves security by keeping resources out of public subnets, automatically manages IPs to prevent port exhaustion, and optimizes operational costs.