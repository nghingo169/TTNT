---
title: "Week 8 Worklog"
date: 2026-07-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
includeInReport: true
reportTableColumns:
  - Day
  - Task
  - Completion Date
reportHeadings:
  - Week 8 Objectives
  - Tasks to be carried out this week
  - Week 8 Achievements
reportType: worklog
---

### Week 8 Objectives:

* Deploy **frontend** using **AWS Amplify** and configure **API Gateway** as an HTTPS proxy for the EC2 backend.
* Implement **warm-up** endpoint and **fast mode** to reduce initial latency.
* Centralize configuration using **SSM Parameter Store** and **Secrets Manager**.
* Assign **Elastic IP** to EC2, enable **Session Manager** for administration without opening public SSH.
* Finalize end-of-internship documentation and prepare demo for FCAJ.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | - Read **STEP 7 – Amplify Frontend & API Gateway HTTPS Proxy** documentation | 07/18/2026 | 07/18/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 2 | - Deploy React frontend via Amplify Hosting (branch `full_structure`) <br> - Obtain HTTPS URL | 07/19/2026 | 07/19/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 3 | - Create API Gateway HTTP API <br> - Configure integration to EC2 endpoint (`http://<ElasticIP>:8000`) for `/health` and `/query` | 07/20/2026 | 07/20/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 4 | - Configure CORS on API Gateway and FastAPI to allow Amplify origin | 07/21/2026 | 07/21/2026 | aws-rag-project/docs/STEP_7_AMPLIFY_API_GATEWAY_DEPLOYMENT.md |
| 5 | - Add `POST /warmup` endpoint to FastAPI (code in `backend/app/main.py`) <br> - Update systemd `ExecStartPost` to auto-warmup after restart | 07/22/2026 | 07/22/2026 | aws-rag-project/docs/STEP_8_WARMUP_FAST_MODE.md |
| 6 | - Enable `RAG_FAST_MODE=true` <br> - Reduce `TOP_K` parameters to lower query time (update `backend/advanced_rag/config.py`) | 07/23/2026 | 07/23/2026 | aws-rag-project/docs/STEP_8_WARMUP_FAST_MODE.md |
| 7 | - Read **STEP 9 – Centralized Config with SSM & Secrets Manager** documentation <br> - Create SSM parameters (`/prod/aws-rag/*`) and secret for `GROQ_API_KEY` | 07/24/2026 | 07/24/2026 | aws-rag-project/docs/STEP_9_CENTRALIZED_CONFIG.md |
| 8 | - Update `.env.prod` to contain only `APP_ENV=prod`, `CONFIG_PREFIX=/prod/aws-rag`, `GROQ_SECRET_NAME=/prod/aws-rag/groq-api-key` | 07/25/2026 | 07/25/2026 | aws-rag-project/docs/STEP_9_CENTRALIZED_CONFIG.md |
| 9 | - Assign **Elastic IP** (54.x.x.x) to EC2 <br> - Update API Gateway integration URL <br> - Verify `/health` and `/query` via HTTPS | 07/26/2026 | 07/26/2026 | aws-rag-project/docs/STEP_10_ELASTIC_IP_SESSION_MANAGER.md |
| 10 | - Enable **Session Manager** on EC2 (install SSM agent, attach `AmazonSSMManagedInstanceCore` policy) <br> - Test access via AWS Console | 07/27/2026 | 07/27/2026 | aws-rag-project/docs/STEP_10_ELASTIC_IP_SESSION_MANAGER.md |
| 11 | - Write final documentation (architecture diagram, deployment guide, run-books) <br> - Update worklog links in README | 07/28/2026 | 07/28/2026 | internal documentation |
| 12 | - Conduct final demo for FCAJ: query demo via Amplify UI, measure latency, present architecture and deployment steps | 07/30/2026 | 07/31/2026 | internal demo plan |

### Week 8 Achievements:

* React frontend deployed on Amplify with HTTPS URL; successfully calling API Gateway.
* API Gateway functioning as HTTPS proxy for EC2 FastAPI; CORS configured correctly.
* `/warmup` endpoint and `RAG_FAST_MODE` reduced initial latency to < 2 seconds.
* Configuration centralized in SSM Parameter Store and Secrets Manager; `.env.prod` minimised.
* Elastic IP assigned to EC2; API Gateway consistently pointing to the correct address; Session Manager enabled for administration without public SSH.
* End-of-internship documentation completed; final demo delivered successfully with positive feedback from FCAJ mentorship.
