---
title: "Worklog Tuần 8"
date: 2026-07-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
reportType: worklog
---

### Tuần 8 Mục tiêu:

* Triển khai **frontend** bằng **AWS Amplify** và cấu hình **API Gateway** làm HTTPS proxy cho backend EC2.
* Thực hiện **warm‑up** endpoint và **fast mode** để giảm latency lần đầu.
* Centralize cấu hình bằng **SSM Parameter Store** và **Secrets Manager**.
* Gán **Elastic IP** cho EC2, bật **Session Manager** để quản trị không cần SSH mở công khai.
* Hoàn thiện tài liệu cuối kỳ và chuẩn bị buổi demo cho FCAJ.

### Các công việc trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------- |
| 1 | Đọc tài liệu **STEP 7 – Amplify Frontend & API Gateway HTTPS Proxy** | 07/18/2026 | 07/18/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 2 | Deploy React frontend bằng Amplify Hosting (branch `full_structure`), lấy URL HTTPS | 07/19/2026 | 07/19/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 3 | Tạo API Gateway HTTP API, cấu hình integration tới EC2 endpoint (`http://<ElasticIP>:8000`) cho `/health` và `/query` | 07/20/2026 | 07/20/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 4 | Cấu hình CORS trên API Gateway và FastAPI để cho phép origin Amplify | 07/21/2026 | 07/21/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 5 | Thêm endpoint `POST /warmup` vào FastAPI (code trong `backend/app/main.py`) và cập nhật systemd `ExecStartPost` để tự động warmup sau restart | 07/22/2026 | 07/22/2026 | aws-rag-project/docs/STEP_8_WARMUP_FAST_MODE.md |
| 6 | Bật `RAG_FAST_MODE=true` và giảm các tham số `TOP_K` để giảm thời gian truy vấn (cập nhật `backend/advanced_rag/config.py`) | 07/23/2026 | 07/23/2026 | aws-rag-project/docs/STEP_8_WARMUP_FAST_MODE.md |
| 7 | Đọc tài liệu **STEP 9 – Centralized Config with SSM & Secrets Manager** và tạo các tham số SSM (`/prod/aws-rag/*`) và secret cho `GROQ_API_KEY` | 07/24/2026 | 07/24/2026 | aws-rag-project/docs/STEP_9_CENTRALIZED_CONFIG.md |
| 8 | Cập nhật `.env.prod` để chỉ chứa `APP_ENV=prod`, `CONFIG_PREFIX=/prod/aws-rag`, `GROQ_SECRET_NAME=/prod/aws-rag/groq-api-key` | 07/25/2026 | 07/25/2026 | aws-rag-project/docs/STEP_9_CENTRALIZED_CONFIG.md |
| 9 | Gán **Elastic IP** (54.x.x.x) cho EC2, cập nhật API Gateway integration URL, kiểm tra lại `/health` và `/query` qua HTTPS | 07/26/2026 | 07/26/2026 | aws-rag-project/docs/STEP_10_ELASTIC_IP_SESSION_MANAGER.md |
|10 | Kích hoạt **Session Manager** trên EC2 (cài đặt SSM agent, attach `AmazonSSMManagedInstanceCore` policy) và kiểm tra truy cập qua AWS Console | 07/27/2026 | 07/27/2026 | aws-rag-project/docs/STEP_10_ELASTIC_IP_SESSION_MANAGER.md |
|11 | Viết tài liệu cuối kỳ (architecture diagram, deployment guide, run‑books) và cập nhật liên kết worklog trong README | 07/28/2026 | 07/28/2026 | internal documentation |
|12 | Thực hiện buổi demo cuối tuần cho FCAJ: truy vấn demo qua Amplify UI, đo latency, trình bày kiến trúc và các bước triển khai | 07/30/2026 | 07/31/2026 | internal demo plan |

### Thành tựu tuần 8:

* Frontend React được triển khai trên Amplify với URL HTTPS và gọi API Gateway thành công.
* API Gateway hoạt động như HTTPS proxy cho EC2 FastAPI; CORS được cấu hình chính xác.
* Endpoint `/warmup` và `RAG_FAST_MODE` giảm latency lần đầu xuống < 2 giây.
* Cấu hình đã được centralize vào SSM Parameter Store và Secrets Manager; `.env.prod` được giảm kích thước.
* Elastic IP gán cho EC2, API Gateway luôn trỏ đúng địa chỉ; Session Manager cho phép quản trị không cần mở SSH công khai.
* Tài liệu cuối kỳ hoàn thiện, buổi demo được thực hiện thành công, nhận được phản hồi tích cực từ mentorship FCAJ.
