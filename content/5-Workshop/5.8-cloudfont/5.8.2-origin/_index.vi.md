---
title : "Cấu hình Origin và Behavior"
date : 2026-07-01 
weight : 2
chapter : false
pre : " <b> 5.8.2 </b> "
---
1. Vào Origin của Cloudfont mới tạo và cấu hình như trong hình.
-  Ấn Create.
-  Origin Domain mình chọn cái ALB mình đã tạo và Port đặt là 80 và ấn Create Origin.
![overview](../../../images/5-Workshop/5.8-cloudfont/161.png)
2. Tiếp tục vào phần Behavior và cài đặt như hình.
- Path mình để `/images/*`
- Chọn S3 lưu trữ tài nguyên tĩnh.
- Viewer protocol policy mình chọn HTTP to HTTPS để tự động chuyển các yêu cầu HTTP sang HTTPS, đảm bảo kết nối an toàn.
- Allowed HTTP methods `GET, HEAD`.
![overview](../../../images/5-Workshop/5.8-cloudfont/163.png)
3. Mình cứ giữ nguyên phần dưới rồi tạo.
![overview](../../../images/5-Workshop/5.8-cloudfont/162.png)
4. Mình tiếp tục thêm phần Behavier tiếp theo.
- Origin and origin groups mình chọn cái ALB.
- Viewer protocol policy mình cũng chọn HTTP to HTTPS để tự động chuyển các yêu cầu HTTP sang HTTPS.
- Allowed HTTP methods `GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE`.
![overview](../../../images/5-Workshop/5.8-cloudfont/164.png)
5. Cache policy mình để CachingDisable và tạo là xong.
![overview](../../../images/5-Workshop/5.8-cloudfont/166.png)