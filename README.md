# AWS Cloud Project — Static Website Deployment

## Overview
A fully cloud-hosted static website deployed on AWS, demonstrating core cloud infrastructure skills including S3, CloudFront CDN, IAM, and optional infrastructure-as-code via Terraform.

## Problem
Modern businesses need fast, scalable, and cost-efficient web hosting. Understanding how to deploy and manage cloud infrastructure is a foundational skill for any cloud or tech role.

## Solution
I designed and deployed a static website using AWS services, following cloud architecture best practices for security, performance, and scalability.

## Architecture

```
User → CloudFront (CDN) → S3 Bucket (Static Files)
                ↑
           IAM Role (least-privilege access)
```

## Tech Stack
- AWS S3 (static file hosting)
- AWS CloudFront (CDN + HTTPS)
- AWS IAM (access management)
- Optional: Terraform (infrastructure as code)

## Features
- HTTPS enabled via CloudFront
- S3 bucket policy configured for secure public access
- IAM roles following least-privilege principle
- Optional Terraform `.tf` files for reproducible deployment

## Deployment Steps
```bash
# 1. Create S3 bucket (replace with your bucket name)
aws s3 mb s3://hermon-portfolio-site

# 2. Enable static website hosting
aws s3 website s3://hermon-portfolio-site --index-document index.html

# 3. Upload files
aws s3 sync ./website s3://hermon-portfolio-site

# 4. Create CloudFront distribution (see cloudfront-config.json)
```

## Screenshots
*(Add AWS console screenshots: S3 bucket, CloudFront distribution, live URL)*

## Key Learnings
- How S3 bucket policies control public vs private access
- How CloudFront reduces latency by caching at edge locations
- Why IAM roles matter for production security

## Next Steps
- Add a custom domain via Route 53
- Set up CI/CD pipeline with GitHub Actions to auto-deploy on push
- Migrate to serverless backend with AWS Lambda + API Gateway
