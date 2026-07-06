---
title : "Tạo VPC, Subnet Group, Regional Nat Gateway"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.2.1 </b> "
---

1. Vào VPC và ấn Create VPC

![overview](../../../images/5-Workshop/5.2-vpc-networking/1.png)

2. Chọn VPC and more và đặt tên cho VPC
![overview](../../../images/5-Workshop/5.2-vpc-networking/2.png)

3. Cấu hình các thành phần trong VPC
- Chọn 2 cho AZs
- Public subnet mình chọn 2 mục đích chứa ALB cần nằm ở 2 Public Subnet.
- Vì toàn bộ các thành phần chính mình đều đặt ở Private Subnet hết nên mình chọn 4 (vẫn còn thiếu 2 Private Subnet mình sẽ tự tay tạo sau) 
![overview](../../../images/5-Workshop/5.2-vpc-networking/3.png)

4. Chọn Regional Nat Gateway.
![overview](../../../images/5-Workshop/5.2-vpc-networking/4.png)

Sau đó ấn tạo mình sẽ có được 1 VPC

5. Tiếp tục mình sẽ tạo thêm 2 Private Subnet còn lại để chứa Elastic Cache
- Chọn VPC cho subnet và đặt tên cho Subnet
![overview](../../../images/5-Workshop/5.2-vpc-networking/7.png)
- Chọn AZ và cấu hình dãi IP cho subnet và ấn tạo.
![overview](../../../images/5-Workshop/5.2-vpc-networking/8.png)
- Priavte Subnet 6 tạo tương tự như trên.
6. Sau khi tạo hoàn thành, vào VPC mới tạo ta sẽ có map nhìn tổng quát.
![overview](../../../images/5-Workshop/5.2-vpc-networking/9.png)