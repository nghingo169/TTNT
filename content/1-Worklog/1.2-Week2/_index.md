---
title: "Week 2 Worklog"
date: 2026-06-17
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
includeInReport: true
reportTableColumns:
  - Day
  - Task
  - Completion Date
reportHeadings:
  - Week 2 Objectives
  - Tasks to be carried out this week
  - Week 2 Achievements
reportType: worklog
---

### Week 2 Objectives:

* Explore advanced AWS storage services: Amazon S3 (advanced features), EBS, and AWS Backup.
* Practice managing bucket policies, versioning, Server‑Side Encryption, and lifecycle rules.
* Create, attach, and snapshot an EBS volume, then restore it on EC2.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | - Read S3 Advanced documentation <br> - Create an S3 bucket with versioning and SSE‑AES enabled | 06/13/2026 | 06/13/2026 | https://cloudjourney.awsstudygroup.com/ |
| 2 | - Set up Lifecycle Policy to automatically transition objects to S3 Glacier after 30 days | 06/14/2026 | 06/14/2026 | https://cloudjourney.awsstudygroup.com/ |
| 3 | - Launch EC2 instance (t3.micro) <br> - Create an EBS gp3 volume, attach to instance, and take a snapshot | 06/15/2026 | 06/15/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Restore snapshot to a new volume and mount it on EC2 to verify data | 06/16/2026 | 06/16/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Use AWS Backup to create a backup plan for EBS volume and test restore via Backup service | 06/17/2026 | 06/17/2026 | https://cloudjourney.awsstudygroup.com/ |

### Week 2 Achievements:

* S3 bucket successfully configured with versioning, SSE‑AES, and lifecycle policy.
* EBS gp3 volume created, snapshotted, and restored successfully on EC2.
* Backup plan for EBS set up and verified through AWS Backup.
* Gained solid understanding of advanced storage features and data security best practices on AWS.
