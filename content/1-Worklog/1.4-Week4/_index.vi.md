---
title: "Worklog Tuần 4"
date: 2026-05-14
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Thiết kế cơ sở dữ liệu cho hệ thống.
* Tạo giao diện người dùng (UI) cho hệ thống.
* Nghiên cứu và vận dụng kiến trúc nâng cao (CQRS Pattern) vào việc phát triển các API cốt lõi.
* Triển khai hệ thống xác thực người dùng an toàn với OAuth2 với Google.
* Tối ưu hóa hiệu suất ứng dụng bằng Redis Cache, giải quyết bài toán nhất quán dữ liệu.
* Bước đầu tiếp cận quy trình CI/CD cơ bản.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - **Thực hành:** Thiết kế dữ liệu.<br>&emsp;+ Tìm hiểu những yêu cầu có thể có trong hệ thống. <br>&emsp;+ Thiết kế cơ sở dữ liệu cho hệ thống web server. <br>&emsp;+ Áp dụng phương pháp Code-First với Entity Framework Core Migrations để khởi tạo và quản lý version database. | 08/05/2026 | 08/05/2026 |  |
| 7 | - Tìm hiểu các nguyên tắc thiết kế UI/UX cơ bản cho hệ thống làm bài thi/luyện tập.<br> - **Thực hành:** Thiết kế Giao diện.<br>&emsp;+ Thiết kế giao diện UI cho các chức năng của hệ thống.<br>&emsp;+ Đảm bảo trải nghiệm người dùng cho các luồng thao tác chính. | 09/05/2026 | 09/05/2026 |  |
| CN | Nghỉ | 10/05/2026 | 10/05/2026 |  |
| 2 | - Nghiên cứu lý thuyết về các luồng cấp quyền (Grant Types) trong chuẩn OAuth2.<br> - **Thực hành:** Xác thực và Bảo mật.<br>&emsp;+ Xây dựng API xác thực người dùng.<br>&emsp;+ Tích hợp chuẩn OAuth2 vào hệ thống để quản lý quyền truy cập.<br> - Tìm hiểu về kiến trúc CQRS (Command Query Responsibility Segregation) và phân tách luồng Đọc/Ghi.<br> - **Thực hành:** Xây dựng API (Phần 1).<br>&emsp;+ Áp dụng CQRS Pattern để thiết kế luồng xử lý.<br>&emsp;+ Xây dựng API cho chức năng làm bài kiểm tra và luyện tập. | 11/05/2026 | 11/05/2026 |<https://learn.microsoft.com/vi-vn/aspnet/core/security/authentication/social/google-logins?view=aspnetcore-9.0> <br> <https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs> <br> <https://200lab.io/blog/cqrs-la-gi>|
| 3 | - **Thực hành:** Xây dựng API (Phần 2).<br>&emsp;+ Tiếp tục áp dụng CQRS Pattern.<br>&emsp;+ Xây dựng API cho chức năng quản lý bài viết và luồng CRUD tài nguyên. | 12/05/2026 | 12/05/2026 |  |
| 4 | - Nghiên cứu lý thuyết về các chiến lược Caching (Cache-Aside), cách validate dữ liệu khi cache và các phương pháp giảm thiểu sai sót, đảm bảo tính nhất quán dữ liệu (Data Consistency).<br> - **Thực hành:** Tối ưu hiệu suất.<br>&emsp;+ Cài đặt và sử dụng Redis để cache các dữ liệu được truy cập thường xuyên.<br>&emsp;+ Triển khai cơ chế event-driven để tự động invalidate (xóa) cache khi dữ liệu có sự thay đổi. | 13/05/2026 | 13/05/2026 | <https://learn.microsoft.com/en-us/azure/architecture/patterns/cache-aside> |
| 5 | - Nghiên cứu lý thuyết về Tích hợp và Triển khai liên tục (CI/CD).<br> - **Thực hành:** CI/CD Automation.<br>&emsp;+ Tìm hiểu và cấu hình thử nghiệm CI/CD pipeline với GitHub Actions. | 14/05/2026 | 14/05/2026 | <https://dev.to/mfyz/simple-gitlab-cicd-deployment-via-sshrsync-8b6> |

### Kết quả đạt được tuần 4:

* Hoàn thiện bản thiết kế cơ sở dữ liệu và giao diện UI, tạo nền tảng vững chắc cho quá trình phát triển tính năng.
* Hiểu và xây dựng thành công cơ chế xác thực người dùng an toàn thông qua việc tích hợp OAuth2.
* Nắm vững tư duy và áp dụng CQRS Pattern vào phát triển API (làm bài kiểm tra, luyện tập, quản lý tài nguyên), giúp hệ thống tách biệt rõ ràng luồng đọc/ghi, tăng khả năng mở rộng.
* Hiểu về bản chất của Caching và tính nhất quán dữ liệu. Cải thiện đáng kể tốc độ phản hồi của API nhờ tích hợp Redis Cache, đồng thời cố gắng hết sức để xử lý triệt để bài toán sai lệch dữ liệu bằng cơ chế event-driven cache invalidation.
* Nắm bắt được quy trình tự động hóa kiểm thử và triển khai mã nguồn thông qua GitHub Actions.