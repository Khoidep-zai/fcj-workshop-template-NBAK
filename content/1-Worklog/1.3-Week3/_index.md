---
title: "Week 3: AWS Lambda and Asynchronous Image Processing (18/05/2026 - 22/05/2026)"
menuTitle: "Week 3"
date: 2026-07-24
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Week 3 Objectives:**

- Learn about AWS Lambda and how to write a Python function to process SQS messages.
- Practice building a Lambda function that reads image information from SQS and S3.

**Tasks completed this week:**

| Day | Task | Start Date | Completion Date | Reference |
|-----|------|------------|-----------------|-----------|
| Mon | Study AWS Lambda: Function, Trigger, Runtime, Layer, Execution Role. Study the pricing model. | 18/05/2026 | 18/05/2026 | https://docs.aws.amazon.com/lambda/ |
| Tue | Set up the IAM Role for Lambda (Lambda-ImageProcessing-Role): AWSLambdaBasicExecutionRole, AmazonS3ReadOnlyAccess, AmazonSQSFullAccess, AmazonRekognitionFullAccess, AmazonTextractFullAccess. | 19/05/2026 | 19/05/2026 | https://docs.aws.amazon.com/IAM/ |
| Wed | Practice creating a Lambda Function (image-quality-processor, Python 3.x). Configure Timeout = 60 seconds, Memory = 512 MB. Attach SQS as the Trigger with Batch size = 1. | 20/05/2026 | 20/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| Thu | Write Python code to process SQS messages: Parse the SQS record to extract the bucket name and object key from the S3 event. Write logs to CloudWatch. Deploy and test. | 21/05/2026 | 21/05/2026 | https://docs.aws.amazon.com/lambda/ |
| Fri | Check CloudWatch Logs after uploading images. Debug connection issues. Clean up test resources after testing. | 22/05/2026 | 22/05/2026 | |

**Week 3 Results:**

- Understood how AWS Lambda works and its pricing model.
- Successfully created an IAM Role following the Least Privilege principle for Lambda.
- Created and configured a Lambda Function with an SQS Trigger (Batch size = 1).
- Successfully wrote Python code to process SQS messages, read image information from S3, and write logs to CloudWatch.
- Successfully tested and debugged the entire S3 → SQS → Lambda pipeline.
