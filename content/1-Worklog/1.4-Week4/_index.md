---
title: "Week 4 Worklog"
date: 2026-07-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
includeInReport: true
reportTableColumns:
  - Day
  - Task
  - Completion Date
reportHeadings:
  - Week 4 Objectives
  - Tasks to be carried out this week
  - Week 4 Achievements
reportType: worklog
---

### Week 4 Objectives:

* Explore AWS security and identity management services: IAM, KMS, CloudTrail and GuardDuty.
* Practice creating IAM Users, Groups, Roles and applying Least‑Privilege Policy.
* Set up CloudTrail to record account activity and enable GuardDuty for threat detection.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | - Read IAM fundamentals documentation <br> - Create IAM User, attach "ReadOnlyAccess" policy | 06/23/2026 | 06/23/2026 | https://cloudjourney.awsstudygroup.com/ |
| 2 | - Create IAM Role for EC2 with S3 read/write and SSM GetParameters permissions | 06/24/2026 | 06/24/2026 | https://cloudjourney.awsstudygroup.com/ |
| 3 | - Practice creating a Customer Managed Key (CMK) using AWS KMS <br> - Encrypt an S3 object | 06/25/2026 | 06/25/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Enable CloudTrail for all regions <br> - Review logs in S3 bucket | 06/26/2026 | 06/26/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Enable GuardDuty <br> - View sample findings and document response steps | 06/27/2026 | 06/27/2026 | https://cloudjourney.awsstudygroup.com/ |

### Week 4 Achievements:

* IAM Users, Groups and Roles created with principle of least privilege applied.
* Customer Managed Key (CMK) created successfully; S3 data encrypted and decrypted.
* CloudTrail recorded all API actions and stored logs in a backup bucket.
* GuardDuty enabled, sample findings detected and remediation steps practiced.
