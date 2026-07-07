---
title: "Configure Security Groups"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 5.2.2 </b> "
---

1. Create a Security Group for EC2:
- Go to the VPC console, select **Security Groups**, and click **Create security group**.
- Enter a name.
- Select your VPC.
- Inbound rules: Open port **8082** only to allow access to the application.
![overview](../../../images/5-Workshop/5.2-vpc-networking/10.png)

2. Create a Security Group for the Database:
- Go to the VPC console, select **Security Groups**, and click **Create security group**.
- Enter a name.
- Select your VPC.
![overview](../../../images/5-Workshop/5.2-vpc-networking/11.png)
- Inbound rules: Open port **1433** only to allow access to the database.
- Source: Instead of choosing `0.0.0.0/0`, select the **EC2 Security Group** to restrict access exclusively to EC2 instances.
![overview](../../../images/5-Workshop/5.2-vpc-networking/12.png)

3. Create a Security Group for ElastiCache:
- Similarly, open port **6379** only and set the source to the **EC2 Security Group**.
![overview](../../../images/5-Workshop/5.2-vpc-networking/13.png)

4. Create a Security Group for the Application Load Balancer:
- For this group, open port **80** and set the source to `0.0.0.0/0`.
![overview](../../../images/5-Workshop/5.2-vpc-networking/14.png)