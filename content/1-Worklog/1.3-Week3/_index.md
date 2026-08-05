---
title: "Week 3 Worklog"
date: 2026-06-24
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
includeInReport: true
reportTableColumns:
  - Day
  - Task
  - Completion Date
reportHeadings:
  - Week 3 Objectives
  - Tasks to be carried out this week
  - Week 3 Achievements
reportType: worklog
---

### Week 3 Objectives:

* Master AWS Compute services: EC2, Lambda, Step Functions and Application Load Balancer.
* Deploy an EC2 instance, configure security groups, IAM role and test SSH.
* Build a simple Lambda function and integrate with API Gateway.
* Explore Step Functions to orchestrate Lambda.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | - Read EC2 fundamentals documentation <br> - Launch a t3.micro instance, set up key pair and IAM role with S3 read access | 06/18/2026 | 06/18/2026 | https://cloudjourney.awsstudygroup.com/ |
| 2 | - Create Security Group (SSH, HTTP, HTTPS) <br> - Open ports 22, 80, 443 and verify SSH connection from laptop | 06/19/2026 | 06/19/2026 | https://cloudjourney.awsstudygroup.com/ |
| 3 | - Create a "HelloWorld" Lambda function using Python <br> - Configure Python 3.11 runtime | 06/20/2026 | 06/20/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Set up API Gateway (HTTP API) as a trigger for Lambda <br> - Test with cURL `GET /hello` | 06/21/2026 | 06/21/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Design a simple Step Function to invoke Lambda "HelloWorld" and run via console | 06/22/2026 | 06/22/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Read Application Load Balancer documentation <br> - Take notes on how to integrate ALB with EC2 | 06/23/2026 | 06/23/2026 | https://cloudjourney.awsstudygroup.com/ |

### Week 3 Achievements:

* EC2 instance launched with IAM role granting S3 access; security group configured with necessary ports; SSH connection successful.
* "HelloWorld" Lambda deployed, integrated with API Gateway, and returning correct response.
* Step Function created and orchestrated Lambda successfully.
* Understood how Application Load Balancer works and prepared for multi-layer architecture in the project.
