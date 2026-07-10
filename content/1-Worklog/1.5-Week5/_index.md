---
title: "Week 5: Amazon DynamoDB and Analysis Result Storage (01/06/2026 - 05/06/2026)"
menuTitle: "Week 5"
date: 2026-07-24
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Week 5 Objectives:**

- Learn about Amazon DynamoDB for storing image analysis results.
- Integrate Lambda to save Rekognition and Textract results to DynamoDB.

**Tasks completed this week:**

| Day | Task | Start Date | Completion Date | Reference |
|-----|------|------------|-----------------|-----------|
| Mon | Study Amazon DynamoDB: Table, Item, Partition Key, Sort Key. Learn about the pricing model: On-Demand vs. Provisioned Capacity. | 01/06/2026 | 01/06/2026 | https://docs.aws.amazon.com/dynamodb/ |
| Tue | Design the DynamoDB schema for the image_scan_results table: Partition Key: order_id, Sort Key: scan_timestamp, Attributes: bucket, key, rekognition_labels, textract_lines, status. | 02/06/2026 | 02/06/2026 | |
| Wed | Practice creating a DynamoDB table in On-Demand mode. Update the Lambda IAM Role to add the AmazonDynamoDBFullAccess permission. | 03/06/2026 | 03/06/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| Thu | Integrate DynamoDB into the Lambda function: After calling Rekognition and Textract, save results to the table. Test by uploading images and viewing items in the DynamoDB Console. | 04/06/2026 | 04/06/2026 | https://docs.aws.amazon.com/dynamodb/ |
| Fri | Integrate Amazon SNS to send email alerts when damaged cargo is detected (confidence > 80%). Test the complete pipeline. | 05/06/2026 | 05/06/2026 | |

**Week 5 Results:**

- Understood how to design a suitable DynamoDB schema for storing image analysis results.
- Successfully created and configured a DynamoDB table in On-Demand mode.
- Successfully integrated DynamoDB into Lambda; analysis results are stored completely.
- Integrated Amazon SNS to automatically send email alerts when damaged cargo is detected.
- Completed the full pipeline: S3 → SQS → Lambda → AI/ML → DynamoDB → SNS.
