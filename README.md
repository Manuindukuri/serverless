# Lambda Function: Triggered by SNS in AWS

[![Python](https://img.shields.io/badge/python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://www.python.org) 
[![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/console)
[![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com)
[![AWS Lambda](https://img.shields.io/badge/aws%20lambda-purple?style=for-the-badge&logo=aws%20lambda&logoColor=white)](https://aws.amazon.com/pm/lambda)
[![AWS SNS](https://img.shields.io/badge/AWS%20SNS-3670A0.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/console)
[![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)](https://code.visualstudio.com)

Serverless computing is used for running applications that require backend services but don't need the complexity and overhead of a full server all the time. It's ideal for workloads that are intermittent or unpredictable, making it a cost-effective and flexible solution for many use cases. In serverless computing, we write code and deploy it to a serverless platform without worrying about the underlying infrastructure. The platform automatically scales the computational resources up or down based on the application's needs.

![image](https://github.com/Manuindukuri/serverless/assets/114769115/07ef404f-cd48-4c0b-a546-f3fe287a004e)

## Overview

This AWS Lambda function downloads a GitHub release archive from a specified repository URL and uploads it to Google Cloud Storage. It also sends email notifications using Mailgun and tracks the email status in AWS DynamoDB. The SNS message includes details such as the GitHub repository URL, user information, and assignment details.

## Functionality

1. **Download Release:** Downloads a GitHub release archive using the provided repository URL.
2. **Upload to GCS:** Uploads the downloaded file to Google Cloud Storage (GCS).
3. **Email Notification:** Sends an email notification about the download status using Mailgun.
4. **Email Tracking:** Tracks the sent emails in AWS DynamoDB.

## Configuration

Before deploying the Lambda function, ensure you have configured the following environment variables:

- **GCS_BUCKET_NAME:** Name of the Google Cloud Storage bucket.
- **GCP_CREDENTIALS:** Base64-encoded JSON credentials for GCP service account.
- **MAILGUN_API_KEY:** API key for Mailgun.
- **MAILGUN_DOMAIN:** Domain associated with your Mailgun account.
- **MAILGUN_SENDER:** Sender email address for Mailgun.
- **DYNAMODB_TABLE:** Name of the DynamoDB table for tracking emails.
- **AWS_REG:** AWS region for DynamoDB.

## How to Use

1. **Deploy the Lambda Function:**
   - Deploy the Lambda function using the provided code.
   - Subscribe the Lambda function to the appropriate SNS topic.

2. **Send SNS Event:**
   - Send an SNS event with details about the GitHub repository using the provided schema.

3. **Monitor Logs:**
   - Monitor the CloudWatch Logs for the Lambda function to view execution logs.
