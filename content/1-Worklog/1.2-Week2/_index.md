---
title: "Week 2"
date: 2026-07-24
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Week 2: Amazon S3, SQS, and Event-Driven Architecture (11/05/2026 - 15/05/2026)

**Week 2 Objectives:**

- Gain an in-depth understanding of Amazon S3 and how to organize cargo image storage.
- Learn about Amazon SQS and its role as a buffer in an Event-Driven architecture.
- Design the S3 → SQS → Lambda pipeline for the asynchronous image processing system.

**Tasks completed this week:**

| Day | Task | Start Date | Completion Date | Reference |
|-----|------|------------|-----------------|-----------|
| Mon | Study Amazon S3: Bucket, Object, Storage Class, Lifecycle Policy, Versioning. Research how to organize prefixes for a bucket storing damaged cargo images. | 11/05/2026 | 11/05/2026 | https://docs.aws.amazon.com/s3/ |
| Tue | Study Amazon SQS: Standard Queue vs. FIFO Queue. Understand key parameters: Visibility Timeout, Message Retention Period, Dead Letter Queue. | 12/05/2026 | 12/05/2026 | https://docs.aws.amazon.com/sqs/ |
| Wed | Research the Event-Driven architecture using the S3 → SQS → Lambda pattern. Understand why SQS is needed as a buffer to prevent Lambda from being overwhelmed when many images are uploaded simultaneously. | 13/05/2026 | 13/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| Thu | Practice: Create an S3 bucket for storing cargo images. Configure S3 Lifecycle Policy and Versioning for the bucket. | 14/05/2026 | 14/05/2026 | https://000057.awsstudygroup.com/vi/ |
| Fri | Practice: Create an SQS Standard Queue (image-processing-queue). Configure the Access Policy to allow S3 to send messages to SQS. Configure S3 Event Notification. | 15/05/2026 | 15/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |

**Week 2 Results:**

- Understood the core concepts of Amazon S3: Bucket, Object, Storage Class, Lifecycle, and Versioning.
- Grasped the role of Amazon SQS in an Event-Driven architecture and why a buffer is needed between S3 and Lambda.
- Successfully created and configured an S3 bucket with Event Notification.
- Successfully created an SQS Standard Queue and granted S3 permission to send messages to the queue.
- Clearly understood the S3 → SQS → Lambda processing pipeline and why this architecture is suitable for large-scale image processing.
