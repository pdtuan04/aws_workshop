---
title: "Week 2 Worklog"
date: 2026-04-30
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Week 2 Objectives:
* Get familiar with and be able to use the AWS CLI.
* Successfully deploy a sample web application (Node.js) connected to a relational database (RDS) on AWS.
* Build a highly available (High Availability) and auto-scalable (Auto Scaling) system architecture.
* Ensure data safety and optimize operational workflows with AWS CLI and AWS Backup.

### Tasks to be implemented this week:
| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri | - Install the AWS Command Line Interface. <br> - Learn and use the AWS CLI to interact with, retrieve information from, and manage AWS services instead of relying solely on the Console. | 24/04/2026 | 24/04/2026 | <https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html> <https://000011.awsstudygroup.com/>|
| Sat | - **Practice:** Set up a basic sample application on the EC2 service.<br>&emsp; + Configure the network for the system. <br>&emsp; + Set up an EC2 instance using the Amazon Linux operating system. <br>&emsp; + Configure a Security Group for the EC2 instance. <br>&emsp; + Deploy a basic Node.js application to the EC2 server. <br>&emsp; + Verify if the application is running successfully. | 25/04/2026 | 25/04/2026 | <https://000004.awsstudygroup.com/> |
| Sun | Day Off | 26/04/2026 | 26/04/2026 |  |
| Mon |- **Practice:** Set up a database with RDS for the sample application.<br>&emsp; + Reconfigure the sample application from the previous day. <br>&emsp; + Configure a Subnet Group for the database. <br>&emsp; + Set up an RDS Database instance for the application. <br>&emsp; + Configure a Security Group to allow the EC2 instance to securely connect to RDS.<br> - Research theory on scalability for high traffic. <br>&emsp; + Target Group <br>&emsp; + Elastic Load Balancing <br>&emsp; + Auto Scaling Group | 27/04/2026 | 27/04/2026 | <https://000006.awsstudygroup.com/> <br> <https://000005.awsstudygroup.com/>|
| Tue | - **Practice:** Set up Launch Templates.<br>&emsp; + Reconfigure the old application created previously. <br>&emsp; + Package the EC2 instance configuration (AMI with the Node.js app, Instance type, Key pair, Security Group) in preparation for Auto Scaling. | 28/04/2026 | 28/04/2026 | <https://000006.awsstudygroup.com/> |
| Wed | - **Practice:** Load Balancer, Auto Scaling & Notification (SNS). <br>&emsp; + Configure Elastic Load Balancing. <br>&emsp; + Set up Elastic Load Balancing.<br>&emsp; + Configure Target Groups and Routing to automatically distribute incoming user traffic across multiple EC2 targets. <br>&emsp; + Set up an Auto Scaling Group (ASG) to automatically adjust the number of EC2 instances (including manual scaling) based on actual demand. <br>&emsp; + Integrate Amazon SNS to send email notifications whenever the ASG performs scale-out or scale-in actions. | 29/04/2026 | 29/04/2026 | <https://000006.awsstudygroup.com/> |
| Thu | - Learn the theory of AWS Backup. <br> - **Practice:** AWS Backup. <br>&emsp; + Set up a Backup Plan to create a scheduled backup strategy (automated Snapshots) for active resources (EC2, RDS). | 30/04/2026 | 30/04/2026 | <https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html>  <br> <https://000013.awsstudygroup.com/>|


### Week 2 Achievements:
* Learned and got familiar with cloud service management operations via the AWS CLI.
* Successfully deployed a Node.js application on EC2 and configured a secure connection to the RDS database using Security Groups.
* Packaged system configurations using Launch Templates and successfully deployed an Elastic Load Balancing model to distribute traffic.
* Built an automated scaling system (Auto Scaling Group) to dynamically increase/decrease the number of EC2 instances, integrated with email notifications (Amazon SNS).
* Ensured system data safety by configuring an AWS Backup Plan and setting up an automated snapshot schedule for EC2 and RDS.