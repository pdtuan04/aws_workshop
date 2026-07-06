---
title : "Tạo Auto Scaling Group"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 5.6.4 </b> "
---
1. Vào Auto Scaling Groups -> ấn create sau đó đặt tên và chọn launch template đã tạo.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/95.png)
2. Tiếp tục chọn VPC và 2 Private Subnet 1 và 2.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/96.png)
3. Chọn Attach to an existing load balancer. Sau đó chọn TG mình đã tạo ở bước trước.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/98.png)
4. Health checks mình tick vào Turn on Elastic Load Balancing health checks 
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/99.png)
5. Tiếp tục Monitoring  tick vào ô Enable và ấn next.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/101.png)
6. Ở phần này mình sẽ tạo SNS mail nhận thông báo khi có sự kiện xảy ra sẽ gửi về mail của mình.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/102.png)
7. Review lại lần cuối và create.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/103.png)
8. 1 Auto Scaling Group đã được tạo.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/104.png)
9. Vào check mail có 1 mail đẫ được gửi về.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/106.png)
10. Check ở phần EC2 cũng thấy có 1 instance mới được tạo.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/107.png)
11. Health check thấy 1/1 healthy.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/108.png)
12. Mình vào Activity thấy Successful.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/109.png)
13. Kiểm tra trong target group cũng thấy healthy
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/110.png)
14. Bây giờ mình tăng thủ công lên 2 và kết quả cũng thấy được 1 cái mới tiếp tục được tạo ra.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/111.png)
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/112.png)
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/113.png)
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/114.png)
15. Giờ mình quay lại lấy DNS của alb và truy cập vào thử.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/105.png)
16. Đã truy cập thành công.
![overview](../../../images/5-Workshop/5.6-auto-scaling-group/94.png)