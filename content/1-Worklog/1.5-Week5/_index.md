



---

## WEEK 5 WORKLOG (13/07/2026 - 17/07/2026)

---

title: "Week 5 Worklog"
date: 2026-07-17
weight: 5
chapter: false
pre: "  1.5.  "
includeInReport: true
reportTableColumns:

* Day
* Task
* Completion Date
reportHeadings:
* Week 5 Objectives
* Tasks to be carried out this week
* Week 5 Achievements
reportType: worklog

---

### Week 5 Objectives:

* Implement **Zero-Trust Data Governance**: Attribute-Based Access Control (ABAC), Dynamic PII Masking, and Role Management.


* Develop SQL Identity Resolution and Customer 360 Candidate Views (`sql/customer_360/`).
* Verify PII tagging and masking policies across Databricks Unity Catalog.



### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - Execute catalog setup scripts `00_setup_catalog_and_schemas.py` and `01_create_catalog_and_delegate.sql`. | 13/07/2026 | 13/07/2026 | `src/pipeline/governance/`, `sql/infrastructure/` |
| 2 | - Define User-Defined Functions (UDFs) and apply tags for PII fields (`01_setup_tags_and_udf.py`). | 14/07/2026 | 14/07/2026 | `src/pipeline/governance/` |
| 3 | - Configure ABAC & Row/Column Level Security policies (`02_setup_abac_policy.py`). | 15/07/2026 | 15/07/2026 | Unity Catalog Policies

 |
| 4 | - Implement SQL scripts for Active Customer Views & Party Candidate Resolution (`01_active_customer_views.sql`, `02_party_candidate_view.sql`). | 16/07/2026 | 16/07/2026 | `sql/customer_360/` |
| 5 | - Run PII tag verification script (`03_apply_and_verify_pii_tags.py`) and log compliance evidence.

 | 17/07/2026 | 17/07/2026 | `resources/apply_and_verify_pii_tags.job.yml` |

### Week 5 Achievements:

* Configured dynamic PII masking on sensitive columns (Tax ID, Full Name, Email) in accordance with banking privacy standards.


* Established fine-grained ABAC and RBAC policies ensuring least-privilege data access.


* Developed SQL candidate views for Customer 360 Master Data Management (MDM).
* Verified policy execution in Unity Catalog using automated verification scripts.
