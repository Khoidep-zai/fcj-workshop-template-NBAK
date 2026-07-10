---
title: "Step 5: Test the System"
date: 2026-07-24
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---
### Objective

Verify that the entire **S3 → SQS → Lambda → AI** pipeline is working correctly.

In this step, you will upload images to S3, verify that Lambda processes the SQS messages, and review the analysis results in CloudWatch Logs.

---

### 5.1 - Prepare Test Images

Prepare at least 2 types of images:

- A damaged or dented package image to verify that Amazon Rekognition correctly identifies the image content.
- An image with a shipping label containing a clearly visible tracking number to verify that Amazon Textract correctly extracts the text.

---

### 5.2 - Upload Images to S3

1. Go to the S3 bucket **logistics-raw-images-&lt;your-name&gt;**, then click **Upload**.

2. Upload approximately **5–10 images** at once to test parallel processing capability.

3. Click **Upload** to start uploading.

![Upload images to S3](/images/5.6-Step5/image13.png)

![Upload complete](/images/5.6-Step5/image14.png)

---

### 5.3 - Check CloudWatch Logs

1. Go to **CloudWatch** and select **Log groups**.

2. Search for the log group **/aws/lambda/image-quality-processor**.

3. Select the latest log stream and review the Lambda output.

![Check CloudWatch Log groups](/images/5.6-Step5/image15.png)

![Check Lambda output](/images/5.6-Step5/image16.png)

---

### 5.4 - Verify SQS Queue is Empty

1. Go to the **SQS Console** and select the **image-processing-queue** queue.

2. Click **Send and receive messages**.

3. Click **Poll for messages**.

If the queue is empty, it means Lambda has successfully processed all messages.

![Check messages in SQS](/images/5.6-Step5/image17.png)
