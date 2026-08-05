---
title: "Worklog Tuần 7"
date: 2026-07-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
reportType: worklog
---

### Tuần 7 Mục tiêu:

* Chuyển backend từ **ChromaDB** sang **S3 Vectors** để giảm chi phí lưu trữ và tăng khả năng mở rộng.
* Tiếp tục triển khai và kiểm thử FastAPI trên EC2 với backend S3 Vectors.
* Đảm bảo độ ổn định và thời gian phản hồi của service sau khi chuyển đổi.

### Các công việc trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------- |
| 1 | Đọc tài liệu **STEP 5 – Online Backend With S3 Vectors** | 07/12/2026 | 07/12/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 2 | Thiết lập các biến môi trường cho S3 Vectors (`S3_VECTOR_BUCKET=rag-vectors-vanh1234`, `S3_VECTOR_INDEX=hotpotqa-val100-bge-m3-v001`) | 07/13/2026 | 07/13/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 3 | Chạy `backend/scripts/check_online_artifacts.py --artifact-layout s3vectors` để xác nhận download thành công của vector backend | 07/14/2026 | 07/14/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 4 | Cập nhật `backend/advanced_rag/pipeline.py` để gọi `load_online_artifacts(layout="s3vectors")` và chạy thử query | 07/15/2026 | 07/15/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 5 | Deploy lại FastAPI trên EC2 (systemd) với cấu hình mới, kiểm thử endpoint `/query` và đo thời gian phản hồi (< 8 giây) | 07/16/2026 | 07/16/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 6 | Ghi lại các vấn đề gặp phải (định dạng vector, permissions, latency) và cách khắc phục | 07/17/2026 | 07/17/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |

### Thành tựu tuần 7:

* Backend đã chuyển hoàn toàn sang S3 Vectors, không còn tải toàn bộ ChromaDB.
* Thời gian tải vector backend giảm ~ 30 % so với phiên bản dense, thời gian query < 8 giây.
* FastAPI trên EC2 hoạt động ổn định với backend S3 Vectors, đáp ứng yêu cầu truy vấn demo.
* Các vấn đề về permissions và latency đã được ghi nhận và giải quyết (cập nhật IAM policy, tăng timeout).
