---
title : "Tạo Elastic Cache (Valkey)"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---
1. Vào Elastic cache và ấn create cache.
![overview](../../../images/5-Workshop/5.4-elastic-cache/32.png)
2. Cấu hình Elastic Cache 
- Engine mình chọn Valkey.
- Deployment option chọn Node-based cluster.
- Creation method chọn Cluster cache.
- Cluster mode mình chọn Disable.     
![overview](../../../images/5-Workshop/5.4-elastic-cache/33.png)
3. Điền tên 
![overview](../../../images/5-Workshop/5.4-elastic-cache/34.png)
4. Ở phần node type mình chọn cache.t4g.micro cho nhẹ credit.
![overview](../../../images/5-Workshop/5.4-elastic-cache/35.png)
5. Số lượng replicas mình đặt chỉ 1 thôi.
![overview](../../../images/5-Workshop/5.4-elastic-cache/36.png)
6. Chọn subnet group vừa tạo ở bước trước.
![overview](../../../images/5-Workshop/5.4-elastic-cache/37.png)
7. Availability Zone placements mình chọn Specify Availability Zones và ấn next.
![overview](../../../images/5-Workshop/5.4-elastic-cache/38.png)
8. Phần Advanced mình giữ nguyên và ấn next review lại toàn bộ và ấn create.
![overview](../../../images/5-Workshop/5.4-elastic-cache/39.png)
1. Mình thiếu bước thêm Security Group cho Elastic Cache nên mình sẽ modify lại elastic cache vừa tạo.
- Kéo xuống dưới phần security group chọn SG mà mình đã tạo sẵn cho Elastic Cache ở bước 5.2.2 và ấn xem lại thay đổi và ấn hoàn thành. 
![overview](../../../images/5-Workshop/5.4-elastic-cache/40.png)
Qua các bước trên Elastic Cache đã được tạo thành công, mình đã có được chuỗi kết nối.
![overview](../../../images/5-Workshop/5.4-elastic-cache/41.png)