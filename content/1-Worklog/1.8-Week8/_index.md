---
title: "Week 8: AWS Amplify and Frontend UI Construction (22/06/2026 - 26/06/2026)"
menuTitle: "Week 8"
date: 2026-07-24
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

**Week 8 Objectives:**

- Learn about AWS Amplify Hosting and begin building the web interface for the monitoring system.
- Build a login page and image upload feature integrated with Cognito and S3.

**Tasks completed this week:**

| Day | Task | Start Date | Completion Date | Reference |
|-----|------|------------|-----------------|-----------|
| Mon | Study AWS Amplify Hosting: CI/CD pipeline, custom domain, build settings. Compare Amplify Hosting with S3 Static Website Hosting. | 22/06/2026 | 22/06/2026 | https://docs.aws.amazon.com/amplify/ |
| Tue | Study Amplify UI Components for React/Next.js: Authenticator component integrated with Cognito, Storage component for uploading images to S3. | 23/06/2026 | 23/06/2026 | https://ui.docs.amplify.aws/ |
| Wed | Practice creating a basic Next.js web application. Integrate Amplify with the Cognito User Pool. Build a login/logout page. | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/vi/ |
| Thu | Build the image upload page: Call the API to get an S3 presigned URL, upload the image directly to S3 from the frontend, display the upload status. | 25/06/2026 | 25/06/2026 | https://docs.amplify.aws/ |
| Fri | Test the complete upload flow: Log in via Cognito → Get presigned URL → Upload image → SQS → Lambda processing. | 26/06/2026 | 26/06/2026 | |

**Week 8 Results:**

- Understood AWS Amplify Hosting and its CI/CD pipeline for frontend web applications.
- Successfully built a Next.js application with Cognito integration (login/logout).
- Successfully deployed an image upload page using S3 presigned URLs.
- Successfully tested the complete flow from the user interface all the way to AI analysis.
