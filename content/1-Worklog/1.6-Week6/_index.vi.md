---
title: "Worklog Tuần 6"
date: 2026-07-15
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
reportType: worklog
---

### Tuần 6 Mục tiêu:

* Triển khai pipeline **online** trên môi trường SageMaker và EC2, tải artefact đã tạo mà không thực hiện lại quá trình chunking hoặc embedding.
* Kiểm thử truy vấn mẫu và đo thời gian đáp ứng.
* Chuẩn bị môi trường EC2 cho việc chạy FastAPI service.

### Các công việc trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------- |
| 1 | Đọc tài liệu **STEP 4 – Online Pipeline Load Existing Artifacts** | 07/06/2026 | 07/06/2026 | aws-rag-project/docs/STEP_4_ONLINE_LOAD_ARTIFACTS.md |
| 2 | Chạy script `backend/scripts/check_online_artifacts.py` để xác nhận artefact được tải về thành công trong môi trường SageMaker | 07/07/2026 | 07/07/2026 | aws-rag-project/docs/STEP_4_ONLINE_LOAD_ARTIFACTS.md |
| 3 | Thực hiện truy vấn mẫu bằng `backend/tools/query.py --index-id index-demo-small-v001` và ghi lại thời gian tải artefact + query (< 5 giây) | 07/08/2026 | 07/08/2026 | aws-rag-project/docs/STEP_4_ONLINE_LOAD_ARTIFACTS.md |
| 4 | Tạo EC2 instance (Ubuntu) và gắn IAM role cho phép truy cập S3, SSM và Secrets Manager | 07/09/2026 | 07/09/2026 | aws-rag-project/docs/STEP_6_EC2_FASTAPI_DEPLOYMENT.md |
| 5 | Clone repo `aws-rag-project` lên EC2, cài đặt dependencies, tạo file `.env.prod` với các biến môi trường (`RAG_INDEX_ID`, `S3_ARTIFACT_BUCKET`, …) | 07/10/2026 | 07/10/2026 | aws-rag-project/docs/STEP_6_EC2_FASTAPI_DEPLOYMENT.md |
| 6 | Deploy FastAPI bằng systemd (`aws-rag-api.service`), khởi động service và kiểm thử endpoint `/health` và `/query` từ máy cục bộ | 07/11/2026 | 07/11/2026 | aws-rag-project/docs/STEP_6_EC2_FASTAPI_DEPLOYMENT.md |

### Thành tựu tuần 6:

* Pipeline online trên SageMaker tải artefact thành công, bỏ qua bước chunking/embedding và giảm thời gian khởi động.
* Truy vấn mẫu trả về kết quả trong vòng < 5 giây, chứng minh hiệu năng của artefact đã preload.
* EC2 instance được chuẩn bị, IAM role có đủ quyền, FastAPI service chạy dưới systemd và trả về kết quả hợp lệ qua endpoint `/query`.
* Các biến môi trường cần thiết đã được cấu hình, sẵn sàng cho các bước tiếp theo.
