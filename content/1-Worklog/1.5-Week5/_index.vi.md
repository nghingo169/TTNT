---
title: "Worklog Tuần 5"
date: 2026-07-08
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
reportType: worklog
---

### Tuần 5 Mục tiêu:

* Bắt đầu triển khai phần core của dự án RAG **aws‑rag‑project**.
* Xây dựng corpus mẫu (HotpotQA – 100 validation rows) và tải lên S3.
* Tạo **offline artifact bundle** (ChromaDB, BM25, manifest) cho index `index-demo-small-v001` và đưa lên S3 theo layout chuẩn.

### Các công việc trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | ------------ | --------------- | ------------------- |
| 1 | Chạy notebook `backend/notebooks/build_s3_offline_artifacts.ipynb` để tạo corpus và xuất `corpus.jsonl`, `eval.jsonl`, `corpus_manifest.json` | 07/01/2026 | 07/01/2026 | aws-rag-project/docs/STEP_1_BUILD_CORPUS_S3.md |
| 2 | Upload các file corpus lên bucket S3 `s3://aws-rag-bucket-vanh1234/rag/corpora/hotpotqa/validation-100/v001/` bằng `aws s3 cp` | 07/02/2026 | 07/02/2026 | aws-rag-project/docs/STEP_1_BUILD_CORPUS_S3.md |
| 3 | Chạy script `backend/scripts/build_offline_artifacts.py` với tham số `--index-id index-demo-small-v001` để tạo offline artifact bundle | 07/03/2026 | 07/03/2026 | aws-rag-project/docs/STEP_2_OFFLINE_ARTIFACTS.md |
| 4 | Kiểm tra các prefix S3 (`processed/`, `vector-db/chroma/`, `bm25/`, `manifests/`) chứa artefact đã upload | 07/04/2026 | 07/04/2026 | aws-rag-project/docs/STEP_2_OFFLINE_ARTIFACTS.md |
| 5 | Ghi lại các vấn đề gặp phải (quota SageMaker, model `BAAI/bge-m3` bị kill, dependency thiếu) và cách khắc phục bằng model nhẹ `BAAI/bge-small-en-v1.5` | 07/05/2026 | 07/05/2026 | aws-rag-project/docs/STEP_2_OFFLINE_ARTIFACTS.md |

### Thành tựu tuần 5:

* Corpus HotpotQA (100 rows) được tạo và lưu trữ thành công trên S3.
* Offline artifact bundle `index-demo-small-v001` được tạo, bao gồm ChromaDB, BM25 và manifest, và đã được tải lên S3 theo layout chuẩn.
* Toàn bộ artefact được xác thực tồn tại trên S3 và sẵn sàng cho pipeline online.
* Các lỗi liên quan tới quota và model đã được ghi nhận và giải quyết bằng việc chuyển sang model nhẹ.
