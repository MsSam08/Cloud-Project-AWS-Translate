
# Serverless Translation Pipeline with AWS Translate and Amazon S3

## Project Overview
This capstone project implements a fully serverless translation pipeline on AWS that automatically translates JSON files uploaded to an S3 bucket. The solution integrates **Amazon S3**, **AWS Lambda**, **Amazon Translate**, and **Amazon Comprehend**, with infrastructure provisioned using **Terraform**. It is designed for scalability, low operational overhead, and operates within AWS Free Tier limits for small-scale testing.

## Features
- Automatic translation of JSON files uploaded to S3.
- Source language detection using Amazon Comprehend.
- Secure storage of original and translated files in S3.
- CloudWatch logging for monitoring and debugging.
- Infrastructure-as-Code (IaC) deployment using Terraform.
- Fully serverless architecture with minimal operational overhead.

## Architecture Overview
1. **Request S3 Bucket** – Stores incoming JSON files.
2. **S3 Event Trigger** – Uploading a file triggers the Lambda function.
3. **Lambda Function** – Reads the JSON, translates text via Amazon Translate, and writes results to the response bucket.
4. **Response S3 Bucket** – Stores translated JSON files.
5. **CloudWatch Logs** – Captures execution logs and errors.
6. **Terraform** – Automates provisioning of S3 buckets, IAM roles, and Lambda function.

## Project Goals
- Automate translation of uploaded JSON files.
- Store original and translated files securely in Amazon S3.
- Ensure scalability and cost-efficiency using serverless architecture.
- Deploy infrastructure reproducibly using Terraform.
- Enforce best practices for IAM, CloudWatch logging, and cost optimization.

## Prerequisites
- AWS Account (Free Tier recommended)
- AWS CLI installed and configured
- Terraform installed
- Python 3.9+ for Lambda function
- Boto3 library

# Phase 1: Initial Setup & AWS Configuration

This phase of the **Serverless Translation Pipeline** project focuses on laying the foundation for the system by setting up AWS resources, configuring tools, and defining permissions.

---

## Key Activities

### 1. Researched AWS Services
- **Amazon Translate**
  - Real-time neural machine translation.
  - Explored supported languages, text size limits (5,000 bytes/request), and Free Tier (2M characters/month for 12 months).
- **Amazon S3**
  - Object storage service with features like versioning, encryption, bucket policies, lifecycle rules, and event notifications for automation.

### 2. IAM Policy with Scoped Access
For secure and minimal permissions, the following IAM policies were drafted for the Lambda function:
- **Amazon Translate**
  - `translate:TranslateText`
- **Amazon S3**
  - `s3:GetObject`
  - `s3:PutObject`
  - `s3:ListBucket`
- **CloudWatch Logs**
  - Permissions to enable Lambda logging
 
### 3. Installed & Configured Required Tools
- **AWS CLI** – for interacting with AWS services locally.
- **Terraform** – for Infrastructure-as-Code provisioning.
- **Python 3.9+** – for developing Lambda functions.

### 4. Configured AWS Credentials
- Set up local credentials using:
```bash
`aws configure`






