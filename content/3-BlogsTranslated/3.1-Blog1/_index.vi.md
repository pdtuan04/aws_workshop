---
title: "Blog 1"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# Lợi Ích Khi Kết Hợp Amazon CloudFront với Application Load Balancer
Khi ứng dụng ngày càng phục vụ nhiều người dùng ở các khu vực địa lý khác nhau, việc đảm bảo tốc độ truy cập, tính sẵn sàng và chi phí vận hành hợp lý trở thành một yêu cầu quan trọng. Một trong những kiến trúc được AWS khuyến nghị là kết hợp Amazon CloudFront với Application Load Balancer (ALB).

Thay vì để người dùng truy cập trực tiếp vào ALB, CloudFront sẽ đóng vai trò là điểm truy cập toàn cầu thông qua mạng lưới hàng trăm edge locations. Kiến trúc này mang lại nhiều lợi ích về hiệu suất, bảo mật và tối ưu chi phí, đồng thời vẫn đảm bảo khả năng mở rộng cho các hệ thống phục vụ người dùng trên phạm vi toàn cầu.

## 1. Cải thiện hiệu suất truy cập

Trong mô hình truyền thống, mọi yêu cầu từ người dùng đều được gửi trực tiếp đến ALB đặt tại một AWS Region. Điều này có thể làm tăng độ trễ đối với những người dùng ở xa khu vực triển khai.

Khi sử dụng CloudFront, các nội dung tĩnh như hình ảnh, CSS và JavaScript được lưu trữ tại các edge locations gần người dùng nhất, giúp giảm đáng kể thời gian phản hồi. Đối với nội dung động, CloudFront duy trì các kết nối TCP liên tục (persistent TCP connections) với ALB, giảm chi phí thiết lập lại kết nối TCP/TLS cho mỗi yêu cầu và cải thiện tốc độ phản hồi.

Theo kết quả thử nghiệm của AWS:
* Thời gian Time-To-First-Byte (TTFB) được cải thiện khoảng 15–25% đối với người dùng trong cùng khu vực với origin.
* Đối với các truy cập liên lục địa, mức cải thiện đạt khoảng 35–50%.

Nhờ đó, người dùng có thể nhận được phản hồi nhanh hơn, đặc biệt khi truy cập từ các vị trí địa lý cách xa hạ tầng triển khai.

## 2. Tăng cường bảo mật
![Security](../../images/3-BlogsTranslated/cfblog.png)
Việc đặt CloudFront ở phía trước ALB giúp chuyển lớp bảo vệ ra ngay tại edge thay vì chỉ bảo vệ ở máy chủ gốc. 

Một trong những tính năng nổi bật là CloudFront VPC Origin, cho phép ALB được triển khai trong Private VPC nhưng vẫn có thể phục vụ người dùng thông qua CloudFront. Điều này giúp giảm nguy cơ truy cập trực tiếp vào hạ tầng backend từ Internet.

Bên cạnh đó, CloudFront có thể tích hợp với:
* AWS Shield Standard: Bảo vệ trước các cuộc tấn công DDoS ở tầng mạng.
* AWS WAF: Lọc các yêu cầu độc hại ngay tại edge, giảm tải cho hệ thống backend.
* AWS Certificate Manager: Quản lý chứng chỉ SSL/TLS tập trung.
* Hỗ trợ IPv6 và TLS 1.3: Tăng cường bảo mật cũng như tối ưu hiệu năng kết nối.

Nhờ xử lý lưu lượng ngay tại edge, nhiều cuộc tấn công có thể được ngăn chặn trước khi đến ALB hoặc các máy chủ ứng dụng.

## 3. Tối ưu chi phí vận hành
![Pricing](../../images/3-BlogsTranslated/cfblog2.png)
## 4. Những lưu ý khi chuyển đổi sang kiến trúc CloudFront - ALB
Bên cạnh việc cải thiện hiệu suất, CloudFront còn giúp giảm nhiều khoản chi phí trong quá trình vận hành hệ thống.

* Miễn phí Data Transfer Out: Data Transfer Out (DTO) từ AWS Origin đến CloudFront được miễn phí. Chi phí chủ yếu phát sinh khi CloudFront phân phối dữ liệu đến người dùng cuối, với mức giá được tối ưu hơn nhờ mô hình tính phí theo bậc và các gói ưu đãi của CloudFront.
* Tự động nén dữ liệu: CloudFront tự động nén nội dung trước khi gửi đến người dùng, giúp giảm dung lượng dữ liệu truyền tải và tiết kiệm chi phí băng thông.
* Tái sử dụng kết nối: CloudFront tái sử dụng các kết nối TCP đến ALB, làm giảm số lượng kết nối mới phải thiết lập. Điều này giúp giảm mức tiêu thụ Load Balancer Capacity Unit (LCU) của ALB và góp phần giảm chi phí vận hành.
* Tối ưu DNS: Nếu sử dụng Amazon Route 53 với Alias Record để trỏ tên miền đến CloudFront Distribution, các truy vấn DNS đối với Alias Record cũng không bị tính phí.


AWS khuyến nghị nên thực hiện quá trình chuyển đổi theo từng giai đoạn để hạn chế rủi ro. Một số thực hành tốt bao gồm:

* Sử dụng Route 53 Weighted Routing để chuyển lưu lượng từng bước từ ALB sang CloudFront, thay vì chuyển toàn bộ cùng một lúc.
* Di chuyển AWS WAF từ ALB sang CloudFront để tận dụng khả năng bảo vệ ngay tại edge.
* Nếu ALB sử dụng Host Header Routing, cần cấu hình CloudFront chuyển tiếp header Host để các quy tắc định tuyến vẫn hoạt động chính xác.
* Với Internet-facing ALB, nên cấu hình Custom Header để ALB chỉ chấp nhận các yêu cầu đến từ CloudFront, tránh việc truy cập trực tiếp vào origin.
* Điều chỉnh các chính sách Cache, Origin Request Policy và Response Header Policy phù hợp với đặc điểm của ứng dụng nhằm đảm bảo hiệu suất và tính tương thích.

## 5. Một số tính năng đáng chú ý khác

Ngoài những lợi ích chính, CloudFront còn cung cấp nhiều tính năng hỗ trợ xây dựng hệ thống quy mô lớn như:
* Hỗ trợ triển khai đa Region với khả năng failover tự động.
* Xử lý yêu cầu tại edge bằng CloudFront Functions hoặc Lambda@Edge.
* Hỗ trợ nén nội dung tự động để giảm băng thông.
* Tích hợp với CloudWatch để theo dõi các chỉ số như Cache Hit Ratio, Origin Latency và tỷ lệ lỗi 4xx/5xx, giúp đánh giá hiệu quả hoạt động của hệ thống.

## Kết luận

Việc kết hợp Amazon CloudFront và Application Load Balancer giúp cải thiện hiệu suất truy cập toàn cầu, tăng cường bảo mật và tối ưu chi phí vận hành. Theo các thử nghiệm của AWS, kiến trúc này có thể cải thiện đáng kể thời gian phản hồi, đặc biệt đối với người dùng ở xa khu vực triển khai.

Bên cạnh đó, các tính năng như CloudFront VPC Origin, AWS WAF, AWS Shield, cơ chế cache, nén dữ liệu và tái sử dụng kết nối giúp giảm tải cho hệ thống backend, đồng thời nâng cao khả năng mở rộng và tính sẵn sàng của ứng dụng.

Đối với các hệ thống phục vụ người dùng trên phạm vi toàn cầu, việc triển khai CloudFront phía trước ALB là một kiến trúc đáng cân nhắc nhằm cân bằng giữa hiệu suất, bảo mật và chi phí trong quá trình vận hành.
<br>Link Bài Viết Trên Group: <https://www.facebook.com/groups/660548818043427/user/100025022862424>

> Nguồn tham khảo: [Optimizing Application Performance: The Strategic Benefits of Combining Amazon CloudFront with Application Load Balancers](https://aws.amazon.com/blogs/networking-and-content-delivery/optimizing-application-performance-the-strategic-benefits-of-combining-amazon-cloudfront-with-application-load-balancers/)