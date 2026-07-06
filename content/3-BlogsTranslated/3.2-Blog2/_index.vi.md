---
title: "Blog 2"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Thêm HTTP Security Headers Bằng Amazon CloudFront

Trong bối cảnh an ninh mạng đối mặt với nhiều rủi ro, việc bảo vệ người dùng khỏi các lỗ hổng phổ biến như XSS, clickjacking và man-in-the-middle là vô cùng cấp thiết. Một lớp phòng thủ quan trọng nhưng thường bị bỏ qua là HTTP security headers. Để giải quyết vấn đề này mà không cần những can thiệp phức tạp vào hệ thống gốc, các nhà phát triển và kỹ sư DevOps có thể triển khai Amazon CloudFront nhằm tự động hóa và tối ưu việc thêm các header bảo mật.

Một thành phần quan trọng trong giải pháp là các tập header như Strict-Transport-Security, Content-Security-Policy, hay X-Frame-Options. Thay vì phải điều chỉnh tại máy chủ ứng dụng, CloudFront cung cấp 3 phương pháp linh hoạt để áp dụng các chính sách này ngay tại biên mạng (edge).

## 1. Lợi ích của việc đưa cấu hình bảo mật lên CloudFront

Ban đầu, các hệ thống thường được cấu hình để gắn header bảo mật trực tiếp tại máy chủ gốc (origin server). Tuy nhiên, việc chuyển giao nhiệm vụ này lên CloudFront mang lại nhiều lợi ích rõ rệt.

Kiến trúc này giúp giải quyết tình trạng không thể can thiệp vào mã nguồn của máy chủ gốc (đặc biệt khi dùng nền tảng bên thứ ba). Việc offload logic này cho CloudFront giúp máy chủ gốc tiết kiệm tài nguyên tính toán, chỉ tập trung vào việc phục vụ nội dung cốt lõi. Đồng thời, nó giúp tiết kiệm băng thông giữa CloudFront và máy chủ gốc, mang lại sự linh hoạt tối đa khi quản trị viên cần cập nhật nhanh các lớp phòng thủ.

## 2. Triển khai nhanh chóng với CloudFront Response Headers Policies

Cách đơn giản và tối ưu chi phí nhất (không phát sinh phí, không cần viết code) là sử dụng CloudFront Response Headers Policies.

Hệ thống cung cấp sẵn các Managed policies (chính sách được AWS cấu hình mặc định) chứa các bộ header bảo mật chuẩn xác cho các tình huống phổ biến. Bạn chỉ cần đính kèm chính sách này vào Cache Behavior của CloudFront. Nếu ứng dụng có những đặc thù riêng, bạn hoàn toàn có thể tạo các Custom policies để tinh chỉnh chi tiết từng giá trị như X-XSS-Protection hay Referrer-Policy. Toàn bộ lưu lượng trả về cho người dùng sẽ tự động được gán các header này.

## 3. Tùy biến bảo mật động bằng CloudFront Functions

Đối với những kịch bản yêu cầu hệ thống phải phản ứng linh hoạt, phương pháp cấu hình tĩnh là chưa đủ.

Nếu bạn cần thay đổi giá trị header dựa trên các điều kiện cụ thể (ví dụ: chỉ thêm header khi phát hiện một request header, cookie, hoặc query string nhất định), CloudFront Functions là giải pháp phù hợp. Bằng cách thực thi các đoạn mã JavaScript cực kỳ gọn nhẹ ngay tại các edge locations, hệ thống có thể phân tích request và chèn security headers theo thời gian thực mà không làm tăng độ trễ của trang web.

## 4. Xử lý các kịch bản bảo mật phức tạp với Lambda@Edge

Khi các yêu cầu kiểm soát trở nên phức tạp hơn mức CloudFront Functions có thể đáp ứng, hệ thống sẽ cần đến sức mạnh của Lambda@Edge (hỗ trợ Node.js và Python).

Trong các tình huống cần gọi API ra bên ngoài (network calls), sử dụng các thư viện bảo mật của bên thứ ba, hoặc cần truy cập sâu vào phần nội dung (body) của request để quyết định xem có nên gán header bảo mật hay không, Lambda@Edge cung cấp toàn quyền lập trình. Giải pháp này giúp các hệ thống lớn (như cổng thông tin y tế hay nền tảng thương mại điện tử) đáp ứng được các tiêu chuẩn tuân thủ dữ liệu khắt khe nhất.

## Kết luận

Thông qua việc tận dụng hệ sinh thái Amazon CloudFront bao gồm Response Headers Policies, CloudFront Functions và Lambda@Edge, các tổ chức có thể xây dựng một giải pháp bảo mật linh hoạt và đa lớp. Giải pháp này không chỉ offload gánh nặng cho máy chủ gốc mà còn giúp dễ dàng áp dụng các tiêu chuẩn an toàn web hiện đại. Bằng cách kết hợp kiểm tra định kỳ với các công cụ như Mozilla Observatory, hệ thống có thể liên tục cải thiện điểm số bảo mật và duy trì tính ổn định cho người dùng hợp lệ.
Nguồn tham khảo: 

<br>Link Bài Viết Trên Group: <https://www.facebook.com/groups/660548818043427/user/100025022862424>

> Nguồn tham khảo: [Add Http](https://aws.amazon.com/blogs/networking-and-content-delivery/adding-http-security-headers-using-amazon-cloudfront/)