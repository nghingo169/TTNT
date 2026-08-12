---
title: "Proposal"
date: 2026-06-15
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

## Project Overview

During the **TAC@NABVN Starcamp - Product Data Engineer** internship program at NAB Innovation Centre Vietnam (from June 15, 2026 to August 14, 2026), my team and I proposed a two-phase product engineering initiative combining **Product Mindset & Discovery** with **Zero-Trust Data Engineering Architecture**[cite: 1, 3]. 

The program bridges the gap between customer-centric product ideation and robust, secure enterprise data engineering[cite: 1]. The proposal is structured into two core components:

1. **Financial Wellbeing Assistant (Product Ideation & Discovery):** A customer-centric banking solution designed to empower retail customers to track cash flows, reduce financial anxiety, and build healthy saving habits while providing NAB Relationship Managers (Bankers) with actionable financial health insights[cite: 1].
2. **Zero-Trust Banking Data Pipeline (Production Technical Architecture):** An enterprise-grade, end-to-end Medallion Data Pipeline built on **Databricks Delta Lake**[cite: 1]. It processes multi-domain banking datasets (Customer, Card, Transaction, FinCrime) while enforcing strict Zero-Trust Security, Attribute-Based Access Control (ABAC), Shift-Left Data Quality rules, automated Quarantine routing, and CI/CD orchestration[cite: 1].

---

## Problem and Motivation

### 1. The Customer & Business Problem (Product Mindset)
Banking customers often struggle to balance regular bills, credit commitments, and savings goals[cite: 1]. Without predictive visibility into their upcoming cash flows, customers face unexpected overdraft fees, missed payments, and severe financial stress[cite: 1]. Concurrently, bank relationship managers lack a unified 360-degree view to proactively detect early financial hardship signals and offer timely support[cite: 1].

### 2. The Data & Governance Problem (Data Engineering)
Modern financial institutions operate in highly regulated environments (e.g., APRA, CDR in Australia) where data breaches or compliance failures result in massive legal fines and loss of customer trust[cite: 1]. Traditional data pipelines often suffer from:
* **Siloed Data & Schema Drift:** Upstream application changes frequently break downstream analytics[cite: 1].
* **Data Quality Pollution:** Corrupted or bad data enters reporting warehouses due to late-stage testing[cite: 1].
* **Privacy Risks & Unmasked PII:** Sensitive Personally Identifiable Information (PII) is exposed to unauthorized internal roles without dynamic masking or strict access control[cite: 1].
* **Lack of Zero-Trust Security:** Over-privileged access models violate the principle of least privilege[cite: 1].

Addressing these challenges requires a holistic approach: first designing data products around human needs (**Product Centricity**), and second, engineering highly resilient, secure, and governed data pipelines (**Zero-Trust Data Engineering**)[cite: 1].

---

## Objectives and Scope

### Project Objectives

The main objectives of the internship project are:

1. **Apply Product Mindset & Design Thinking:** Conduct user research, formulate "5 Whys" root-cause analyses, map Customer Journeys, define Jobs-To-Be-Done (JTBD), and build Figma prototypes for the **Financial Wellbeing Assistant**[cite: 1].
2. **Evaluate Solution Viability (SDVF Framework):** Assess product concepts against Suitability (regulatory compliance), Desirability (customer demand), Viability (business impact), and Feasibility (technical execution)[cite: 1].
3. **Build an Enterprise Medallion Lakehouse Pipeline:** Implement a multi-layer pipeline (Bronze $\rightarrow$ Silver $\rightarrow$ Gold) on Databricks Delta Lake handling multi-domain banking data[cite: 1].
4. **Enforce Shift-Left Data Quality & Quarantine:** Define explicit Data Contracts (YAML) and Quality Rules to validate raw data at ingestion, routing non-compliant records to Quarantine tables without halting pipeline execution[cite: 1].
5. **Implement Zero-Trust Security & PII Governance:** Deploy Attribute-Based Access Control (ABAC), Row-Level Security (RLS), and Dynamic PII Masking via Unity Catalog to protect sensitive customer attributes[cite: 1].
6. **Automate CI/CD & Observability:** Configure Databricks Asset Bundles, GitHub Actions workflows, SAST security scans, and execution telemetry monitoring[cite: 1].

### Project Scope

* **In Scope:**
  * **Product Discovery:** Customer Personas (Retail User & NAB Banker), Empathy Mapping, JTBD, Low/High-Fidelity Figma Wireframes, and SDVF Assessment[cite: 1].
  * **Data Pipeline Architecture:** Ingesting 4 domain datasets (Customer, Card, Transaction, FinCrime) into Bronze Delta tables[cite: 1].
  * **Data Contracts & Quality:** Schema enforcement via YAML registries, data normalization, and quality rule validation (`bronze_to_validated_silver.py`)[cite: 1].
  * **Gold Layer Analytics & Identity Resolution:** Building `Customer 360`, `Fraud Transaction Context`, `AML Investigation Context`, and SQL Master Data Management (MDM) candidate views[cite: 1].
  * **Governance & CI/CD:** PII tagging, UDF masking, ABAC policy enforcement, PyTest automation, GitHub Actions integration, and execution telemetry[cite: 1].

* **Out of Scope:**
  * Providing regulated live financial advice within the customer prototype[cite: 1].
  * Production deployment on live core-banking transaction systems with real customer funds[cite: 1].

---

## Proposed Solution and Architecture

### 1. Product Solution: Financial Wellbeing Assistant

The proposed **Financial Wellbeing Assistant** operates via two synchronized interfaces:
* **Customer Mobile App:** Features a 30-day Predictive Cashflow Forecaster, Automated Micro-Savings Nudges, and Smart Bill Alerts[cite: 1].
* **Banker Portal:** Provides Relationship Managers with a Customer 360 Financial Health Index, highlighting early financial hardship signals to trigger proactive outreach[cite: 1].

### 2. Technical Architecture: Zero-Trust Banking Pipeline

The pipeline follows the **Medallion Lakehouse Architecture** integrated with Databricks Unity Catalog and Zero-Trust Security controls[cite: 1]:


```

[Raw Landing Source Data]
│
▼
┌────────────────────────────────────────────────────────────────────────┐
│ 1. BRONZE LAYER (Ingestion & Raw Delta Storage)                         │
│    - Batch ingestion via PySpark / Delta Lake                          │
│    - Schema validation against YAML Data Contracts                     │
└──────┬─────────────────────────────────────────────────────────────────┘
│
▼
┌────────────────────────────────────────────────────────────────────────┐
│ 2. SILVER LAYER (Cleansing, Standardization & Shift-Left Data Quality) │
│    - Quality Rule Engine & Schema Normalization                        │
│    - Split: Validated Records ──► Silver Atomic Tables                 │
│             Invalid Records   ──► Quarantine / Audit Tables             │
└──────┬─────────────────────────────────────────────────────────────────┘
│
▼
┌────────────────────────────────────────────────────────────────────────┐
│ 3. GOLD LAYER (Business Aggregations & Analytical Contexts)            │
│    - Customer 360 Health Context (Cashflow & Risk Features)            │
│    - Fraud Transaction Context & AML Investigation Views               │
│    - Identity Resolution & Entity Matching Views                       │
└──────┬─────────────────────────────────────────────────────────────────┘
│
▼
┌────────────────────────────────────────────────────────────────────────┐
│ 4. ZERO-TRUST GOVERNANCE & OBSERVABILITY (Unity Catalog)                │
│    - Dynamic PII Masking (UDFs) & Column-Level Tagging                 │
│    - Attribute-Based Access Control (ABAC) & Row-Level Security         │
│    - Automated Telemetry, Execution Logging & CI/CD Gating             │
└────────────────────────────────────────────────────────────────────────┘

```

### Component Responsibility Matrix

| Component | Planned Role & Implementation |
| :--- | :--- |
| **Databricks Delta Lake** | Core Lakehouse storage providing ACID transactions, time travel, and schema evolution[cite: 1]. |
| **PySpark Engine** | Distributed compute engine orchestrating Bronze, Silver, and Gold transformation pipelines[cite: 1]. |
| **Unity Catalog** | Centralized data governance, cataloging, ABAC policy management, and PII tag enforcement[cite: 1]. |
| **Data Contracts (YAML)** | Decoupled domain schema definitions and data quality rule inventories[cite: 1]. |
| **GitHub Actions** | Automated CI/CD pipeline running PyTest, Flake8 linting, and Bandit SAST security scans[cite: 1]. |
| **Databricks Asset Bundles** | Declarative pipeline deployment and job orchestration in non-production environments[cite: 1]. |
| **Figma** | High-fidelity interactive prototyping for the Financial Wellbeing Assistant user flows[cite: 1]. |

---

## Project Plan and Timeline

The 8-week internship is organized into **4 Sprints (2 weeks per Sprint)**, transitioning smoothly from Product Discovery to Technical Pipeline Engineering[cite: 1]:


```

┌────────────────────────────────────────────────────────────────────────┐
│ PHASE 1: PRODUCT MINDSET & DISCOVERY (Weeks 1 - 2 / Sprint A)           │
│ - Banking Domain Knowledge & APRA/CDR Compliance                       │
│ - Design Thinking, "5 Whys", Customer Personas & JTBD Framework        │
│ - SDVF Assessment & Sprint A Pitch Deck Presentation                   │
└────────────────────────────────────────────────────────────────────────┘
│
▼
┌────────────────────────────────────────────────────────────────────────┐
│ PHASE 2: ZERO-TRUST PIPELINE ENGINEERING (Weeks 3 - 8 / Sprints 1 - 4) │
│ - Weeks 3-4 (Sprint 1): Data Contracts & Bronze/Silver Pipelines       │
│ - Weeks 5-6 (Sprint 2): Zero-Trust Governance, ABAC & Customer 360     │
│ - Week 7 (Sprint 3): CI/CD Automation, Telemetry & Figma Finalization  │
│ - Week 8 (Sprint 4): Final Showcase & Business Impact Assessment      │
└────────────────────────────────────────────────────────────────────────┘

```

### Detailed Weekly Timeline

| Week | Phase / Focus Area | Planned Activities & Deliverables |
| :--- | :--- | :--- |
| **Week 1** | **Onboarding & Problem Framing** | Onboard to TAC@NABVN Starcamp[cite: 1]. Learn banking domain fundamentals (Retail, Corporate, Regulatory Compliance)[cite: 1]. Kick off **Financial Wellbeing Assistant** project[cite: 1]. Conduct "5 Whys" analysis and write Confluence Deliverables 1 & 7[cite: 1]. |
| **Week 2** | **Customer Discovery & SDVF Pitch** | Build Customer Personas (Alex & Sarah) and JTBD mappings[cite: 1]. Execute SDVF Assessment and Responsible Design evaluation[cite: 1]. Draft low-fidelity wireframes[cite: 1]. Present Sprint A proposal pitch deck to Product Owners[cite: 1]. |
| **Week 3** | **Data Contracts & Bronze Layer** | Onboard `zero-trust-banking-pipeline` codebase[cite: 1]. Define YAML Data Contracts for 4 domains[cite: 1]. Implement `source_to_bronze_ingestion.py` PySpark scripts and write Bronze unit tests[cite: 1]. |
| **Week 4** | **Silver Transformations & Data Quality** | Build Silver domain transformations (`customer`, `card`, `transaction`, `fincrime`)[cite: 1]. Implement Quality Rule Registry and build `bronze_to_validated_silver.py` with automatic Quarantine routing[cite: 1]. |
| **Week 5** | **Zero-Trust Governance & ABAC** | Configure Databricks Unity Catalog permissions, schemas, and UDFs[cite: 1]. Apply dynamic PII masking and ABAC security policies[cite: 1]. Build SQL views for Customer 360 identity candidate resolution[cite: 1]. |
| **Week 6** | **Gold Aggregations & Diagnostics** | Build Gold Layer pipelines (`customer_360_context.py`, `fraud_transaction_context.py`, `aml_investigation_context.py`)[cite: 1]. Write diagnostic SQL queries for unresolved KYC and Employment records[cite: 1]. |
| **Week 7** | **CI/CD, Monitoring & Figma Prototype** | Configure GitHub Actions CI/CD workflows and Databricks Asset Bundles[cite: 1]. Build telemetry monitoring views[cite: 1]. Finalize high-fidelity Figma Prototype and Confluence Sprint Artefacts[cite: 1]. |
| **Week 8** | **Final Showcase & Submission** | Deliver Final Showcase presentation to NAB Product Owners and Data Leads[cite: 1]. Evaluate business impact metrics[cite: 1]. Complete CSE HCMUT Internship Report and obtain company approvals[cite: 3]. |

---

## Expected Outcomes

By the end of the internship program, the project delivers the following tangible outcomes:

1. **Product Discovery Artefacts:**
   * A fully documented **Financial Wellbeing Assistant** space on Confluence covering 13 comprehensive deliverables (Personas, JTBD, SDVF, Design Principles, Feature Specs)[cite: 1].
   * An interactive, high-fidelity **Figma Prototype** demonstrating retail customer and banker user flows[cite: 1].

2. **Technical Data Engineering Artefacts:**
   * A fully functional, production-ready **Zero-Trust Banking Data Pipeline** built on Databricks Delta Lake[cite: 1].
   * Standardized **YAML Data Contracts** enforcing schema consistency across 4 banking domains[cite: 1].
   * A **Shift-Left Quality Control Engine** with automated Quarantine table routing[cite: 1].
   * An **ABAC & Dynamic PII Masking Security Layer** compliant with banking privacy standards[cite: 1].
   * **Gold Layer Context Views** powering Customer 360 analytics, Fraud detection, and AML investigations[cite: 1].
   * An automated **CI/CD Pipeline (GitHub Actions)** with unit tests, linting, SAST security checks, and telemetry logging[cite: 1].