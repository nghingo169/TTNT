
---

## WEEK 7 WORKLOG (27/07/2026 - 07/08/2026)

---

title: "Week 7 Worklog"
date: 2026-08-07
weight: 7
chapter: false
pre: "  1.7.  "
includeInReport: true
reportTableColumns:

* Day
* Task
* Completion Date
reportHeadings:
* Week 7 Objectives
* Tasks to be carried out this week
* Week 7 Achievements
reportType: worklog

---

### Week 7 Objectives:

* Build automated CI/CD pipelines and orchestration using Databricks Asset Bundles.


* Implement Observability & Monitoring telemetry views (`src/data_contracts/monitoring/views.py`).


* Refine the high-fidelity Figma Prototype for the **Financial Wellbeing Assistant** for final showcase integration.



### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - Configure GitHub Actions workflow (`.github/workflows/ci-cd.yml`) with automated linting, security scanning, and unit testing.

 | 27/07/2026 | 29/07/2026 | `.github/workflows/`<br> |
| 2 | - Configure Databricks Asset Bundles orchestration (`databricks.yml`, `resources/banking_investigation.job.yml`). | 30/07/2026 | 01/08/2026 | Databricks Workflows |
| 3 | - Develop pipeline execution logging and monitoring scripts (`src/pipeline/monitoring/finalize_pipeline_run.py`).

 | 02/08/2026 | 04/08/2026 | `src/pipeline/monitoring/`<br> |
| 4 | - Finalize High-Fidelity Figma Prototype and update Confluence Sprint Artefacts.

 | 05/08/2026 | 06/08/2026 | Figma / Confluence

 |
| 5 | - Run integration test suites (`resources/run_integration_tests.yml`) and deploy pipeline to staging environment.

 | 07/08/2026 | 07/08/2026 | Integration Pipeline

 |

### Week 7 Achievements:

* Automated end-to-end CI/CD with strict gating (code cannot be merged without passing linting, SAST scanning, and tests).


* Enabled deep observability and execution telemetry tracking pipeline metrics and health.


* Completed high-fidelity Figma Prototype bridging Product Mindset ideation with Data Pipeline feasibility.


* Successfully deployed the Zero-Trust Banking Pipeline stack to non-production environment.
