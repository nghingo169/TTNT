---
title: "Self-Assessment"
date: 2026-08-14
weight: 6
chapter: false
pre: " <b> 6. </b> "
includeInReport: true
---

During my internship in the **TAC@NABVN Starcamp - Product Data Engineer** program at **NAB Innovation Centre Vietnam** from **15/06/2026** to **14/08/2026**, I had the invaluable opportunity to bridge academic knowledge with enterprise-grade engineering practices.

Throughout the 8-week program, I successfully engaged in a two-phase product engineering journey:
1. **Product Mindset & Discovery Phase:** Spearheaded the **Financial Wellbeing Assistant** project with team `[TheHELLO]`, applying Design Thinking, "5 Whys" root-cause analysis, Customer Journey Mapping, Jobs-To-Be-Done (JTBD) frameworks, SDVF Assessments, and interactive Figma prototyping.
2. **Data Engineering & Governance Phase:** Designed, engineered, and deployed the **Zero-Trust Banking Data Pipeline** on Databricks Delta Lake. I built multi-domain PySpark pipelines (Customer, Card, Transaction, FinCrime) following Medallion Architecture, enforced Shift-Left Data Quality rules with automated Quarantine routing, implemented Attribute-Based Access Control (ABAC) and Dynamic PII Masking via Unity Catalog, and configured automated CI/CD workflows using GitHub Actions and Databricks Asset Bundles.

Through these projects, I significantly advanced my technical competencies in **PySpark, Databricks Delta Lake, SQL Master Data Management (MDM), Data Contracts (YAML), Zero-Trust Security (ABAC/RBAC/PII Masking), GitHub Actions CI/CD, Product Centricity, and Figma Prototyping**.

In terms of work ethic, I maintained a high level of dedication, adhered strictly to corporate policies and banking compliance standards, and collaborated effectively with mentors, Product Owners, and team members to maximize project impact.

To objectively reflect on my internship performance, I evaluate myself based on the following criteria:

| No. | Criteria | Description | Good | Fair | Average |
| --- | ----------------------------------- | ------------------------------------------------------------------------------------------------ | ---- | ---- | ------- |
| 1 | **Professional knowledge & skills** | Understanding of data engineering & product mindset, applying knowledge in practice, work quality | [X] | [ ] | [ ] |
| 2 | **Ability to learn** | Ability to absorb complex cloud & governance concepts quickly | [X] | [ ] | [ ] |
| 3 | **Proactiveness** | Taking initiative in task execution, problem-solving, and architectural research | [X] | [ ] | [ ] |
| 4 | **Sense of responsibility** | Completing pipeline modules and Confluence deliverables on time with high quality | [X] | [ ] | [ ] |
| 5 | **Discipline** | Adhering to schedules, agile ceremonies, security rules, and work processes | [X] | [ ] | [ ] |
| 6 | **Progressive mindset** | Willingness to receive feedback during Design Critiques and continuously refine solutions | [X] | [ ] | [ ] |
| 7 | **Communication** | Presenting ideas during pitch decks, technical discussions, and reporting work clearly | [ ] | [X] | [ ] |
| 8 | **Teamwork** | Collaborating effectively in Group `[TheHELLO]`, sharing knowledge, and reviewing pull requests | [X] | [ ] | [ ] |
| 9 | **Professional conduct** | Respecting mentors, colleagues, banking data privacy rules, and the corporate environment | [X] | [ ] | [ ] |
| 10 | **Problem-solving skills** | Diagnosing data anomalies, designing quarantine routing, and resolving identity edge cases | [X] | [ ] | [ ] |
| 11 | **Contribution to project/team** | Delivering robust pipeline code, complete Confluence documentation, and successful Final Showcase | [X] | [ ] | [ ] |
| 12 | **Overall** | General evaluation of the entire internship period | [X] | [ ] | [ ] |

---

### Summary of Achievements

* **Product Centricity & Discovery:** Completed all 13 Confluence deliverables for the **Financial Wellbeing Assistant**, defining clear Customer Personas (Alex & Sarah), JTBD mappings, and an interactive high-fidelity Figma Prototype for cash flow forecasting and banker health tracking.
* **Enterprise Medallion Data Pipeline:** Built an end-to-end data pipeline processing 4 banking domains (Customer, Card, Transaction, FinCrime) from raw landing to Gold layer aggregations on Databricks Delta Lake.
* **Shift-Left Data Quality & Governance:** Implemented YAML-based Data Contracts, a domain Quality Rule Engine, and automated Quarantine table routing for corrupted records (`bronze_to_validated_silver.py`).
* **Zero-Trust Security Implementation:** Configured fine-grained ABAC/RBAC policies and Dynamic PII Masking via UDFs in Databricks Unity Catalog, ensuring strict compliance with APRA/CDR banking standards.
* **DevOps & CI/CD Automation:** Established automated GitHub Actions workflows with Flake8 linting, PyTest unit testing, and Bandit SAST security scans, orchestrated via Databricks Asset Bundles.
* **Successful Final Showcase:** Delivered an outstanding Final Showcase presentation to NAB Product Owners and Data Leads, demonstrating both business value realization and technical engineering rigor.

---

### Areas for Improvement

* **Refine Technical Presentation Skills:** Continue improving the ability to explain complex data pipeline architectures and Zero-Trust governance concepts to non-technical business stakeholders in a more concise manner.
* **Deepen Cloud Cost Optimization:** Further explore advanced Databricks cluster sizing, auto-scaling configurations, and serverless compute models to optimize pipeline running costs in production.
* **Enhance Development Time Estimation:** Improve accuracy when estimating time required for complex PySpark transformations, schema debugging, and identity resolution SQL diagnostic queries.
* **Strengthen Autonomous Debugging:** Continue developing independent troubleshooting capabilities for edge cases in multi-table identity resolution before seeking mentor intervention.