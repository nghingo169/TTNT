---
title: "Worklog Tuần 3"
date: 2026-06-24
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
reportType: worklog
---

### Tuần 3 Mục tiêu:

* Tìm hiểu về networking trên AWS: VPC, Subnet, Route Table, Internet Gateway, NAT Gateway, Security Group và Network ACL.
* Thực hành xây dựng một VPC hai tầng (public/private subnets) với NAT Gateway để EC2 private có thể ra internet.
* Kết nối VPC với S3 thông qua VPC Endpoint (Gateway).

### Các công việc trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------- |
| 1 | - Thiết kế VPC 2-tier: public subnet (Load Balancer, Bastion Host) và private subnet (Application, Database) | 06/19/2026 | 06/19/2026 | https://cloudjourney.awsstudygroup.com/ |
| 2 | - Tạo VPC, public subnet (10.0.1.0/24), private subnet (10.0.2.0/24), Internet Gateway, NAT Gateway và Route Tables | 06/20/2026 | 06/20/2026 | https://cloudjourney.awsstudygroup.com/ |
| 3 | - Launch EC2 instance trong private subnet, cấu hình Security Group để chỉ cho phép traffic từ Bastion Host | 06/21/2026 | 06/21/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Tạo VPC Endpoint (Gateway) cho S3, gán policy để EC2 private truy cập S3 mà không qua internet | 06/22/2026 | 06/22/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Kiểm tra kết nối: dùng Bastion Host SSH vào EC2 private, verify S3 access và internet access qua NAT Gateway | 06/23/2026 | 06/23/2026 | https://cloudjourney.awsstudygroup.com/ |

### Thành tựu tuần 3:

* VPC 2‑tier được thiết kế và triển khai thành công với public/private subnet, IGW, NAT Gateway, route tables.
* EC2 instance trong private subnet có thể ra internet (qua NAT) và truy cập S3 (qua VPC Endpoint) theo đúng yêu cầu.
* Hiểu rõ cách Security Group và Network ACL hoạt động ở mỗi tầng.
* Có khả năng triển khai hạ tầng mạng cơ bản cho một ứng dụng web an toàn trên AWS.
