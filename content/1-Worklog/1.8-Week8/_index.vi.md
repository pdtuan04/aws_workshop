---
title: "Worklog Tuần 8"
date: 2026-06-11
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Hoàn thiện bản vẽ sơ đồ kiến trúc AWS tổng thể cho hệ thống EngExam.
* Phát triển tính năng tạo đề thi tùy chỉnh dựa trên lịch sử lỗi sai của người dùng.
* Nghiên cứu và nâng cấp lại quy trình CI/CD từ việc dùng SSH thủ công sang ứng dụng AWS CodeDeploy và Docker Hub.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 6 | - **Thực hành:** Thiết kế kiến trúc AWS.<br>&emsp;+ Thiết kế và hoàn thiện luồng kiến trúc AWS tổng thể cho hệ thống EngExam.<br>&emsp;+ Xác định các thành phần và vẽ sơ đồ kiến trúc thể hiện cách thức tương tác giữa các dịch vụ (VPC, EC2, RDS, S3, ALB, ASG,...). | 05/06/2026 | 05/06/2026 | <https://youtu.be/l8isyDe-GwY> |
| 7 | - Tìm hiểu lý thuyết về dịch vụ AWS CodeDeploy.<br> - Nghiên cứu cơ chế tự động triển khai ứng dụng của CodeDeploy khi có phiên bản code mới được đẩy lên repository. | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html> |
| CN | Nghỉ | 07/06/2026 | 07/06/2026 | |
| 2 | - **Thực hành:** Tính năng Đề thi.<br>&emsp;+ Phân tích logic và truy xuất dữ liệu các câu hỏi mà người dùng thường trả lời sai từ lịch sử làm bài.<br>&emsp;+ Xây dựng hoàn chỉnh API tạo đề thi ôn tập tự động dựa trên các câu hỏi hỏng/sai của người dùng. | 08/06/2026 | 08/06/2026 | |
| 3 | - **Thực hành:** Nâng cấp CI/CD (Phần 1).<br>&emsp;+ Cấu hình lại luồng pipeline (GitHub Actions) để tự động build ứng dụng ASP.NET Core.<br>&emsp;+ Tích hợp tự động push Docker image lên Docker Hub. | 09/06/2026 | 09/06/2026 | <https://docs.docker.com/build/ci/github-actions/> |
| 4 | - **Thực hành:** Nâng cấp CI/CD (Phần 2).<br>&emsp;+ Tích hợp AWS CodeDeploy vào quy trình CI/CD.<br>&emsp;+ Loại bỏ phương pháp SSH đơn giản, thiết lập kịch bản (AppSpec) để CodeDeploy tự động pull image mới nhất và cập nhật ứng dụng trên EC2. | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/reference-appspec-file.html> |
| 5 | - **Thực hành:** Kiểm thử hệ thống.<br>&emsp;+ Kiểm thử luồng CI/CD mới từ bước push code đến khi ứng dụng được tự động deploy thành công.<br>&emsp;+ Kiểm tra lại tính chính xác của chức năng sinh đề thi từ câu hỏi sai. | 11/06/2026 | 11/06/2026 |  |

### Kết quả đạt được tuần 8:

* Hoàn thiện và hệ thống hóa toàn bộ luồng kiến trúc hạ tầng AWS thông qua bản vẽ sơ đồ kiến trúc trực quan, rõ ràng.
* Xây dựng thành công tính năng học tập thông minh: tự động tạo đề thi ôn luyện từ những câu hỏi người dùng hay sai, giúp tối ưu hóa trải nghiệm học tập trên hệ thống EngExam.
* Nắm được cơ chế hoạt động của AWS CodeDeploy.
* Nâng cấp thành công quy trình CI/CD: tự động hóa quá trình build, lưu trữ image trên Docker Hub và deploy ứng dụng mượt mà qua CodeDeploy, thay thế hoàn toàn cho thao tác SSH thủ công trước đây.