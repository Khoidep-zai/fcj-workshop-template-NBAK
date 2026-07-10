---
title: "Week 9"
date: 2026-07-24
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

## Week 9: Backend Development — Lambda, S3, SQS, and AI/ML Integration (29/06/2026 - 03/07/2026)

**Week 9 Objectives:**

- Complete the entire serverless backend with all necessary Lambda functions.
- Optimize processing performance and handle error scenarios (error handling).

**Tasks completed this week:**

| Day | Task | Start Date | Completion Date | Reference |
|-----|------|------------|-----------------|-----------|
| Mon | Complete the orchestrator Lambda function: Fully process all records from the SQS batch, call Rekognition and Textract in parallel, handle timeouts and retries. | 29/06/2026 | 29/06/2026 | |
| Tue | Develop the evaluator Lambda function: Assess the level of damage from Rekognition results, define confidence thresholds for classification. | 30/06/2026 | 30/06/2026 | |
| Wed | Develop the processor Lambda function: Store complete results in DynamoDB, trigger SNS notifications for critical cases. | 01/07/2026 | 01/07/2026 | |
| Thu | Configure a Dead Letter Queue (DLQ) for SQS. Add CloudWatch Alarms for Lambda errors and SQS queue depth. Test various error scenarios. | 02/07/2026 | 02/07/2026 | |
| Fri | Load-test the backend: Upload 20–30 images simultaneously. Record performance limits and propose optimization strategies. Write API documentation for frontend use. | 03/07/2026 | 03/07/2026 | |

**Week 9 Results:**

- Completed 3 Lambda functions (orchestrator, evaluator, processor) with comprehensive error handling.
- Configured a DLQ to handle failed messages and prevent data loss.
- Added CloudWatch Alarms for proactive monitoring of system errors.
- Successfully load-tested with 20–30 simultaneous images; the backend remained stable.
