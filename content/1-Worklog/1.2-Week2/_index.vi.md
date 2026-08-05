---
title: "Worklog Tuần 2"
date: 2026-06-17
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
reportType: worklog
---

### Tuần 2 Mục tiêu:

* Khám phá sâu hơn các dịch vụ lưu trữ trên AWS: Amazon S3 nâng cao, EBS và AWS Backup.
* Thực hành quản lý bucket policies, versioning, Server‑Side Encryption và lifecycle rules.
* Tạo, gắn và snapshot một EBS volume, sau đó thực hiện restore trên EC2.

### Các công việc trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------- |
| 1 | - Đọc tài liệu S3 Advanced, tạo bucket S3 với versioning và Server‑Side Encryption (SSE‑AES) | 06/12/2026 | 06/12/2026 | https://cloudjourney.awsstudygroup.com/ |
| 2 | - Thiết lập Lifecycle Policy để tự động chuyển objects sang S3 Glacier sau 30 ngày | 06/13/2026 | 06/13/2026 | https://cloudjourney.awsstudygroup.com/ |
| 3 | - Tạo EC2 instance (t3.micro), tạo EBS gp3 volume, attach vào instance và tạo snapshot | 06/14/2026 | 06/14/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Thực hiện restore snapshot thành một volume mới và mount lên EC2 để kiểm tra dữ liệu | 06/15/2026 | 06/15/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Sử dụng AWS Backup để tạo backup plan cho EBS volume và kiểm tra restore qua Backup service | 06/16/2026 | 06/16/2026 | https://cloudjourney.awsstudygroup.com/ |

### Thành tựu tuần 2:

* Bucket S3 được cấu hình versioning, SSE‑AES và lifecycle policy thành công.
* EBS gp3 volume được tạo, snapshot và restore thành công trên EC2.
* Backup plan cho EBS đã được thiết lập và kiểm tra qua AWS Backup.
* Nắm vững các tính năng lưu trữ nâng cao và best practice bảo mật dữ liệu trên AWS.
