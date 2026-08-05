---
title: "Self-Assessment"
date: 2026-07-30
weight: 6
chapter: false
pre: " <b> 6. </b> "
includeInReport: false
---

During my internship at **First Cloud AI Journey (FCAJ) program** from **10/06/2026** to **30/07/2026**, I had the opportunity to learn, practice, and apply the knowledge acquired in school to a real-world working environment.  
I participated in **the aws-rag-project** — building and deploying a Retrieval-Augmented Generation (RAG) pipeline for multi-hop reasoning on the HotpotQA dataset, from offline indexing to a fully deployed cloud service on AWS. Through this project, I improved my skills in **Python/FastAPI development, LangChain and RAG techniques, AWS cloud services (EC2, S3, API Gateway, Amplify, SSM, Secrets Manager, IAM, CloudWatch), frontend development with React, and technical documentation**.

In terms of work ethic, I always strived to complete tasks well, complied with workplace regulations, and actively engaged with colleagues to improve work efficiency.

To objectively reflect on my internship period, I would like to evaluate myself based on the following criteria:

| No. | Criteria                            | Description                                                                                      | Good | Fair | Average |
| --- | ----------------------------------- | ------------------------------------------------------------------------------------------------ | ---- | ---- | ------- |
| 1   | **Professional knowledge & skills** | Understanding of the field, applying knowledge in practice, proficiency with tools, work quality | ✅    | ☐    | ☐       |
| 2   | **Ability to learn**                | Ability to absorb new knowledge and learn quickly                                                | ✅    | ☐    | ☐       |
| 3   | **Proactiveness**                   | Taking initiative, seeking out tasks without waiting for instructions                            | ✅    | ☐    | ☐       |
| 4   | **Sense of responsibility**         | Completing tasks on time and ensuring quality                                                    | ✅    | ☐    | ☐       |
| 5   | **Discipline**                      | Adhering to schedules, rules, and work processes                                                 | ☐    | ✅    | ☐       |
| 6   | **Progressive mindset**             | Willingness to receive feedback and improve oneself                                              | ✅    | ☐    | ☐       |
| 7   | **Communication**                   | Presenting ideas and reporting work clearly                                                      | ☐    | ✅    | ☐       |
| 8   | **Teamwork**                        | Working effectively with colleagues and participating in teams                                   | ✅    | ☐    | ☐       |
| 9   | **Professional conduct**            | Respecting colleagues, partners, and the work environment                                        | ✅    | ☐    | ☐       |
| 10  | **Problem-solving skills**          | Identifying problems, proposing solutions, and showing creativity                                | ✅    | ☐    | ☐       |
| 11  | **Contribution to project/team**    | Work effectiveness, innovative ideas, recognition from the team                                  | ✅    | ☐    | ☐       |
| 12  | **Overall**                         | General evaluation of the entire internship period                                               | ✅    | ☐    | ☐       |

### Summary of Achievements

* Completed a full end-to-end RAG pipeline: offline indexing (BM25 + dense embeddings with BAAI/bge-m3), hybrid retrieval via Reciprocal Rank Fusion, cross-encoder reranking, and LLM-driven adaptive query decomposition and hop planning.
* Deployed the service on AWS: FastAPI backend on EC2 behind API Gateway, React frontend on Amplify, centralized configuration with SSM Parameter Store and Secrets Manager, Elastic IP and Session Manager for secure administration.
* Resolved real latency challenges by implementing a `/warmup` endpoint and `RAG_FAST_MODE`, reducing initial query latency to under 2 seconds within API Gateway's timeout constraints.
* Delivered a successful final demo to the FCAJ mentorship team with positive feedback.

### Needs Improvement

* Strengthen communication skills to present ideas and technical reports even more clearly and concisely, especially when explaining complex cloud architectures to non-technical audiences.
* Deepen understanding of cloud cost optimization beyond the AWS Free Tier, since the current deployment is intentionally scoped to a low-cost demo.
* Improve time estimation for development tasks, as some deployment and debugging steps (e.g., API Gateway integration, CORS configuration) took longer than initially planned.
* Continue improving problem-solving independence — while I could identify and resolve issues, I sometimes relied on mentor guidance earlier than necessary.
