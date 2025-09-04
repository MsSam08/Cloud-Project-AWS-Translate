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

## Setup and Deployment

1. **Clone the Repository**
```bash
git clone <repository-url>
cd serverless-translation-pipeline
