---
title: "Bản đề xuất"

weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Tại phần này, bạn cần tóm tắt các nội dung trong workshop mà bạn **dự tính** sẽ làm.

# IoT Weather Platform for Lab Research  
## Giải pháp AWS Serverless hợp nhất cho giám sát thời tiết thời gian thực  

### 1. Tóm tắt điều hành

Smart Resume Analyzer là một nền tảng web serverless cho phép đánh giá mức độ phù hợp giữa CV của ứng viên và Job Description (JD). Hệ thống sẽ tạo ra Fit Score, phát hiện khoảng trống kỹ năng và đưa ra đề xuất học tập cá nhân hóa.
Giải pháp được triển khai bởi nhóm 5 thành viên trong 4 tuần trên AWS với các dịch vụ quản lý theo mô hình trả phí theo nhu cầu, giúp tối ưu chi phí gần như bằng 0 cho quy mô demo. Giao diện được xây dựng bằng Next.js và triển khai qua AWS Amplify; backend sử dụng API Gateway + Lambda cùng với DynamoDB, S3, Comprehend, Textract và Cognito.

Kết quả chính

Tăng tốc quá trình sàng lọc CV lên đến 90% cho các kịch bản demo.

Fit Score khách quan, có báo cáo trực quan.

Lộ trình học tập được gợi ý phù hợp với từng ứng viên.

2) Vấn đề
2.1 Vấn đề là gì?

Nhà tuyển dụng mất nhiều thời gian đọc thủ công CV và so sánh với JD.

Ứng viên không biết rõ mình thiếu những kỹ năng nào để cải thiện.

Các công cụ hiện có thường đắt và không phù hợp thị trường Việt Nam/Đông Nam Á.

2.2 Giải pháp

Tải lên CV (PDF/DOCX) và JD → tự động trích xuất và phân tích NLP.

Phát hiện kỹ năng, kinh nghiệm, học vấn → tính Fit Score so với JD.

Đề xuất kỹ năng cần học thêm, tham chiếu theo SkillOntology trong DynamoDB.

Đăng nhập bảo mật bằng Cognito, kết quả hiển thị trực quan trên dashboard Next.js.

3) Kiến trúc giải pháp (tổng quan)

Kiến trúc serverless, vận hành theo sự kiện trên AWS.

Thành phần chính

Frontend: Next.js UI (Amplify Hosting) cho tải lên và xem kết quả.

API Layer: Amazon API Gateway → AWS Lambda functions.

Xử lý:

parseResume → Textract (nếu là PDF scan) → chuẩn hóa văn bản.

nlpAnalyze → Comprehend → phát hiện entity/kỹ năng.

recommendSkills → so sánh với JD + SkillOntology trong DynamoDB.

Dữ liệu: DynamoDB (kết quả, ontology), S3 (lưu tạm CV/JD).

Danh tính: Cognito (JWT).

Ops: IaC với AWS SAM, CI/CD qua CodeBuild + CodePipeline, logging trong CloudWatch.

(Biểu đồ Mermaid được cung cấp riêng.)

4) Triển khai kỹ thuật
4.1 Công nghệ sử dụng

Backend: .NET 8 (C# Minimal API chạy Lambda)

Frontend: Next.js + TailwindCSS (Amplify Hosting)

AWS: Lambda, API Gateway, DynamoDB, S3, Cognito, Comprehend, Textract

IaC: AWS SAM

CI/CD: CodeBuild + CodePipeline

4.2 Quy trình end-to-end

Người dùng đăng nhập qua Cognito để lấy JWT.

Frontend yêu cầu presigned URL để tải CV/JD lên S3.

API Gateway gọi Lambda parseResume:

Nếu là PDF scan → sử dụng Textract trích xuất văn bản.

Làm sạch & chuẩn hóa → lưu tạm trên S3.

Lambda nlpAnalyze dùng Comprehend nhận diện kỹ năng → lưu vào DynamoDB.

Lambda recommendSkills lấy SkillOntology từ DynamoDB → so sánh CV với JD → trả Fit Score và khoảng trống kỹ năng.

Frontend gọi API để lấy kết quả → hiển thị biểu đồ và bảng.

4.3 Mô hình dữ liệu (DynamoDB – rút gọn)

Bảng Profiles (PK: userId, SK: profileId) – lưu dữ liệu CV parse mới nhất.

Bảng Analyses (PK: analysisId) – Fit Score, gaps, timestamps.

Bảng SkillOntology (PK: skillId, thuộc tính: name, tags, learningPath[]).

4.4 API (mức độ tổng quan)

POST /upload-url → cấp presigned URL cho upload CV/JD.

POST /analyze → chạy pipeline cho cặp file đã upload.

GET /analyses/{id} → lấy Fit Score & đề xuất.

GET /skills/{id} → (tuỳ chọn) lấy thông tin lộ trình học.

5) Kế hoạch & Mốc thời gian (4 tuần)
Tuần	Mốc hoàn thành	Sản phẩm bàn giao
1	Thiết lập nền tảng	SAM template, bảng DynamoDB, Cognito, UI cơ bản
2	Parsing & NLP	parseResume, nlpAnalyze, parsing JD, unit test
3	Gợi ý kỹ năng & tích hợp FE	recommendSkills, dashboard, biểu đồ
4	Demo & hoàn thiện	Test E2E, logging, tối ưu chi phí, slide demo
6) Ước tính chi phí (mức demo)

Giả định < 500 lượt request/tháng

Lambda: ~$0.02

API Gateway: ~$0.01

S3 (dung lượng nhỏ): ~$0.10

DynamoDB (on-demand): ~$0.05

Amplify Hosting: ~$0.30

Comprehend + Textract (ít trang): ~$0.40

Cognito: $0.00
Tổng ≈ $0.9 / tháng (~$10 / năm)

7) Bảo mật, Rủi ro & Giảm thiểu

Bảo mật

S3 private với SSE-KMS; chỉ cho upload qua presigned URL.

IAM least privilege; API yêu cầu Cognito JWT.

Ẩn thông tin nhạy cảm trong log; cảnh báo bằng CloudWatch.

Có thể cấu hình xóa file CV/JD sau khi phân tích.

Rủi ro & hướng xử lý

Độ chính xác NLP: hỗ trợ nhiều định dạng + fallback theo rule.

CV lớn/không chuẩn: xác thực size/format trước khi xử lý.

Tăng chi phí bất thường: AWS Budget alarm; giới hạn số trang mỗi lần upload.

8) Kết quả kỳ vọng

Tự động so khớp CV – JD với Fit Score minh bạch.

Báo cáo trực quan về kỹ năng trùng khớp và khoảng trống kỹ năng + lộ trình học tập.

Kiến trúc serverless dễ mở rộng, tiết kiệm chi phí, phù hợp demo và localize.

📄 Tài liệu đề xuất (Google Docs)

👉 Xem bản đề xuất tại đây:
[GOOGLE DOC LINK](https://docs.google.com/document/d/1ALFieRvZWl1Azg3C8a7L8Z-iL6-chpzS/edit?usp=sharing&ouid=100398969873071071371&rtpof=true&sd=true)