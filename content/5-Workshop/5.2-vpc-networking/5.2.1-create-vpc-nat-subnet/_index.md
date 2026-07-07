---
title: "Create VPC, Subnet Group, Regional NAT Gateway"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 5.2.1 </b> "
---

1. Go to the VPC console and click **Create VPC**.

![overview](../../../images/5-Workshop/5.2-vpc-networking/1.png)

2. Select **VPC and more** and enter a name for the VPC.
![overview](../../../images/5-Workshop/5.2-vpc-networking/2.png)

3. Configure the VPC components:
- Select **2** for Availability Zones (AZs).
- Select **2** for Public subnets, as the ALB needs to be located across 2 Public Subnets.
- Since all our main components will be placed in Private Subnets, select **4** for Private subnets.
![overview](../../../images/5-Workshop/5.2-vpc-networking/3.png)

4. Select **Regional NAT Gateway**.
![overview](../../../images/5-Workshop/5.2-vpc-networking/4.png)

Then click create to generate the VPC.

5. Next, create 2 additional Private Subnets to host ElastiCache:
- Select the newly created VPC for the subnet and enter a name for the Subnet.
![overview](../../../images/5-Workshop/5.2-vpc-networking/7.png)
- Select the AZ, configure the IP CIDR block for the subnet, and click create.
![overview](../../../images/5-Workshop/5.2-vpc-networking/8.png)
- Create **Private Subnet 6** similarly following the steps above.

6. Once completion, navigate to the newly created VPC to view the Resource Map overview.
![overview](../../../images/5-Workshop/5.2-vpc-networking/9.png)