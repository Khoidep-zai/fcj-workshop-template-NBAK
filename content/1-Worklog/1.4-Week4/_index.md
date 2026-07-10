---
title: "Week 4"
date: 2026-07-24
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## Week 4: Amazon Rekognition and Textract — AI/ML Image Analysis (25/05/2026 - 29/05/2026)

**Week 4 Objectives:**

- Integrate Amazon Rekognition to detect damage in cargo packages.
- Integrate Amazon Textract to extract tracking numbers and information from shipping labels.

**Tasks completed this week:**

| Day | Task | Start Date | Completion Date | Reference |
|-----|------|------------|-----------------|-----------|
| Mon | Study Amazon Rekognition: detect_labels, detect_text, compare_faces. Understand how to use MaxLabels and MinConfidence to filter analysis results. | 25/05/2026 | 25/05/2026 | https://docs.aws.amazon.com/rekognition/ |
| Tue | Study Amazon Textract: detect_document_text, analyze_document. Understand the difference between LINE and WORD blocks in Textract results. | 26/05/2026 | 26/05/2026 | https://docs.aws.amazon.com/textract/ |
| Wed | Integrate Amazon Rekognition into the Lambda function: Call detect_labels on images from S3, log detected labels and confidence scores. Practice with cargo images. | 27/05/2026 | 27/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| Thu | Integrate Amazon Textract into the Lambda function: Call detect_document_text on images from S3, extract and log text lines (tracking numbers, phone numbers, addresses). | 28/05/2026 | 28/05/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| Fri | End-to-end testing: Upload 5–10 images simultaneously to S3. Verify CloudWatch Logs and confirm the SQS queue is empty after Lambda has processed all messages. | 29/05/2026 | 29/05/2026 | |

**Week 4 Results:**

- Understood how to use Amazon Rekognition to detect the condition of cargo (Box, Cardboard, Damaged, etc.).
- Understood how to use Amazon Textract to extract text from shipping labels.
- Successfully integrated both Rekognition and Textract into the image-processing Lambda function.
- Successfully completed end-to-end testing: image upload → SQS → Lambda → AI analysis → CloudWatch Logs.
- Confirmed parallel processing with multiple images; the SQS queue was fully processed and emptied.
