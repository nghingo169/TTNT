---
title: "Week 5 Worklog"
date: 2026-07-08
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
includeInReport: true
reportTableColumns:
  - Day
  - Task
  - Completion Date
reportHeadings:
  - Week 5 Objectives
  - Tasks to be carried out this week
  - Week 5 Achievements
reportType: worklog
---

### Week 5 Objectives:

* Understand AWS Database services: RDS, DynamoDB, ElastiCache.
* Deploy an RDS MySQL instance and connect to it from EC2.
* Create a DynamoDB table and practice CRUD operations.
* Implement caching with ElastiCache (Redis).

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | - Read RDS documentation (MySQL) <br> - Launch an RDS MySQL (db.t3.micro) in private subnet | 06/28/2026 | 06/28/2026 | https://cloudjourney.awsstudygroup.com/ |
| 2 | - Configure Security Group for RDS (port 3306) <br> - Connect from EC2 using MySQL client | 06/29/2026 | 06/29/2026 | https://cloudjourney.awsstudygroup.com/ |
| 3 | - Read DynamoDB documentation <br> - Create DynamoDB table (on-demand capacity) <br> - Insert, query, and delete items via Console and AWS CLI | 06/30/2026 | 06/30/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Read ElastiCache (Redis) documentation <br> - Launch a Redis cluster in default VPC | 07/01/2026 | 07/01/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Connect EC2 to Redis cluster using `redis-cli` <br> - Practice basic cache operations (SET/GET) | 07/02/2026 | 07/02/2026 | https://cloudjourney.awsstudygroup.com/ |

### Week 5 Achievements:

* RDS MySQL instance deployed successfully; EC2 connected and queried the database.
* DynamoDB table created with partition key "UserId" and sort key "Timestamp"; CRUD operations practiced via Console and CLI.
* ElastiCache Redis cluster running and basic caching operations performed.
* Gained understanding of relational (RDS) vs NoSQL (DynamoDB) database choices on AWS.
