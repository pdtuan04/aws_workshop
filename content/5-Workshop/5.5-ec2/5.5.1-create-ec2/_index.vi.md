---
title : "Tạo EC2 Instance"
date : 2026-07-01
weight : 1
chapter : false
pre : " <b> 5.5.1 </b> "
---
Phần này mình tạo tạm EC2 để tạo AMI mình sẽ xóa instance này sau.
1. Vào EC2 và ấn Create Instance và đặt tên cho nó. 
![overview](../../../images/5-Workshop/5.5-ec2/43.png)
2. Ở instance type mình chọn t3.small cho dư dã tài nguyên 1 chút và chọn luôn phần key pair cho nó.
![overview](../../../images/5-Workshop/5.5-ec2/44.png)
3. Chọn VPC và Subnet (ở đây mình mược tạm Public Subnet 1), sau đó bật enable Auto-assign public IP.
![overview](../../../images/5-Workshop/5.5-ec2/45.png)
4. Chọn SG dành cho EC2 mà mình đã tạo sẵn ở bước 5.2.2
![overview](../../../images/5-Workshop/5.5-ec2/46.png)
5. Mình sẽ tạo một IAM Role có tên EngExam-EC2-SSM-Role và gắn policy AmazonSSMManagedInstanceCore.
- Việc này giúp mình kết nối đến EC2 thông qua AWS Systems Manager Session Manager mà không cần Key Pair hay mở cổng SSH (22). Đồng thời, mình vẫn có thể truy cập các EC2 nằm trong Private Subnet một cách thuận tiện hơn.
![overview](../../../images/5-Workshop/5.5-ec2/48.png)
6. Tiếp tục mình kéo xuống phía Advanced details mình chọn EngExam-EC2-SSM-Role và ấn Launch instance.
![overview](../../../images/5-Workshop/5.5-ec2/47.png)
7. Lúc này EC2 mình đã khởi chạy.
![overview](../../../images/5-Workshop/5.5-ec2/49.png)
8. Tiếp tục mình ấn vào instance vừa tạo và chọn Connect.
![overview](../../../images/5-Workshop/5.5-ec2/50.png)
9. Ở đây mình thấy trạng thái ping là online rồi mình ấn Connect.
![overview](../../../images/5-Workshop/5.5-ec2/51.png)
10. Mình đã kết nối thành công đến EC2 và ping ra ngoài thử.
![overview](../../../images/5-Workshop/5.5-ec2/52.png)
Qua các bước trên 1 EC2 tạm đã được tạo.