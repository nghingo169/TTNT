---
title: "Week 7 Worklog"
date: 2026-07-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
includeInReport: true
reportTableColumns:
  - Day
  - Task
  - Completion Date
reportHeadings:
  - Week 7 Objectives
  - Tasks to be carried out this week
  - Week 7 Achievements
reportType: worklog
---

### Week 7 Objectives:

* Migrate backend from **ChromaDB** to **S3 Vectors** to reduce storage costs and improve scalability.
* Continue deploying and testing FastAPI on EC2 with the new S3 Vectors backend.
* Ensure service stability and response time after the migration.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | - Read **STEP 5 – Online Backend With S3 Vectors** documentation | 07/12/2026 | 07/12/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 2 | - Set up environment variables for S3 Vectors (`S3_VECTOR_BUCKET=rag-vectors-vanh1234`, `S3_VECTOR_INDEX=hotpotqa-val100-bge-m3-v001`) | 07/13/2026 | 07/13/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 3 | - Run `backend/scripts/check_online_artifacts.py --artifact-layout s3vectors` to verify vector download success | 07/14/2026 | 07/14/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 4 | - Update `backend/advanced_rag/pipeline.py` to call `load_online_artifacts(layout="s3vectors")` and test query | 07/15/2026 | 07/15/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 5 | - Redeploy FastAPI on EC2 (systemd) with new configuration <br> - Test `/query` endpoint and measure response time (< 8 seconds) | 07/16/2026 | 07/16/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |
| 6 | - Document issues encountered (vector format, permissions, latency) and their resolutions | 07/17/2026 | 07/17/2026 | aws-rag-project/docs/STEP_5_S3_VECTORS_ONLINE.md |

### Week 7 Achievements:

* Backend fully migrated to S3 Vectors; no longer loading the full ChromaDB index.
* Vector backend load time reduced ~ 30 % compared to dense version; query time < 8 seconds.
* FastAPI on EC2 running stably with S3 Vectors backend, meeting demo query requirements.
* Permission and latency issues were identified and documented for future reference.
