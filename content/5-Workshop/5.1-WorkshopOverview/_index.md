---
title: "Workshop Overview"
date: 2026-07-24
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Building an Asynchronous Image Processing Pipeline Using Amazon S3, SQS, and AWS Lambda

### Workshop Summary

This workshop guides you through building an asynchronous image processing pipeline following the Event-Driven architecture on AWS. It solves the challenge of "multiple users uploading images simultaneously" while ensuring system stability, scalability, and cost control.

---

### Main Objectives

- Design the **S3 → SQS → Lambda** architecture to process images via a queue, preventing Lambda from being overwhelmed by concurrent upload events.
- Write a Lambda function (Python) to:
  - Receive messages from SQS (containing S3 events)
  - Download images from S3
  - Call Amazon Rekognition to detect labels and identify conditions (e.g., damaged packages)
  - Call Amazon Textract to extract text from shipping labels (tracking numbers, route info, phone numbers, etc.)
  - Write results to CloudWatch Logs for observation and testing

### What You Will Learn

  - Why SQS is needed as a "buffer" between S3 and Lambda in high-load systems.
  - How to configure an IAM Role following the Least Privilege principle (granting only the necessary permissions).
  - How to create and configure:
    - An S3 bucket and Event Notification
    - An SQS Standard Queue with important parameters (Visibility Timeout, retention period, etc.)
    - A Lambda Trigger from SQS and how to process individual messages (small batch size for easy observation)
  - The end-to-end Testing & Validation process and how to clean up resources to avoid unnecessary costs.
