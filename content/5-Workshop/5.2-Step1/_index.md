---
title: "Step 1: Set Up IAM Role for Lambda"
date: 2026-07-24
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---
### Introduction

An IAM Role defines the permissions that Lambda uses to access the required AWS services in this workshop, including Amazon S3, Amazon SQS, Amazon Rekognition, and Amazon Textract.

In this step, you will create an IAM Role for Lambda and attach the necessary policies so that Lambda can read data, receive messages, and write logs during image processing.

---

### Steps

1. Go to the **AWS Console** and search for the **IAM** service.

![Search for the IAM service](/images/5.2-Step1/image1.png)

2. Select **Roles**, then click **Create role**.

![Select Roles and Create role](/images/5.2-Step1/image2.png)

3. Under **Trusted entity type**, select **AWS service**.

4. Under **Use case**, select **Lambda**, then click **Next**.

![Select AWS service and Lambda](/images/5.2-Step1/image3.png)

5. Search for and attach the required policies for Lambda one by one.

![Search for Lambda policies](/images/5.2-Step1/image4.png)

![Select Lambda policies](/images/5.2-Step1/image5.png)

![Attach AWSLambdaBasicExecutionRole policy](/images/5.2-Step1/image6.png)

![Attach AmazonS3ReadOnlyAccess policy](/images/5.2-Step1/image7.png)

![Attach AmazonSQSFullAccess policy](/images/5.2-Step1/image8.png)

![Attach Rekognition and Textract policies](/images/5.2-Step1/image9.png)

6. Name the role **Lambda-ImageProcessing-Role**, then click **Create role**.

![Name the IAM Role](/images/5.2-Step1/image10.png)

![Create the IAM Role](/images/5.2-Step1/image11.png)

---

### Security Note

In a production environment, instead of using AWS managed policies, you should write a **Custom Policy** to restrict permissions to only the specific bucket or queue required.

This is a security best practice following the **Least Privilege** principle — granting only the exact permissions needed, nothing more.

![Custom policy following the Least Privilege principle](/images/5.2-Step1/image12.png)
