---
title: "Bản đề xuất"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Hệ Thống Học Tiếng Anh Trên AWS
## Giải pháp Hệ thống Ôn luyện Tiếng Anh triển khai trên kiến trúc AWS High Availability

### 1. Tóm tắt điều hành
Hệ thống ôn luyện tiếng Anh được thiết kế nhằm cung cấp một nền tảng học tập, kết hợp các phương pháp ghi nhớ và tương tác cộng đồng. Các tính năng cốt lõi bao gồm hệ thống Flashcard thông minh giúp ghi nhớ từ vựng, thư viện bài viết tiếng Anh đa dạng, chức năng luyện tập thực hành và hệ thống bình luận phân cấp để tăng cường trao đổi giữa người học. Hệ thống tận dụng sức mạnh của các dịch vụ đám mây của AWS đảm bảo tính sẵn sàng cao (High Availability), khả năng mở rộng tự động và tích hợp CI/CD tự động hoá hoàn toàn.

### 2. Tuyên bố vấn đề
*Vấn đề hiện tại:*
Mặc dù thị trường hiện nay có rất nhiều nền tảng học tiếng Anh chất lượng, người học thường phải đối mặt với sự phân mảnh: họ dùng một ứng dụng riêng để học Flashcard (như Quizlet, Anki), đọc bài viết ở một trang web khác. Việc thiếu một môi trường "Tất cả trong một" (All-in-one) có tính gắn kết cao làm gián đoạn luồng tập trung của người học.

*Giải pháp:*
Phát triển một hệ thống học tập tập trung tích hợp đầy đủ tính năng ôn luyện. Hệ thống tận dụng hạ tầng AWS với sự kết hợp của WAF, CloudFront và S3 để phân phối nội dung tĩnh nhanh chóng và bảo mật. Application Load Balancer (ALB) kết hợp với Auto Scaling Group sẽ điều phối traffic đến các máy chủ ứng dụng chạy Docker container. Dữ liệu được quản lý an toàn trong các Private Subnet với SQL Server và tăng tốc truy xuất bằng ElastiCache (Valkey). Quá trình phát triển được tinh gọn nhờ luồng CI/CD từ GitHub Actions đến DockerHub và AWS CodeDeploy.

*Lợi ích:*
Giải pháp mang lại trải nghiệm học tập mượt mà, tốc độ tải trang nhanh, không gián đoạn nhờ cơ chế cân bằng tải và chịu lỗi. Việc thiết lập hạ tầng bài bản tạo nền tảng vững chắc cho quá trình thực tập tốt nghiệp và phát triển dự án thực tế, đồng thời kiểm soát chi phí hiệu quả bằng cách sử dụng các tier miễn phí (CloudFront, WAF) và các node có kích thước phù hợp (t3.micro, t4g.micro).

### 3. Kiến trúc giải pháp  
Hệ thống vận hành hoàn toàn trong môi trường mạng an toàn Amazon VPC trải rộng trên nhiều Availability Zone nhằm đảm bảo tính sẵn sàng cao (High Availability).

![EngExam Cloud & Deployment Architecture](../images/2-proposal/architechture.drawio.png)

*Luồng tương tác dữ liệu:*
1. User gửi request tới hệ thống, đi qua Cloudfont 
2. Thông qua CloudFont check lớp phòng vệ AWS WAF rules đầu tiên để lọc các cuộc tấn công web phổ biến.
3. Các request yêu cầu tài nguyên tĩnh được CloudFront xử lý trực tiếp và giảm tải thông qua Amazon S3 Bucket.
4. Các request động (API) được CloudFront điều hướng qua cổng Internet Gateway (IG) để đi vào VPC.
5. Luồng traffic đi tới Application Load Balancer (ALB) để phân phối tải.
6. ALB điều phối đều traffic đến các máy chủ EC2 nằm trong Auto Scaling Group thuộc các Private Subnet.
7. Các dữ liệu truy vấn thường xuyên hoặc cấu hình đề thi được phân phối và lưu cache trực tiếp tại Amazon ElastiCache (Valkey) Replica Node & Primary Node để giảm tải cho RDS.
8. Các EC2 Instance xử lý logic nghiệp vụ và tương tác với cơ sở dữ liệu Amazon RDS (SQL Server) cấu hình theo cụm Primary DB và Standby DB để tự động chuyển vùng khi có sự cố.
9. Khi các EC2 trong private subnet cần tải thư viện hoặc kết nối Internet (gửi mail, kết nối Docker Hub), luồng outbound sẽ truyền qua Regional NAT Gateway tập trung để tối ưu chi phí.
10. Từ Regional NAT Gateway, luồng traffic đi ra ngoài qua Internet Gateway.
11. Amazon CloudWatch liên tục giám sát các chỉ số hiệu năng (CPU, Network) của các EC2 instance.
12. Khi tải hệ thống vượt ngưỡng thiết lập, CloudWatch kích hoạt Alarm.
13. Alarm phát lệnh Trigger Scaling yêu cầu Auto Scaling Group tự động thêm máy chủ (Scale-out).
14. Đồng thời, một thông báo Send Notifications được chuyển tới Amazon SNS để gửi email cảnh báo tự động đến quản trị viên khi một instance mới được khởi tạo.

*Luồng tự động hóa CI/CD:*

15. Developer tiến hành commit và Push Code lên GitHub Repository.
16. Hành động push code tự động kích hoạt GitHub Actions Workflows để khởi chạy quá trình kiểm thử và Build Code To Image.
17. Docker image sau khi build thành công sẽ được Push lên kho lưu trữ Docker Hub.
18. Pipeline tiến hành nén mã nguồn cấu hình triển khai thành một Publish Deploy Artifact.
19. File nén này Zip File được đẩy trực tiếp lên Amazon S3 Bucket lưu trữ tạm thời dành cho việc triển khai.
20. GitHub Actions gọi dịch vụ AWS CodeDeploy thông báo có phiên bản mới.
21. AWS CodeDeploy Agent trên các máy chủ truy cập S3 để Get Files chứa artifact.
22. CodeDeploy thực hiện kịch bản deployment.
23. Ra lệnh cho toàn bộ các EC2 kéo image mới nhất từ Docker Hub về.
### 4. Triển khai kỹ thuật

*Các giai đoạn triển khai*
Dự án được thực hiện xuyên suốt trong kỳ thực tập, chia thành 3 giai đoạn chính nhằm đảm bảo tiến độ từ việc nắm bắt công nghệ đến khi hoàn thiện hệ thống:
1. Nghiên cứu và làm quen dịch vụ nền tảng (Tháng 1): Tập trung nghiên cứu lý thuyết và thực hành các bài lab cơ bản trên AWS. Mục tiêu của giai đoạn này là làm quen thao tác và hiểu cơ chế hoạt động của các dịch vụ hạ tầng cốt lõi (như VPC, EC2, RDS, S3).
2. Định hình kiến trúc và tính toán chi phí (Đầu Tháng 2): Tiến hành phác thảo và vẽ sơ đồ kiến trúc hệ thống tổng thể. Lập bảng ước tính chi phí hạ tầng (sử dụng AWS Pricing Calculator), từ đó đưa ra các quyết định điều chỉnh dịch vụ và kiến trúc nhằm tối ưu hóa ngân sách vận hành.
3. Phát triển và tích hợp hệ thống (Giữa Tháng 2): Bắt tay vào quá trình xây dựng thực tế. Lập trình các tính năng cốt lõi (Backend & Frontend) và từng bước tích hợp, triển khai các dịch vụ nâng cao (Auto Scaling, ALB, ElastiCache, CI/CD, RabbitMQ, WAF) lên môi trường Cloud.
4. Kiểm thử và hoàn thiện (Cuối Tháng 3): Rà soát lại toàn bộ dự án. Tiến hành kiểm thử các chức năng và khắc phục dứt điểm các lỗi phát sinh. Đóng gói môi trường và hoàn tất các tài liệu báo cáo cuối kỳ.

*Yêu cầu kỹ thuật*
* Hạ tầng Đám mây (AWS): Yêu cầu kiến thức cấu hình mạng VPC (Public/Private Subnet, Internet Gateway, Regional NAT Gateway). Có khả năng thiết lập cụm máy chủ EC2 hoạt động dưới Auto Scaling Group và ALB. Sử dụng Amazon S3 kết hợp CloudFront để phân phối nội dung tĩnh, tích hợp rào chắn bảo mật AWS WAF. Lưu trữ dữ liệu với RDS (SQL Server) và thiết lập bộ nhớ đệm ElastiCache (Valkey).
* Kiến trúc & Backend (.NET): Sử dụng C# ASP.NET Core, Entity Framework Core. Nắm tư duy thiết kế kiến trúc CQRS để phân tách luồng Đọc/Ghi. Sử dụnng Message Broker (cài đặt RabbitMQ và MassTransit) để xử lý event-driven và đồng bộ dữ liệu phân tán.
* CI/CD & Tự động hóa: Dùng công nghệ ảo hóa Container (Docker, Docker Compose). Có khả năng viết kịch bản tự động hóa (Pipeline) bằng GitHub Actions để build image, đẩy lên Docker Hub và cấu hình AppSpec cho AWS CodeDeploy thực hiện In-Place Deployment.
* Frontend: Kỹ năng phát triển giao diện người dùng bằng React, đảm bảo trải nghiệm mượt mà cho các luồng thao tác chính như làm bài thi trắc nghiệm, lật thẻ flashcard và tương tác bình luận.
### 5. Lộ trình & Mốc triển khai

Dự án được lên kế hoạch triển khai gói gọn trong 3 tháng thực tập với các cột mốc công việc như sau:

* Tháng 1: Khởi động và Làm quen nền tảng:
  * Nghiên cứu lý thuyết và thực hành lab các dịch vụ AWS cơ bản (VPC, EC2, RDS, S3).
  * Ôn tập công nghệ phát triển (ASP.NET Core, React) và Docker.

* Tháng 2: Thiết kế kiến trúc và Bắt đầu xây dựng
  * *Đầu tháng:* Phác thảo sơ đồ kiến trúc tổng thể, tính toán và tối ưu chi phí hạ tầng.
  * *Giữa - Cuối tháng:* Xây dựng tính năng cốt lõi (áp dụng CQRS). Tích hợp hạ tầng lên môi trường Cloud (ALB, Auto Scaling) và thiết lập CI/CD cơ bản.

* Tháng 3: Tối ưu, Kiểm thử và Đóng gói
  * Hoàn thiện quy trình CI/CD (AWS CodeDeploy), đồng bộ dữ liệu (RabbitMQ), cấu hình Cache (Valkey) và bảo mật (WAF).
  * Khắc phục dứt điểm lỗi, quay video demo và hoàn tất tài liệu báo cáo cuối kỳ.

### 6. Ước tính ngân sách

*Chi phí hạ tầng*
- Amazon EC2: 9,42 USD/tháng (Instance t3.small).
- Amazon RDS: 22,63 USD/tháng (1 Instance db.t3.micro, SQL Server Express Edition miễn phí bản quyền).
- Amazon ElastiCache: 14,02 USD/tháng (Cache.t4g.micro, engine Valkey dạng On-Demand).
- Amazon S3 Standard: 0,25 USD/tháng (Ước lượng lưu trữ 10 GB tài nguyên tĩnh với đơn giá 0,025 USD/GB).
- Amazon CloudFront & AWS WAF: 0,00 USD/tháng (Gói Free Tier kèm WAF hỗ trợ rule cơ bản).
- AWS CodeDeploy: 0,00 USD/tháng (Hoàn toàn miễn phí khi triển khai mã nguồn lên EC2/Auto Scaling Group).
- Amazon CloudWatch: 0,00 USD/tháng (Giám sát hiệu năng EC2 cơ bản nằm trong Free Tier).
- Amazon SNS: 0,00 USD/tháng (Gửi email cảnh báo tự động nằm trong Free Tier).
- Docker Hub: 0,00 USD/tháng (Tài khoản Free Tier cho Public Repository).

*Tổng*: 46,32 USD/tháng.

### 7. Đánh giá rủi ro
*Ma trận rủi ro*
- Cấu hình sai bảo mật (Security Groups/VPC): Ảnh hưởng cao, xác suất trung bình.
- Lỗi triển khai (Downtime khi update): Ảnh hưởng cao.
- Chi phí phát sinh ngoài ý muốn (Đặc biệt là NAT Gateway và Data Transfer): Ảnh hưởng trung bình, xác suất trung bình.

*Chiến lược giảm thiểu*
- Chỉ mở port cần thiết, đưa toàn bộ DB, Elastic Cache và EC2 xử lý vào Private Subnet.
- Cấu hình Amazon CloudFront để ép buộc chuyển hướng toàn bộ luồng truy cập từ HTTP sang HTTPS (Redirect HTTP to HTTPS).
- Cài đặt AWS Budgets và CloudWatch Billing Alarm để cảnh báo ngay lập tức nếu chi phí vượt mức cho phép.

### 8. Kết quả kỳ vọng
- Về Kỹ thuật: Xây dựng thành công một hệ thống ôn luyện tiếng Anh hoạt động ổn định, có khả năng chịu lỗi (fault-tolerant) nhờ Multi-AZ và tự động mở rộng theo lượng truy cập. Quy trình triển khai được tự động hóa hoàn toàn từ lúc push code.
- Về Sản phẩm: Người dùng có một nền tảng mượt mà để thực hành từ vựng qua Flashcard, làm bài tiếng anh, đọc bài viết và trao đổi học thuật thông qua hệ thống bình luận phân cấp.