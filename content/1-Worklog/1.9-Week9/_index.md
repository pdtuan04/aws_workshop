---
title: "Week 9 Worklog"
date: 2026-06-18
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Learn about and configure the Amazon ElastiCache (Valkey) caching system.
* Troubleshoot issues in the CI/CD pipeline with AWS CodeDeploy.
* Deploy the In-Place Deployment mechanism and automatically fetch the latest version to run in the Auto Scaling Group.
* Research theory and optimize network infrastructure costs with a Region NAT Gateway.

### Tasks to be implemented this week:

| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri | - Learn the theory of Amazon ElastiCache.<br> - Research how to configure ElastiCache with the Valkey engine. | 12/06/2026 | 12/06/2026 | <https://aws.amazon.com/elasticache/valkey/> <https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/WhatIs.html>|
| Sat | - **Practice:** ElastiCache Configuration.<br>&emsp;+ Initialize and configure Amazon ElastiCache with Valkey on AWS. | 13/06/2026 | 13/06/2026 | <https://docs.aws.amazon.com/AmazonElastiCache/latest/dg/SubnetGroups.designing-cluster-pre.valkey.html> |
| Sun |Day Off | 14/06/2026 | 14/06/2026 | |
| Mon | - **Practice:** CI/CD Troubleshooting.<br>&emsp;+ Inspect logs and fix errors occurring during the AWS CodeDeploy configuration for the CI/CD system. <br> - Learn the theory of the In-Place Deployment mechanism in AWS CodeDeploy.<br> - Research how the Auto Scaling Group works together with CodeDeploy. | 15/06/2026 | 15/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/integrations-aws-auto-scaling.html> <br> <https://docs.aws.amazon.com/codedeploy/latest/userguide/tutorials-auto-scaling-group.html>|
| Tue | - **Practice:** In-Place Deployment Implementation.<br>&emsp;+ Create an Application and Deployment Group in CodeDeploy for the In-place flow.<br>&emsp;+ Proceed to fetch the latest update using the In-Place mechanism in the Auto Scaling Group. | 16/06/2026 | 16/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/deployment-groups.html> |
| Wed | - Research NAT Gateway theory and architectural design strategies for cost optimization on AWS. | 17/06/2026 | 17/06/2026 | <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html> |
| Thu | - **Practice:** Network Cost Optimization.<br>&emsp;+ Migrate traditional NAT Gateways scattered across public subnets to use a single Region NAT Gateway. | 18/06/2026 | 18/06/2026 | |

### Week 9 Achievements:

* Successfully learned about and configured Amazon ElastiCache with the Valkey engine.
* Fixed AWS CodeDeploy configuration errors, ensuring a stable CI/CD pipeline.
* Grasped the In-Place Deployment mechanism, successfully created the Application and Deployment Group in CodeDeploy.
* Successfully zipped the file and uploaded it to S3 so that all EC2 Instances in the Auto Scaling Group can get the new code.
* Mastered the theoretical knowledge of NAT Gateways and successfully migrated to a Region NAT Gateway instead of having to create 2 NAT Gateways to optimize operational costs.