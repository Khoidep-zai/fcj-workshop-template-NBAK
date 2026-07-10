---
title: "Step 6: Clean Up Resources"
date: 2026-07-24
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---
### Objective

After completing the workshop, you need to delete the resources you created to avoid incurring unnecessary costs.

---

### 1. Delete the SQS Queue

1. Go to **Amazon SQS**.

2. Select the queue created during the workshop, then click **Delete**.

![Delete SQS queue](/images/5.7-Step6/image1.png)

3. Type **Confirm** to confirm the deletion.

![Confirm SQS queue deletion](/images/5.7-Step6/image2.png)

---

### 2. Delete the Lambda Function

1. Go to **AWS Lambda**.

2. Select the function created during the workshop, then click **Delete**.

![Delete Lambda function](/images/5.7-Step6/image3.png)

3. Enter the confirmation text to delete the function.

![Confirm Lambda function deletion](/images/5.7-Step6/image4.png)

---

### 3. Delete the S3 Bucket

1. Go to **Amazon S3**.

2. Navigate to the bucket created during the workshop.

3. Select the bucket and click **Delete**.

Note: An S3 bucket must be emptied before it can be deleted. If the bucket still contains objects, delete all objects inside it first.

![Delete S3 bucket](/images/5.7-Step6/image5.png)

---

### 4. Delete the IAM Role

1. Go to **IAM**.

2. Select **Roles**.

3. Select the IAM Role **Lambda-ImageProcessing-Role** created during the workshop, then delete it.

![Delete IAM Role](/images/5.7-Step6/image6.png)
