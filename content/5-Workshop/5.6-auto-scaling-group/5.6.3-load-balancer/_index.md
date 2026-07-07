---
title : "Create Application Load Balancer"
date : 2026-07-01 
weight : 3
chapter : false
pre : " <b> 5.6.3 </b> "
---
1. Go to Load Balancer and click Create.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/86.png)
2. Choose Application Load Balancer.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/87.png)
3. Enter the name.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/88.png)
4. Choose VPC.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/89.png)
5. Choose 2 Public Subnets 1 and 2 for ALB.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/90.png)
6. Choose the SG for ALB that I created in the previous step.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/91.png)
7. Routing action
- Choose Forward to target group.
- Choose the Target Group that I just created.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/92.png)
8. After creating the ALB, I will have a DNS string, and after the ASG creation step I will use it to check whether it can be accessed.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/93.png)