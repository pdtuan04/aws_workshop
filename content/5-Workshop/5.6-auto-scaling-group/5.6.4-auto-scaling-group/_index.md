---
title : "Create Auto Scaling Group"
date : 2026-07-01 
weight : 4
chapter : false
pre : " <b> 5.6.4 </b> "
---
1. Go to Auto Scaling Groups -> click create, then enter the name and choose the launch template created earlier.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/95.png)
2. Continue by choosing the VPC and 2 Private Subnets 1 and 2.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/96.png)
3. Choose Attach to an existing load balancer. Then choose the TG created in the previous step.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/98.png)
4. For Health checks, tick Turn on Elastic Load Balancing health checks.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/99.png)
5. Continue to Monitoring, tick Enable and click next.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/101.png)
6. In this section, I will create an SNS email to receive notifications when events occur and send them to my email.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/102.png)
7. Review one last time and create.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/103.png)
8. An Auto Scaling Group has been created.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/104.png)
9. Check email, there is an email sent.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/106.png)
10. Check in EC2, there is also a new instance created.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/107.png)
11. Health check shows 1/1 healthy.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/108.png)
12. I go to Activity and see Successful.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/109.png)
13. Check in target group also shows healthy.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/110.png)
14. Now I manually increase to 2 and the result also shows a new one continues to be created.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/111.png)
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/112.png)
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/113.png)
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/114.png)
15. Now I go back to get the DNS of the ALB and try to access it.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/105.png)
16. Accessed successfully.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/94.png)