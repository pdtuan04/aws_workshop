---
title: "Week 1 Worklog"
date: 2026-04-23
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---


### Week 1 Objectives:

* Connect and get acquainted with new members in the First Cloud Journey.
* Understand fundamental AWS services and how to use them.

### Tasks to be implemented this week:
| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri |- Create an AWS Free Tier account. <br> - Learn about AWS Console. <br>- Prepare necessary resources to perform labs for the task to receive $200 credit. <br> - Learn how to draw AWS architecture diagrams with draw.io. | 17/04/2026 | 17/04/2026 | <https://000001.awsstudygroup.com/> <br> <https://youtu.be/l8isyDe-GwY> |
| Sat | - Practice: Set up basic Billing Alerts to control the number of credits in the account.<br>&emsp; + Send daily and monthly bill emails. <br>&emsp; + Send alert emails when exceeding the predefined limit. | 18/04/2026 | 18/04/2026 | <https://000007.awsstudygroup.com/> <br> <https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html> |
| Sun | Day Off | 19/04/2026 | 19/04/2026 |  |
| Mon | - Practice: Manage access with AWS Identity and Access Management (IAM)<br>&emsp; + Create IAM Group and IAM User.<br>&emsp; + Create IAM Role and IAM User.<br>- Research theory on basic AWS network infrastructure <br>&emsp; + Region <br>&emsp; + VPC <br>&emsp; + Subnet <br>&emsp; + Internet Gateway <br>&emsp; + Route Table <br>&emsp; + Security Group | 20/04/2026 | 20/04/2026 | <https://000003.awsstudygroup.com/> <br><https://000002.awsstudygroup.com/>|
| Tue | - **Practice:** Configure network components <br>&emsp; + VPC <br>&emsp; + Subnet <br>&emsp; + Internet Gateway <br>&emsp; + Route Table <br>&emsp; + Security Group<br> - Learn about NAT Gateway | 21/04/2026 | 21/04/2026 | <https://000003.awsstudygroup.com/> |
| Wed | - Learn basic EC2: <br>&emsp; + Instance types <br>&emsp; + AMI <br>&emsp; + Launch Instance | 22/04/2026 | 22/04/2026 | <https://000003.awsstudygroup.com/> |
| Thu | - **Practice:** <br>&emsp; + Create EC2 instances inside public and private subnets. <br>&emsp;+ SSH into the EC2 inside the public subnet to check the connection. <br>&emsp; + Configure NAT Gateway for the Private EC2 instance in the private subnet to access the internet. <br>&emsp; + Indirectly SSH from the EC2 in the public subnet to the EC2 in the private subnet using a .pem file to check the outbound internet connection. | 23/04/2026 | 23/04/2026 | <https://000003.awsstudygroup.com/> |


### Week 1 Achievements:

* Set up the practice environment: Successfully created an AWS account (with $200 credit), got familiar with the AWS Console, draw.io, and formed a working team.

* Optimized cost risk management by configuring a detailed Billing Alerts system (sending daily/monthly reports and over-limit alerts).

* Ensured the Principle of Least Privilege in authorization by setting up and managing AWS IAM resources (Group, User, Role).

* Successfully built the core AWS VPC network infrastructure, including planning Public/Private Subnets, and configuring Route Tables, Internet Gateways, and Security Groups.

* Deployed a secure server model: Created EC2 instances on both Subnets, set up a NAT Gateway to grant Internet access for the Private subnet, and successfully tested the indirect SSH flow from Public to Private using a .pem file.