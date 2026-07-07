---
title : "Tạo RDS (SQL Server)"
date : 2026-07-01 
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

1. Tiếp tục ấn create database để tạo db.
![overview](../../../images/5-Workshop/5.3-rds/18.png)
2. Ở đây hệ thống mình dùng SQL Server thì mình sẽ chọn nó và chọn Full Configuration.
![overview](../../../images/5-Workshop/5.3-rds/19.png)
3. Chọn Edition
![overview](../../../images/5-Workshop/5.3-rds/20.png)
4. Ở phần Credentials management mình chọn Self managed để tự cấu hình mật khẩu theo ý mình.
![overview](../../../images/5-Workshop/5.3-rds/21.png)
5. Instance type chọn db.t3.micro.
![overview](../../../images/5-Workshop/5.3-rds/22.png)
6. Allocated storage mình chỉnh về 20.
![overview](../../../images/5-Workshop/5.3-rds/23.png)
7. Mình chọn vpc cho db và subnet group mình vừa tạo ở phần trước cho nó.
![overview](../../../images/5-Workshop/5.3-rds/24.png)
8. Ở đây chọn Securuty group cho VPC.
![overview](../../../images/5-Workshop/5.3-rds/25.png)
9. Tiếp tục chọn Standard.
![overview](../../../images/5-Workshop/5.3-rds/26.png)
10. Chọn Create database để hoàn thành.
![overview](../../../images/5-Workshop/5.3-rds/27.png)
Qua các bước trên ta đã tạo thành công database cho hệ thống và đã có chuỗi kết nối.
![overview](../../../images/5-Workshop/5.3-rds/42.png)