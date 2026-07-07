---
title: "Blog 3"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---
# Tối Ưu Hóa Kiến Trúc Mạng Với Amazon VPC Regional NAT Gateway

Trước đây, để đảm bảo tính sẵn sàng cao, hệ thống yêu cầu phải tạo các NAT Gateway riêng biệt tại các subnet công cộng (public subnet) cho từng Availability Zone (AZ). Với chế độ Regional NAT Gateway (RNAT), AWS cho phép bạn chỉ cần tạo một NAT Gateway duy nhất hoạt động ở cấp độ toàn bộ Virtual Private Cloud (VPC). Hệ thống này sẽ tự động mở rộng hoặc thu hẹp quy mô trên các AZ dựa trên khối lượng công việc thực tế, giúp đơn giản hóa kiến trúc mạng và giảm bớt gánh nặng quản lý.

## 1. Các Lợi Ích Cốt Lõi

* Bảo vệ an ninh mạng tốt hơn: Tổ chức không cần phải tạo các public subnet để chứa NAT Gateway nữa. Điều này loại bỏ hoàn toàn nguy cơ vô tình triển khai các tài nguyên nhạy cảm vào public subnet và làm lộ chúng ra internet.
* Tự động chống cạn kiệt cổng (Port Exhaustion): Mỗi địa chỉ IP của RNAT hỗ trợ tới 55.000 kết nối đồng thời đến cùng một đích. Với 2 cơ chế tăng giảm:
  * Cơ chế tự động tăng: Khi số kết nối vượt qua ngưỡng khoảng 40.000, RNAT tự động bổ sung IP mới trong vòng 5 phút (tối đa 32 IP cho mỗi AZ).
  * Cơ chế tự động giảm: Khi số kết nối giảm xuống dưới 20.000 và duy trì trong khoảng 1 giờ, hệ thống sẽ tự động thu hồi IP để tiết kiệm.
* Tích hợp trình quản lý IP (VPC IPAM): RNAT tự động lấy IP từ các pool IPAM tuân thủ đúng chính sách của tổ chức khi cần mở rộng sang AZ mới hoặc khi tải tăng cao.
* Kiểm soát linh hoạt: Người dùng có thể chọn chế độ Tự động (AWS lo việc quản lý IP và AZ) hoặc chế độ Thủ công (người dùng tự phân bổ Elastic IP và chọn AZ). Lưu ý ở chế độ thủ công: nếu dữ liệu sinh ra ở AZ không bật RNAT, lưu lượng sẽ chạy ngẫu nhiên sang một AZ khác có RNAT, có thể gây tốn phí truyền tải chéo.

## 2. Định Tuyến Và Giám Sát

* Định tuyến linh hoạt: RNAT được trang bị sẵn một Route Table mặc định trỏ ra Internet Gateway (IGW). Cấu trúc này cho phép dễ dàng chèn thêm các thiết bị kiểm tra an ninh (như Tường lửa) vào giữa luồng dữ liệu.
* Giám sát toàn diện: Hỗ trợ giám sát qua Amazon CloudWatch với các chỉ số như: ID tài nguyên, ID AZ, IP nguồn/đích, Cổng (Port) nguồn/đích và giao thức.

## 3. Các Mô Hình Triển Khai Phổ Biến

* VPC đi ra Internet (Đơn giản nhất): Lưu lượng từ Subnet nội bộ đi thẳng đến RNAT, sau đó ra Internet Gateway (IGW) rồi ra ngoài mạng.
* VPC đi ra Internet có kiểm tra lưu lượng: Lưu lượng từ Subnet nội bộ trước tiên được đẩy qua Tường lửa (AWS Network Firewall hoặc thiết bị bên thứ 3) để kiểm tra bảo mật, sau đó mới truyền tới RNAT và ra ngoài Internet.

## 4. Các Lưu Ý Quan Trọng Cần Biết

* Mức độ áp dụng: RNAT gắn với toàn bộ VPC, không bị ràng buộc vào từng subnet riêng lẻ. Route Table của RNAT không thể liên kết với các subnet hoặc các RNAT khác.
* Thời gian mở rộng AZ (Scaling time): Ở chế độ tự động, nếu bạn triển khai tài nguyên ở một AZ mới, RNAT sẽ mất trung bình 15 - 20 phút (tối đa 60 phút) để mở rộng sang AZ đó.
* Giới hạn tài nguyên: Mỗi VPC có thể thiết lập tối đa 5 RNAT.
* Hiệu suất: Băng thông hỗ trợ từ 5 Gbps và có thể tự động mở rộng lên tới 100 Gbps mỗi AZ (hỗ trợ các giao thức TCP, UDP, ICMP).
* Điểm hạn chế hiện tại: RNAT hiện chưa hỗ trợ kiểu kết nối hoàn toàn riêng tư (Private connectivity). Đối với nhu cầu này, AWS khuyến nghị vẫn sử dụng Zonal NAT Gateway kiểu cũ.

<br>Link Bài Viết Trên Group: <https://www.facebook.com/groups/660548818043427/user/100025022862424>

> Nguồn tham khảo: [Introducing Amazon VPC Regional NAT Gateway](https://aws.amazon.com/blogs/networking-and-content-delivery/introducing-amazon-vpc-regional-nat-gateway/)