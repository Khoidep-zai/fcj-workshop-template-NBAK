---
title: "Step 2: Create an Amazon SQS Queue"
date: 2026-07-24
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---
### Introduction

Amazon SQS acts as an intermediate queue between Amazon S3 and AWS Lambda.

When a user uploads an image to S3, S3 sends a notification to SQS. Lambda then reads and processes messages from SQS incrementally, keeping the system stable even when many images are uploaded simultaneously.

---

### Steps

1. Go to the **AWS Console**, search for **Amazon SQS**, then click **Create queue**.

![Search for Amazon SQS](/images/5.3-Step2/image13.png)

2. Select **Standard Queue** as the queue type.

Do not select **FIFO Queue** for this workshop — the goal is asynchronous image processing with high scalability, which does not require strict message ordering.

![Select Standard Queue](/images/5.3-Step2/image14.png)

3. Name the queue **image-processing-queue**.

![Name the SQS queue](/images/5.3-Step2/image15.png)

4. Configure the important queue parameters.

![Configure SQS parameters](/images/5.3-Step2/image16.png)

![Review SQS configuration](/images/5.3-Step2/image17.png)

5. Click **Create queue** to create the queue.

6. After the queue is created, copy the **ARN**. This ARN will be used in the S3 Event Notification configuration step.

![Copy the SQS queue ARN](/images/5.3-Step2/image18.png)
