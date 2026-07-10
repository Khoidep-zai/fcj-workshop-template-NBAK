---
title: "Step 3: Configure Amazon S3 Storage and Events"
date: 2026-07-24
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---
### Objective

In this step, you will create an S3 bucket to store images and configure it so that every time a new image is uploaded, Amazon S3 automatically sends a notification to the SQS queue created in the previous step.

---

### 3.1 - Create an S3 Bucket

1. Go to **Amazon S3**, then click **Create bucket**.

![Create S3 bucket](/images/5.4-Step3/image19.png)

2. Name the bucket following the format **logistics-raw-images-&lt;your-name&gt;**.

The bucket name must be globally unique across all of AWS.

![Name the S3 bucket](/images/5.4-Step3/image20.png)

3. Select Region **ap-southeast-1 (Singapore)** for proximity to Vietnam.

![Select Singapore Region](/images/5.4-Step3/image21.png)

4. Keep the default settings, then click **Create bucket**.

![Keep default settings](/images/5.4-Step3/image22.png)

![Bucket created successfully](/images/5.4-Step3/image23.png)

---

### 3.2 - Grant S3 Permission to Send Notifications to SQS

1. Go to the **SQS Console** and select the **image-processing-queue** queue.

2. Open the **Access policy** tab and choose to edit the policy.

3. Add a policy to allow S3 to send messages to SQS.

![Open SQS Access policy](/images/5.4-Step3/image24.png)

Example policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "s3.amazonaws.com"
      },
      "Action": "sqs:SendMessage",
      "Resource": "arn:aws:sqs:ap-southeast-1:<account-id>:image-processing-queue",
      "Condition": {
        "ArnLike": {
          "aws:SourceArn": "arn:aws:s3:::logistics-raw-images-<your-name>"
        }
      }
    }
  ]
}
```

Replace **&lt;account-id&gt;** with your AWS Account ID and **logistics-raw-images-&lt;your-name&gt;** with the name of the bucket you created.

![Add S3 permission to send messages to SQS](/images/5.4-Step3/image25.png)

---

### 3.3 - Configure S3 Event Notification

1. Go to the bucket you just created, open the **Properties** tab, scroll down to the **Event notifications** section, then click **Create event notification**.

![Open Event notifications](/images/5.4-Step3/image26.png)

![Create event notification](/images/5.4-Step3/image27.png)

2. Name the event **new-image-uploaded**.

![Name the event notification](/images/5.4-Step3/image28.png)

3. Under **Event types**, check **s3:ObjectCreated:***.

![Select ObjectCreated event type](/images/5.4-Step3/image29.png)

4. Under **Prefix/Suffix**, enter image suffixes such as **.jpg**, **.jpeg**, **.png** to trigger only when image files are uploaded.

This configuration ensures that non-image files such as `.txt` or `.pdf` are ignored.

![Configure image file suffixes](/images/5.4-Step3/image30.png)

5. Under **Destination**, select **SQS Queue**, then choose the **image-processing-queue** queue.

![Select SQS queue as destination](/images/5.4-Step3/image31.png)

6. Click **Save changes** to save the configuration.

![Save event notification](/images/5.4-Step3/image32.png)
