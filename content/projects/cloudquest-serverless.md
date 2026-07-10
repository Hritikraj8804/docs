---
title: "CloudQuest Serverless"
date: 2026-05-26
tags: ["AWS Lambda", "Serverless", "DynamoDB", "Terraform", "GitHub Actions"]
description: "A fantasy-themed serverless quest management platform built with AWS Lambda, API Gateway, DynamoDB, Terraform, and GitHub Actions."
source: "https://github.com/Hritikraj8804/cloudquest-serverless"
featured: true
---

## Overview

**CloudQuest Serverless** is a full-stack, fantasy-themed serverless application. It provides a gamified quest management platform built using a modern event-driven serverless architecture on **AWS**. All infrastructure resources are fully declared in **Terraform** and automatically deployed using **GitHub Actions**.

## Key Features

- **⚡ Serverless Backend**: Built using AWS Lambda functions triggered by API Gateway endpoints for a pay-per-request API.
- **💾 NoSQL Storage**: Utilizes Amazon DynamoDB for fast, predictable, and single-digit millisecond latency performance at any scale.
- **🏗️ Automated IaC**: The entire serverless application stack is declared using modular Terraform configurations.
- **🔄 GitOps CI/CD**: Seamless automated deployments using GitHub Actions pipelines that run tests and trigger terraform apply on push.

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **AWS Lambda** | Serverless Compute Engine |
| **Amazon API Gateway** | REST API Routing |
| **Amazon DynamoDB** | NoSQL Database |
| **Terraform** | IaC Automation |
| **GitHub Actions** | CI/CD Pipeline |

## Getting Started

```bash
# Clone the repository
git clone https://github.com/Hritikraj8804/cloudquest-serverless.git
cd cloudquest-serverless

# Install dependencies for local development
npm install

# Test application functions locally
npm test
```

---

*Gamifying quest management with serverless technologies and GitOps workflows.*
