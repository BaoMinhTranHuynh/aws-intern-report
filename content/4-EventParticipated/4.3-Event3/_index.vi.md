---
title: "Event 2"

weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# BÁO CÁO SỰ KIỆN: TRỤ CỘT BẢO MẬT CỦA AWS WELL-ARCHITECTED

&emsp;**Sự kiện:** AWS Cloud Mastery Series #3: Thực hành Trụ cột Bảo mật của AWS Well-Architected.

&emsp;**Ngày:** Thứ Bảy, 29 tháng 11, 2025.

&emsp;**Thời gian:** 8:30 Sáng – 12:00 Trưa (GMT+7).

&emsp;**Địa điểm:** Văn phòng AWS Việt Nam, Tòa nhà Tài chính Bitexco, Quận 1, TP. Hồ Chí Minh.

&emsp;**Mục tiêu Sự kiện:** Cung cấp kiến thức chuyên sâu về 5 trụ cột của Trụ cột Bảo mật trong Khung Well-Architected, bao gồm các nguyên tắc cốt lõi, dịch vụ và chiến lược phòng thủ.

---

## TÓM TẮT CHƯƠNG TRÌNH

| Thời gian         | Chủ đề                                            | Trọng tâm Chính                                                                                                           |
|:------------------|:-------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------|
| **8:30 – 8:50**   | **Khai mạc & Nền tảng Bảo mật**                  | Vai trò của Trụ cột Bảo mật, Mô hình Trách nhiệm Chia sẻ, và các mối đe dọa hàng đầu trên đám mây tại Việt Nam.               |
| **8:50 – 9:30**   | **Trụ cột 1: Quản lý Danh tính & Truy cập (IAM)** | Kiến trúc IAM hiện đại (Người dùng, Vai trò, Chính sách), IAM Identity Center, SCP, MFA, và Demo Access Analyzer.               |
| **9:30 – 9:55**   | **Trụ cột 2: Phát hiện**                          | Giám sát liên tục với CloudTrail, GuardDuty, Security Hub, và mô hình Phát hiện-dưới-dạng-Mã (Detection-as-Code).                   |
| **10:10 – 10:40** | **Trụ cột 3: Bảo vệ Cơ sở hạ tầng**              | Bảo mật mạng (Phân đoạn VPC, SG vs NACL), WAF, Network Firewall, và bảo mật Tải công việc (Workload security).                        |
| **10:40 – 11:10** | **Trụ cột 4: Bảo vệ Dữ liệu**                    | Mã hóa (lúc nghỉ & khi truyền tải), Quản lý Khóa (KMS), Quản lý Bí mật (Secrets Manager), và Phân loại Dữ liệu.                      |
| **11:10 – 11:40** | **Trụ cột 5: Ứng phó Sự cố**                      | Vòng đời IR của AWS, Sách hướng dẫn (Playbooks) (Mã bị lộ, Lộ S3), và phản hồi tự động (Auto-response).                                   |
| **11:40 – 12:00** | **Tổng kết & Hỏi đáp**                            | Các cạm bẫy thường gặp và lộ trình học Chứng chỉ chuyên môn Bảo mật.                                                                                               |

---

## KIẾN THỨC CHUYÊN SÂU THEO 5 TRỤ CỘT

### 1. Nền tảng Bảo mật & Các Nguyên tắc Cốt lõi

* **Nguyên tắc Cốt lõi:** Nhấn mạnh sự cần thiết của **Đặc quyền Tối thiểu (Least Privilege)**, **Zero Trust** (không bao giờ tin tưởng, luôn xác minh), và **Phòng thủ Chiều sâu (Defense in Depth)** (phòng thủ nhiều lớp).

* **Mô hình Trách nhiệm Chia sẻ:** Làm rõ ranh giới trách nhiệm: AWS chịu trách nhiệm về bảo mật **của Đám mây** (cơ sở hạ tầng, vật lý), trong khi Khách hàng chịu trách nhiệm về bảo mật **trong Đám mây** (dữ liệu, IAM, cấu hình).

### 2. Trụ cột 1: Quản lý Danh tính & Truy cập (IAM)

* **Kiến trúc Hiện đại:** Tránh sử dụng **thông tin xác thực dài hạn** (Khóa Truy cập có thời hạn dài) cho người dùng. Ưu tiên **Vai trò (Roles)** cho các dịch vụ và **IAM Identity Center** (SSO) cho người dùng.

* **Kiểm soát Đa Tài khoản:** Áp dụng **Chính sách Kiểm soát Dịch vụ (SCPs)** ở cấp AWS Organizations và **Ranh giới Quyền hạn (Permission Boundaries)** để đặt giới hạn tối đa cho các quyền được ủy thác.

* **Demo Nhỏ:** Trình diễn việc sử dụng **Access Analyzer** và công cụ mô phỏng chính sách để xác minh và xác thực quyền truy cập trước khi triển khai.

### 3. Trụ cột 2: Phát hiện

* **Giám sát Liên tục:** Sử dụng **CloudTrail** (ở cấp Tổ chức) để ghi lại tất cả các hành động API, **GuardDuty** để phát hiện các mối đe dọa bất thường được hỗ trợ bởi ML, và **Security Hub** để tổng hợp các phát hiện.

* **Phát hiện-dưới-dạng-Mã (Detection-as-Code):** Định nghĩa các quy tắc phát hiện dưới dạng mã (ví dụ: Lambda, CloudFormation) để tự động hóa việc triển khai và quản lý.

### 4. Trụ cột 3: Bảo vệ Cơ sở hạ tầng

* **Phân đoạn Mạng:** Tách các tầng ứng dụng (Web, Ứng dụng, DB) bằng cách sử dụng **phân đoạn VPC**. Phân biệt rõ ràng vai trò của **Nhóm Bảo mật (Security Groups)** (có trạng thái) và **NACLs** (phi trạng thái).

* **Phòng thủ Vòng ngoài:** Triển khai **WAF** (Tường lửa Ứng dụng Web) và **Shield** để bảo vệ ứng dụng khỏi tấn công DDoS và Tầng 7.

### 5. Trụ cột 4: Bảo vệ Dữ liệu

* **Mã hóa:** Đảm bảo dữ liệu được mã hóa cả **lúc nghỉ** (được lưu trữ trong S3, EBS, RDS) và **khi truyền tải** (được truyền qua TLS/SSL).

* **Quản lý Khóa và Bí mật:** Sử dụng **KMS (Key Management Service)** để quản lý các khóa mã hóa chính, kiểm soát các chính sách khóa và xoay vòng khóa. Sử dụng **Secrets Manager** để lưu trữ và tự động **xoay vòng** các bí mật (mật khẩu cơ sở dữ liệu, khóa API).

### 6. Trụ cột 5: Ứng phó Sự cố

* **Vòng đời IR:** Hướng dẫn tuân thủ vòng đời tiêu chuẩn của AWS (Chuẩn bị, Phát hiện, Ứng phó, Phục hồi).

* **Tự động hóa Ứng phó:** Phát triển **Sách hướng dẫn tự động (Playbooks)** bằng cách sử dụng **Lambda hoặc Step Functions** cho các sự cố phổ biến như khóa IAM bị xâm phạm hoặc phát hiện phần mềm độc hại trên EC2. Các bước chính bao gồm **Chụp nhanh (Snapshot), cô lập và thu thập bằng chứng**.
