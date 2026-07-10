---
title: "PART 2: PROPOSAL"
menuTitle: "Proposal"
date: 2026-07-24
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# AUTOMATED CARGO QUALITY MONITORING SOLUTION BASED ON SERVERLESS AND AI/ML

### Executive Summary

In the logistics industry, enterprises face heavy pressures regarding processing speed, data accuracy, and loss control. Currently, cargo quality monitoring in warehouses heavily depends on manual human inspection, leading to slow incident response, fragmented data, and an inability to track updates in real time.

We propose developing the **"Automated Cargo Quality Monitoring Solution Based on Serverless Architecture and Artificial Intelligence (AI/ML)"**. This software application utilizes Amazon Web Services (AWS) to allow delivery personnel or customers to take photos of damaged parcels (torn, broken, dented, or deformed) and upload them directly to the system for automated analysis.

The system employs AI/ML to detect damage levels, extract shipping label information, store visual proof, and send alerts to relevant departments. Consequently, incident processing times are reduced from hours or days to mere seconds, while lowering operational costs, minimizing manual errors, and improving overall service quality.

---

### Problem Statement

#### Current Challenges

According to field assessments, the current process of recording and handling damaged goods faces several operational bottlenecks:

- **Manual, Time-Consuming, and Error-Prone Process:** When damaged cargo is detected, staff typically take photos using personal phones, send them via chat groups, or fill out paper reports. The verification department must then gather these scattered pieces of information to manually enter them into the ERP system and initiate compensation claims. This process is slow and prone to data confusion.

- **Lack of Automation and Immediate Alerts:** Without automated image analysis and label extraction software, warehouse managers are not alerted immediately to damage severity, delaying critical operational decisions. Slow feedback loops degrade customer experience and service reputation.

- **Limited System Scalability:** Peak seasons experience a sharp surge in cargo volume. Manual inspection processes cannot handle numerous packages concurrently, resulting in bottlenecks, overlooked damaged items, or defective items being delivered to consumers.

- **Fragmented and Difficult-to-Access Storage:** Incident files are scattered across physical logbooks, Excel spreadsheets, and messaging groups. Compiling monthly/quarterly loss ratios for executive reports requires manual consolidation, which is inefficient and inaccurate.

- **High Operational Costs:** Companies must maintain specialized personnel at warehouse checkpoints for inspection, manual data entry, and dispute handling. Along with labor costs, data entry errors and prolonged claims settlements erode logistics profit margins and reputation.

---

### Proposed Solution

We propose building an automated cargo quality monitoring solution leveraging Serverless architecture and AI/ML, focusing on these core capabilities:

- **Intelligent AI Automation:** The system uses Amazon Rekognition to analyze cargo images and identify damage signs. Analysis results include condition labels, damage severity, and confidence scores. Amazon Textract is utilized to automatically extract tracking numbers, addresses, and related text from shipping labels without manual entry.

- **Real-Time Asynchronous Processing:** Uploading images to Amazon S3 triggers an automated processing pipeline. Visual data, tracking numbers, and analytical results are synchronized to Amazon DynamoDB for querying, auditing, and report generation. This reduces response cycles from days to seconds.

- **Auto-Scaling Serverless Infrastructure:** Built entirely on AWS Serverless services, the system scales automatically during peak traffic without manual server management while maintaining high concurrency.

- **Centralized and Transparent Data Management:** All scan histories, visual evidence, tracking numbers, and processing statuses are stored in a centralized repository. Managers can look up records anytime, verify evidence, and export damage statistical reports.

- **Operational Cost Optimization:** Integrating AI reduces manual data entry errors, optimizes labor requirements at warehouses, shortens claim dispute resolution times, and improves reliability in compensation workflows.

---

### Solution Architecture

#### High-Level Architecture
![Serverless and AI/ML Solution Architecture](/images/DiagramStructure.png)

The system adopts an event-driven architecture utilizing AWS services to scale automatically with actual traffic. The complete lifecycle of a cargo monitoring request is divided into four primary layers:

| Architectural Layer | Role | Proposed AWS Services |
| --- | --- | --- |
| Frontend & Auth | Provides the web interface, manages login/registration, issues JWT Tokens, and secures API access | AWS Amplify, Amazon Cognito, Amazon API Gateway |
| Storage | Receives and stores damaged cargo images uploaded by users | Amazon S3 |
| Backend & AI/ML | Processes upload events, analyzes images, extracts shipping details, evaluates damage severity, and updates databases | Amazon SQS, AWS Lambda, Amazon Rekognition, Amazon Textract, Amazon DynamoDB |
| Monitoring & Security | Tracks system performance, manages logs, and enforces least privilege access control | Amazon CloudWatch, AWS IAM |

#### Main Processing Flow

| Step | Description |
| --- | --- |
| 1 | Users log in via the web application hosted on AWS Amplify and authenticated by Amazon Cognito. |
| 2 | Users upload photos of damaged cargo. Images are stored in the Amazon S3 Raw Image Bucket. |
| 3 | S3 Event Notifications trigger upon successful upload and send processing records to Amazon SQS. |
| 4 | The orchestrator Lambda function polls SQS events, invokes Amazon Rekognition to detect damage, and calls Amazon Textract to read tracking numbers/text. |
| 5 | The evaluator Lambda function assesses damage severity based on AI/ML outputs and determines processing status. |
| 6 | The processor Lambda function writes results to Amazon DynamoDB, updates record statuses, and triggers alerts if necessary. |
| 7 | Amazon SNS sends Email/SMS notifications to warehouse managers or handling teams upon detecting critical damage. |
| 8 | Amazon CloudWatch captures execution logs and metrics to monitor operational health. |

---

### AWS Services Utilized

#### Frontend & Auth

- **AWS Amplify:** Hosts and delivers the frontend web application.
- **Amazon Cognito:** Handles user authentication, registration, and JWT issuance.
- **Amazon API Gateway:** Exposes API endpoints, validates authorization tokens, and proxies requests to the backend.

#### Storage

- **Amazon S3:** Stores original cargo images as the primary data ingestion point.

#### Backend Serverless & AI/ML

- **Amazon SQS:** Acts as an asynchronous message buffer to decouple components and absorb burst traffic.
- **AWS Lambda orchestrator-function:** Reads SQS events and coordinates AI/ML analysis tasks.
- **Amazon Rekognition:** Analyzes images to detect cargo condition and damage signs.
- **Amazon Textract:** Extracts printed text, shipping labels, and tracking numbers from images.
- **AWS Lambda evaluator-function:** Evaluates damage severity and categorizes processing statuses.
- **AWS Lambda processor-function:** Saves results, updates records, and triggers downstream actions.
- **Amazon DynamoDB:** Stores scan results, processing history, package statuses, and reporting data.
- **Amazon SNS:** Dispatches Email/SMS alerts to stakeholders.

#### Monitoring & Security

- **Amazon CloudWatch:** Monitors execution logs, system metrics, alarms, and performance.
- **AWS IAM:** Enforces least privilege permissions across all AWS resources.

---

### Risk Assessment

| Risk | Impact | Mitigation Strategy |
| --- | --- | --- |
| Poor Input Image Quality | AI may misclassify or fail to extract tracking numbers | Provide guidelines for taking clear, well-lit photos; validate image format and size on the frontend before upload |
| Ambiguous AI/ML Analysis Results | May misclassify damage severity levels | Allow manual verification by warehouse managers for cases with low confidence scores |
| High Traffic Spikes During Peak Seasons | System latency could increase if queues backlog | Use SQS for traffic buffering, Lambda auto-scaling, and CloudWatch alarms to monitor queue depth |
| Sensitive Data Leakage | Potential exposure of customer shipping information | Apply Cognito authentication, IAM least privilege, S3 bucket policies, and encryption at rest/in transit |
| Excessive Processing Costs at High Volume | May impact operational cloud budget | Monitor usage via CloudWatch, set AWS Budgets alerts, and optimize image dimensions before inference |

---

### Expected Outcomes

- Reduce incident recording and processing times from hours/days to seconds.
- Automatically detect cargo damage via AI, minimizing reliance on manual visual inspection.
- Automatically extract tracking numbers and shipping details, eliminating data entry errors.
- Centralize incident records, visual proof, and processing statuses in a unified platform.
- Enable warehouse managers to search histories, analyze loss statistics, and export reports efficiently.
- Ensure high scalability during peak logistics seasons via Serverless architecture.
- Optimize labor costs, shorten dispute resolutions, and enhance logistics service reputation.

---

### Conclusion

The Automated Cargo Quality Monitoring Solution based on Serverless and AI/ML enables logistics enterprises to transition from manual, fragmented workflows to an automated, centralized, and highly scalable system. Combining Amazon S3, SQS, Lambda, Rekognition, Textract, DynamoDB, SNS, CloudWatch, and IAM creates an optimal architecture for real-time visual inspection while optimizing operational costs and elevating customer service quality.

---

# Operational Cost Estimation on AWS

### Executive Summary

This document estimates the AWS operational costs for the Cargo Damage Detection and Processing System based on a serverless architecture utilizing Amplify, Cognito, API Gateway, S3, SQS, Lambda, Rekognition, Textract, DynamoDB, SNS, CloudWatch, and IAM.

The estimation covers a 1-week testing/production pilot scenario involving ~245 processed images and ~30 active users. Under these assumptions, the actual out-of-pocket cost for a newly created AWS account is **$0.00 USD**, as all usage falls well within applicable AWS Free Tier limits. Calculated at standard On-Demand pricing without Free Tier benefits, the total weekly cost is approximately **$1.57 USD**.

---

### 1. Architectural Overview

The serverless AWS solution detects and handles damaged parcels in warehouses. Users access the web app hosted on AWS Amplify, authenticate via Amazon Cognito to receive JWTs, and call REST APIs via Amazon API Gateway to upload images to Amazon S3.

Upon upload, S3 publishes event notifications to Amazon SQS to buffer incoming load. SQS triggers an AWS Lambda pipeline that coordinates image processing, invokes Amazon Rekognition for damage detection, calls Amazon Textract to read shipping labels, stores structured records in Amazon DynamoDB, and dispatches Amazon SNS alerts when damage is detected with high confidence.

The entire system is monitored by Amazon CloudWatch and secured with least-privilege IAM policies. This estimate covers 12 AWS services over a 1-week operational period.

---

### 2. Usage Assumptions

The following baseline assumptions form the foundation of our calculation:

- Processed image volume: ~35 images/day × 7 days = 245 images/week.
- Active users: ~30 staff/customers accessing the web application.
- AWS Account status: New account within the 12-month AWS Free Tier period.
- Pricing Region: US East (N. Virginia).

---

### 3. Weekly Cost Estimation Breakdown by Service

| AWS Service | Estimated Weekly Usage | Reference Unit Price (US East, N. Virginia) | Standard On-Demand Cost (No Free Tier) | Applicable AWS Free Tier Allowance | Actual Estimated Cost (New Account, Free Tier) |
| --- | --- | --- | --- | --- | --- |
| AWS Amplify (Web Hosting) | ~5 builds, ~0.5 GB CDN storage, ~0.5 GB data transfer for ~30 users | $0.01/build min, $0.023/GB-month, $0.15/GB transfer | ≈ $0.23 | 1,000 build mins + 5 GB storage + 15 GB transfer/month (first 12 months) | $0.00 |
| Amazon Cognito (Authentication) | ~30 Monthly Active Users (MAU) | $0.015/MAU | ≈ $0.45 | 10,000 MAUs/month | $0.00 |
| Amazon API Gateway (REST API) | ~1,800 API calls | $3.50 per 1 million calls | ≈ $0.006 | 1,000,000 calls/month (first 12 months) | $0.00 |
| Amazon S3 (Raw Image Bucket) | 245 PUTs + 245 GETs, ~0.5 GB storage | $0.005/1,000 PUTs, $0.0004/1,000 GETs, $0.023/GB-month | ≈ $0.004 | 2,000 PUTs + 20,000 GETs + 5 GB storage/month | $0.00 |
| Amazon SQS (Message Queue) | ~735 requests | $0.40 per 1 million requests | ≈ $0.0003 | 1,000,000 requests/month | $0.00 |
| AWS Lambda (3 Functions) | ~800 invocations, ~800 GB-seconds | $0.20 per 1 million invocations + $0.0000166667/GB-s | ≈ $0.013 | 1,000,000 invocations + 400,000 GB-seconds/month | $0.00 |
| Amazon Rekognition (Damage Detection) | 245 processed images | $0.001/image | ≈ $0.245 | 5,000 images/month (first 12 months) | $0.00 |
| Amazon Textract (Label OCR) | 245 pages | $0.0015/page | ≈ $0.368 | 1,000 pages/month (first 3 months) | $0.00 |
| Amazon DynamoDB (Database) | 245 writes + 300 reads | $0.625/1M WRUs, $0.125/1M RRUs | ≈ $0.0002 | 25 WCU/RCU + 25 GB storage/month | $0.00 |
| Amazon SNS (Alerting) | ~25 email alerts | $2.00 per 100,000 sent emails | ≈ $0.0005 | 1,000 emails/month (first 12 months) | $0.00 |
| Amazon CloudWatch (Monitoring) | ~30 MB logs, 3-5 metrics, 3-5 alarms | $0.50/GB log, $0.30/metric-month, $0.10/alarm-month | ≈ $0.10 – $0,40 | 5 GB logs + 10 metrics + 10 alarms/month | $0.00 |
| AWS IAM (Least Privilege Security) | Unlimited usage | Free | $0.00 | Always Free | $0.00 |

---

### 4. Cost Summary

**Total Standard Cost (without Free Tier):** ≈ **$1.57 USD**

**Actual Estimated Out-of-Pocket Cost (with Free Tier):** **$0.00 USD**

These figures illustrate two viewpoints:

- Standard billing cost if Free Tier were inapplicable.
- Actual billed amount during the pilot week ($0.00 due to full Free Tier coverage).

---

### 5. Scaling and Post-Free Tier Projection

If operated continuously over a full month, most service usage remains within Free Tier thresholds. The primary service to monitor closely is Amazon Textract, as its Free Tier allowance lasts for the first 3 months. However, at the current operational scale, the total monthly AWS bill remains negligible even after Free Tier expiration.

---

### 6. Limitations and Recommendations

- Estimations are based on projected workload traffic rather than historical billing exports.
- Actual costs should be monitored actively via AWS Cost Explorer once production traffic begins.
- Pricing references correspond to the US East (N. Virginia) region; pricing in other regions may vary slightly.
- Excludes external expenses such as AWS Support Plans, custom domain names, Route 53, WAF, or operational labor.

---

### 7. References

- AWS Lambda Pricing: https://aws.amazon.com/lambda/pricing/
- Amazon API Gateway Pricing: https://aws.amazon.com/api-gateway/pricing/
- Amazon S3 Pricing: https://aws.amazon.com/s3/pricing/
- Amazon SQS Pricing: https://aws.amazon.com/sqs/pricing/
- Amazon Rekognition Pricing: https://aws.amazon.com/rekognition/pricing/
- Amazon Textract Pricing: https://aws.amazon.com/textract/pricing/
- Amazon DynamoDB Pricing: https://aws.amazon.com/dynamodb/pricing/on-demand
- Amazon SNS Pricing: https://aws.amazon.com/sns/pricing/
- Amazon Cognito Pricing: https://aws.amazon.com/cognito/pricing/
- Amazon CloudWatch Pricing: https://aws.amazon.com/cloudwatch/pricing/
- AWS Amplify Pricing: https://aws.amazon.com/amplify/pricing/
- AWS Free Tier: https://aws.amazon.com/free/
