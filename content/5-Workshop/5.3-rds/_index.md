---
title : "Deploy Amazon RDS"
date : 2026-07-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

#### Deploy Amazon RDS

In this section, we will create an Amazon RDS SQL Server to store data for the application. The database will be deployed using a Multi-AZ configuration, which includes a Primary DB Instance and a Standby DB Instance across two different Availability Zones to ensure high availability and disaster recovery resilience.

To enhance security, the RDS instance will be placed within Private Subnets using a DB Subnet Group, and access will be strictly restricted to traffic originating from the EC2 Security Group.

#### Table of Contents

- [Create DB Subnet Group](5.3.1-subnet-group/)
- [Create Amazon RDS SQL Server Multi-AZ](5.3.2-create-rds/)