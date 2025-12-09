---
title: "Blog 2"

weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Phần này sẽ liệt kê và giới thiệu bài blog mà tôi đã dịch.

### Blog 2 - Mới ra mắt – AWS Systems Manager dành cho Quản lý Cấu hình SAP: Tự động xác thực các Thực tiễn Tốt nhất cho SAP HANA.
Blog này thông báo về sự ra mắt của AWS Systems Manager for SAP Configuration Management, một tính năng mới cho phép tự động xác thực cấu hình cơ sở dữ liệu SAP HANA dựa trên các thực tiễn tốt nhất của AWS (dựa trên SAP Lens of AWS Well-Architected Framework). Tính năng này giúp các quản trị viên SAP phát hiện lỗi cấu hình tiềm ẩn và đảm bảo hiệu năng, bảo mật, và độ tin cậy tối ưu cho khối lượng công việc SAP HANA chạy trên AWS.

Tính năng Configuration Checks ban đầu tập trung vào ba hạng mục kiểm tra chính:

SAP EC2 Instance Type Selection: Xác minh loại instance EC2 có được chứng nhận cho SAP hay không.

SAP HANA EBS Storage Configuration: Kiểm tra cấu hình lưu trữ Amazon EBS và hệ thống tệp.

SAP HANA Pacemaker Configuration: Kiểm tra cấu hình cụm Pacemaker cho các thiết lập High Availability (HA).

Mỗi kiểm tra trả về trạng thái chi tiết (OKAY, ERROR, WARNING, INFO hoặc UNKNOWN) và cung cấp hướng dẫn khắc phục kèm theo tài liệu kỹ thuật liên quan. Tính năng này hỗ trợ chạy kiểm tra thủ công qua AWS Console hoặc tự động hóa định kỳ thông qua lệnh API đơn giản, đồng thời cho phép theo dõi lịch sử cấu hình trong 30 ngày. Dịch vụ này được định giá theo mô hình trả tiền theo mức sử dụng ($0,25 USD cho mỗi lần chạy kiểm tra cấu hình trên mỗi ứng dụng).
[Đọc toàn bộ bài dịch trên Google Docs](https://docs.google.com/document/d/1OfummNzAJUQRtHSIqkvKrEJZxHHWL2dXaQxlFypCqr0/edit?usp=sharing)