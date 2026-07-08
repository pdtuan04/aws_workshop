---
title: "Deploy VPC and Networking"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Deploy VPC and Networking

## Overview

In this section, we will construct the network infrastructure serving as the foundation for the entire Web Application system on AWS. The network architecture is designed using a Multi-tier model, isolating resources into Public and Private Subnets to enhance security and scalability.

Components such as the Application Load Balancer will be deployed within the Public Subnets to accept incoming Internet traffic and provide outbound connectivity for internal resources. Meanwhile, Amazon EC2, Amazon RDS, and Amazon ElastiCache will be placed inside the Private Subnets to prevent direct access from the Internet.
A Regional NAT Gateway is utilized for outbound Internet access instead of creating multiple NAT Gateways across different Availability Zones (AZs).
Upon completing this section, you will have a network infrastructure fully prepared for deploying the system's services in the subsequent steps.

## Table of Contents

1. [Create VPC and Configure Networking](5.2.1-create-vpc-nat-subnet/)
2. [Create Security Groups](5.2.2-create-security-group/)