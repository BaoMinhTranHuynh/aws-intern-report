---
title: "Blog 3"

weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Phần này sẽ liệt kê và giới thiệu các bài blog mà tôi đã dịch.

### Blog 3 - Các mô hình kiến trúc Generative AI – Phần 2 (Không theo thời gian thực).
Phần 2 của loạt bài này giới thiệu hai mô hình kiến trúc bổ sung cho các quy trình làm việc Generative AI không yêu cầu phản hồi ngay lập tức, rất phù hợp cho các tác vụ tốn nhiều thời gian hoặc xử lý khối lượng dữ liệu lớn theo lịch trình: Xử lý bất đồng bộ có bộ đệm và Xử lý theo lô không tương tác.

Mô hình 4: Xử lý yêu cầu – phản hồi bất đồng bộ có bộ đệm (Buffered asynchronous request response)
Mô hình này sử dụng kiến trúc hướng sự kiện để xử lý các yêu cầu chạy trong thời gian dài (ví dụ: tạo video, phân tích khoa học) nhằm tăng khả năng mở rộng và độ tin cậy.

REST API kết hợp Hàng đợi tin nhắn: Giao diện người dùng (frontend) gửi yêu cầu qua API Gateway và được đệm vào Amazon SQS. Lớp trung gian (Lambda/EC2/Fargate) xử lý thông điệp theo lô, gọi LLM, lưu kết quả vào DynamoDB, và frontend truy vấn (polling) để nhận phản hồi.

WebSocket API kết hợp Hàng đợi tin nhắn: Là một biến thể, sử dụng API Gateway WebSocket API. Sau khi xử lý, lớp trung gian chủ động gửi kết quả trở lại client ngay lập tức (không cần polling) thông qua kết nối WebSocket.

Mô hình 5: Phân tán song song đa phương thức (Multimodal parallel fan-out)
Mô hình này áp dụng cho các trường hợp cần tương tác với nhiều mô hình LLM, nguồn dữ liệu hoặc agent khác nhau. Nó sử dụng mẫu hình fan-out thông qua Amazon EventBridge hoặc Amazon SNS để phân phối các thông điệp cụ thể đến nhiều điểm đích song song, chia nhỏ và thực thi các tác vụ phức tạp đồng thời, giúp giảm tổng thời gian tạo kết quả.

Mô hình 6: Xử lý theo lô không tương tác (Non-interactive batch processing)
Lý tưởng cho việc xử lý khối lượng dữ liệu lớn, theo lịch trình hoặc kích hoạt theo sự kiện (ví dụ: tối ưu hóa hàng loạt hình ảnh, tạo báo cáo định kỳ). Mẫu hình này sử dụng các dịch vụ như AWS Step Functions hoặc AWS Glue để xây dựng pipeline xử lý dữ liệu và suy luận (inferencing) theo mô hình serverless, tối ưu hóa việc sử dụng tài nguyên và tăng thông lượng.
[Đọc toàn bộ bài dịch trên Google Docs](https://docs.google.com/document/d/1yOGQn6Z0tj7i5G_-li2U0zU6pFMy3pI_IvAF1khlEfY/edit?usp=sharing)