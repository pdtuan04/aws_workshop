---
title : "Tạo Application Load Balancer"
date : 2026-07-01 
weight : 3
chapter : false
pre : " <b> 5.6.3 </b> "
---
1. Vào Load Balancer và ấn Create.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/86.png)
2. Chọn Application Load Balancer.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/87.png)
3. Điền tên
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/88.png)
4. Chọn VPC
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/89.png)
5. Chọn 2 Public Subnet 1 và 2 cho ALB.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/90.png)
6. Chọn SG dành cho ALB mà mình đã tạo từ bước trước.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/91.png)
7. Routing action
- Chọn Forward to target group.
- Chọn Target Group mà mình mới tạo
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/92.png)
8. Sau khi tạo xong ALB mình sẽ có 1 chuỗi DNS để sau bước tạo ASG mình sẽ dùng nó để xem truy cập vô được không.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/93.png)