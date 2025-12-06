---
title: "Event 2"

weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# BÁO CÁO SỰ KIỆN: DEVOPS TRÊN AWS

&emsp;**Tên Sự kiện:** AWS Cloud Mastery Series #2 : DevOps trên AWS.

&emsp;**Ngày:** Thứ Hai, 17 tháng 11, 2025.

&emsp;**Thời gian:** 8:30 Sáng – 5:00 Chiều.

&emsp;**Địa điểm:** Văn phòng AWS Việt Nam, Tòa nhà Tài chính Bitexco, Quận 1, TP. Hồ Chí Minh.

&emsp;**Mục tiêu Sự kiện:** Cung cấp kiến thức toàn diện về Văn hóa DevOps, các nguyên tắc, số liệu hiệu suất và bộ dịch vụ DevOps của AWS để xây dựng các đường ống CI/CD, IaC và Khả năng Quan sát (Observability).

---

## PHẦN SÁNG (8:30 Sáng – 12:00 Chiều): CI/CD & CƠ SỞ HẠ TẦNG DƯỚI DẠNG MÃ (IAC)

### 1. Chào mừng & Tư duy DevOps (8:30 – 9:00 Sáng)
* Sự kiện bắt đầu bằng việc **tóm tắt nhanh** từ phiên AI/ML trước đó, đặt bối cảnh cho việc đưa các mô hình/ứng dụng vào sản xuất.
* Trọng tâm là **văn hóa và các nguyên tắc DevOps**, nhấn mạnh sự hợp tác giữa Phát triển (Dev) và Vận hành (Ops).
* Giới thiệu về **các số liệu hiệu suất chính** như **DORA** (Tần suất Triển khai, Thời gian Dẫn đầu cho Thay đổi, MTTR, Tỷ lệ Thất bại Thay đổi) và **MTTR** (Thời gian Trung bình để Phục hồi).

### 2. Các Dịch vụ DevOps của AWS – Xây dựng Đường ống CI/CD (9:00 – 10:30 Sáng)
Phần này đi sâu vào bộ công cụ AWS CodeFamily để tự động hóa **Tích hợp Liên tục (CI)** và **Triển khai Liên tục (CD)**:
* **Kiểm soát Nguồn:** Sử dụng **AWS CodeCommit** và thảo luận về các chiến lược quản lý mã nguồn như **GitFlow** và **Trunk-based**.
* **Xây dựng & Thử nghiệm:** Cấu hình **CodeBuild** để tự động hóa việc biên dịch và chạy các đường ống thử nghiệm.
* **Triển khai:** Phân tích các chiến lược triển khai nâng cao với **CodeDeploy**, bao gồm **Blue/Green, Canary, và Rolling updates**.
* **Điều phối:** Sử dụng **CodePipeline** để tự động hóa toàn bộ quy trình từ cam kết mã nguồn đến môi trường sản xuất.
* **Demo:** Một buổi trình diễn trực quan về một đường ống CI/CD hoàn chỉnh trên AWS.

### 3. Cơ sở hạ tầng dưới dạng Mã (IaC) (10:45 Sáng – 12:00 Chiều)
IaC là nền tảng của DevOps hiện đại, đảm bảo tính nhất quán và khả năng tái tạo môi trường:
* **AWS CloudFormation:** Tìm hiểu về **Mẫu (Templates), Ngăn xếp (Stacks),** và cách sử dụng **Phát hiện Độ lệch (Drift Detection)** để xác định sự khác biệt giữa trạng thái thực tế và mã nguồn.
* **AWS CDK (Cloud Development Kit):** Giới thiệu CDK như một phương pháp tiếp cận hiện đại hơn, sử dụng các ngôn ngữ lập trình quen thuộc (TypeScript, Python,...) để định nghĩa cơ sở hạ tầng thông qua **Constructs** và **các mẫu có thể tái sử dụng**.
* **Demo & Thảo luận:** Trình diễn việc triển khai cơ sở hạ tầng bằng cả CloudFormation và CDK, cùng với thảo luận về tiêu chí lựa chọn công cụ IaC phù hợp.

---

## PHẦN CHIỀU (1:00 Chiều – 5:00 Chiều): CONTAINER, KHẢ NĂNG QUAN SÁT & CÁC THỰC TIỄN TỐT NHẤT

### 4. Dịch vụ Container trên AWS (1:00 – 2:30 Chiều)
* **Khái niệm cơ bản về Docker:** Ôn tập các khái niệm cơ bản liên quan đến **Microservices** và **Containerization**.
* **Amazon ECR (Elastic Container Registry):** Dịch vụ lưu trữ các image container, bao gồm các tính năng **quét image** và **chính sách vòng đời (lifecycle policies)**.
* **Amazon ECS & EKS:** So sánh hai dịch vụ điều phối container chính: **ECS** (đơn giản hơn, tích hợp AWS) và **EKS** (dựa trên Kubernetes). Phân tích các chiến lược triển khai và mở rộng quy mô.
* **AWS App Runner:** Một giải pháp đơn giản hóa để triển khai container, tập trung vào mã nguồn hơn là cơ sở hạ tầng.
* **Demo & Nghiên cứu điển hình:** Minh họa việc triển khai kiến trúc microservices và so sánh các dịch vụ.

### 5. Giám sát & Khả năng Quan sát (2:45 – 4:00 Chiều)
* **CloudWatch:** Công cụ cốt lõi để thu thập **số liệu, nhật ký, báo động và bảng điều khiển** trên toàn bộ hệ sinh thái AWS.
* **AWS X-Ray:** Cung cấp **Truy vết Phân tán (Distributed Tracing)** để theo dõi luồng yêu cầu trên các microservices, giúp xác định các điểm nghẽn và vấn đề hiệu suất.
* **Demo:** Thiết lập một hệ thống khả năng quan sát toàn diện (Full-stack observability).
* **Các Thực tiễn Tốt nhất:** Các thực tiễn tốt nhất cho **Cảnh báo (Alerting), bảng điều khiển,** và quy trình **trực ban (on-call)**.

### 6. Thực tiễn Tốt nhất & Nghiên cứu Điển hình về DevOps (4:00 – 4:45 Chiều)
* **Các Chiến lược Triển khai Nâng cao:** Thảo luận về **Cờ tính năng (Feature flags)** và **kiểm thử A/B** trong đường ống triển khai.
* **Thử nghiệm tự động** và tích hợp sâu với CI/CD.
* **Quản lý Sự cố:** Quản lý các sự cố và tầm quan trọng của **Báo cáo Hậu sự cố (Postmortems)** để học hỏi và cải tiến.
* **Nghiên cứu Điển hình:** Các bài học kinh nghiệm từ các công ty khởi nghiệp và doanh nghiệp lớn đã trải qua quá trình chuyển đổi DevOps thành công.

### 7. Hỏi đáp & Tổng kết (4:45 – 5:00 Chiều)
* Giải đáp các câu hỏi chuyên sâu.
* Cung cấp thông tin về **lộ trình nghề nghiệp DevOps** và các chứng chỉ AWS liên quan.

---