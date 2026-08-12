



---

## WEEK 3 WORKLOG (29/06/2026 - 03/07/2026)

---

title: "Week 3 Worklog"
date: 2026-07-03
weight: 3
chapter: false
pre: "  1.3.  "
includeInReport: true
reportTableColumns:

* Day
* Task
* Completion Date
reportHeadings:
* Week 3 Objectives
* Tasks to be carried out this week
* Week 3 Achievements
reportType: worklog

---

### Week 3 Objectives:

* Transition to technical pipeline engineering: Onboard the **zero-trust-banking-pipeline** repository.
* Study Lakehouse architecture, PySpark, and Delta Lake ACID transaction features.


* Ingest raw datasets into the **Bronze Layer** and define YAML Data Contracts for domain schemas.



### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - Set up Databricks workspace and clone `zero-trust-banking-pipeline-main` repository.<br>

<br>- Explore codebase directory structure. | 29/06/2026 | 29/06/2026 | Project Codebase |
| 2 | - Define YAML Data Contracts for 4 banking domains (`Customer`, `Card`, `Transaction`, `FinCrime`). | 30/06/2026 | 30/06/2026 | `data_contract/*.yaml`<br> |
| 3 | - Write raw data ingestion module `src/pipeline/bronze/source_to_bronze_ingestion.py`. | 01/07/2026 | 01/07/2026 | `src/pipeline/bronze/` |
| 4 | - Create local snapshot loading shell script `scripts/source_landing/load_local_snapshots.sh`. | 02/07/2026 | 02/07/2026 | `scripts/source_landing/` |
| 5 | - Write PyTest unit tests for Bronze Layer (`tests/bronze/test_bronze.py`) and verify ingestion runs. | 03/07/2026 | 03/07/2026 | `tests/bronze/` |

### Week 3 Achievements:

* Successfully onboarded the `zero-trust-banking-pipeline` project structure.
* Enforced schema validation at entry points using YAML Data Contracts.
* Built automated Bronze Layer ingestion pipelines writing raw landing data to Delta Lake format.
* Passed all Bronze Layer unit tests with 100% assertion coverage.