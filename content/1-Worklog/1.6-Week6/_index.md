---
title: "Week 6 Worklog"
date: 2026-07-15
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
includeInReport: true
reportTableColumns:
  - Day
  - Task
  - Completion Date
reportHeadings:
  - Week 6 Objectives
  - Tasks to be carried out this week
  - Week 6 Achievements
reportType: worklog
---

### Week 6 Objectives:

* Deploy online pipeline on SageMaker and EC2, loading pre-built artifacts without re-running chunking or embedding.
* Run sample queries and measure response times.
* Prepare EC2 environment for running FastAPI service.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | - Read **STEP 4 – Online Pipeline Load Existing Artifacts** documentation | 07/06/2026 | 07/06/2026 | aws-rag-project/docs/STEP_4_ONLINE_LOAD_ARTIFACTS.md |
| 2 | - Run script `backend/scripts/check_online_artifacts.py` to verify artifacts are loaded successfully in SageMaker environment | 07/07/2026 | 07/07/2026 | aws-rag-project/docs/STEP_4_ONLINE_LOAD_ARTIFACTS.md |
| 3 | - Execute sample query via `backend/tools/query.py --index-id index-demo-small-v001` <br> - Record artifact load time + query time (< 5 seconds) | 07/08/2026 | 07/08/2026 | aws-rag-project/docs/STEP_4_ONLINE_LOAD_ARTIFACTS.md |
| 4 | - Create EC2 instance (Ubuntu) <br> - Attach IAM role for S3, SSM and Secrets Manager access | 07/09/2026 | 07/09/2026 | aws-rag-project/docs/STEP_6_EC2_FASTAPI_DEPLOYMENT.md |
| 5 | - Clone `aws-rag-project` repo onto EC2 <br> - Install dependencies <br> - Create `.env.prod` with environment variables (`RAG_INDEX_ID`, `S3_ARTIFACT_BUCKET`, …) | 07/10/2026 | 07/10/2026 | aws-rag-project/docs/STEP_6_EC2_FASTAPI_DEPLOYMENT.md |
| 6 | - Deploy FastAPI via systemd (`aws-rag-api.service`) <br> - Start service and test `/health` and `/query` endpoints locally | 07/11/2026 | 07/11/2026 | aws-rag-project/docs/STEP_6_EC2_FASTAPI_DEPLOYMENT.md |

### Week 6 Achievements:

* Online pipeline on SageMaker loaded artifacts successfully, skipping chunking/embedding step and reducing startup time.
* Sample query returned results within < 5 seconds, proving pre-loaded artifact performance.
* EC2 instance provisioned with proper IAM role; FastAPI service running under systemd and returning valid responses via `/query` endpoint.
* All necessary environment variables configured, ready for the next steps.
