---
title: "Worklog Tuần 4"
date: 2026-07-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
reportType: worklog
---

### Tuần 4 Mục tiêu:

* Tìm hiểu các dịch vụ bảo mật và quản lý danh tính trên AWS: IAM, KMS, CloudTrail và GuardDuty.
* Thực hành tạo IAM Users, Groups, Roles và áp dụng Least‑Privilege Policy.
* Thiết lập CloudTrail để ghi lại hoạt động tài khoản và bật GuardDuty cho phát hiện threat.

### Các công việc trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | ------------ | --------------- | ------------------- |
| 1 | Đọc tài liệu IAM fundamentals, tạo IAM User, gán Policy "ReadOnlyAccess" | 06/23/2026 | 06/23/2026 | https://cloudjourney.awsstudygroup.com/ |
| 2 | Tạo IAM Role cho EC2 với quyền S3 read/write và SSM GetParameters | 06/24/2026 | 06/24/2026 | https://cloudjourney.awsstudygroup.com/ |
| 3 | Thực hành tạo Customer Managed Key (CMK) bằng AWS KMS, encrypt một S3 object | 06/25/2026 | 06/25/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | Kích hoạt CloudTrail cho toàn bộ region, kiểm tra log trong S3 bucket | 06/26/2026 | 06/26/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | Bật GuardDuty, xem mẫu findings và ghi chú các bước phản hồi | 06/27/2026 | 06/27/2026 | https://cloudjourney.awsstudygroup.com/ |

### Thành tựu tuần 4:

* IAM Users, Groups và Roles được tạo, áp dụng chính sách principle of least privilege.
* Customer Managed Key (CMK) tạo thành công, dữ liệu S3 được encrypt và giải mã.
* CloudTrail ghi lại tất cả các hành động API và lưu vào bucket dự phòng.
* GuardDuty được bật, phát hiện một số sample findings và thực hành các bước remediation.
