---
title: "Deploy Amazon ElastiCache"
date: 2026-07-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

#### Deploy Amazon ElastiCache

In this section, we will create an Amazon ElastiCache for Valkey cluster to store cached data for the application. ElastiCache will be deployed using a Primary Node and Replica Node model to enhance data read capabilities, offload query stress from the Amazon RDS database, and support automatic Failover if the Primary Node encounters an issue.

To ensure strict security, ElastiCache will be deployed within the Private Subnets via a dedicated Subnet Group, and network access will be restricted exclusively to EC2 instances through the configured Security Group.

#### Table of Contents

- [Create ElastiCache Subnet Group](5.4.1-subnet-group/)
- [Create Amazon ElastiCache for Valkey](5.4.2-create-elasticache/)