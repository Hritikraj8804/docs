---
title: "Terraform AWS Infrastructure"
date: 2026-01-10
tags: ["Terraform", "AWS", "IaC", "VPC"]
description: "Modular Terraform configuration for production AWS infrastructure"
---

## Overview

A collection of reusable Terraform modules for deploying production-grade AWS infrastructure, including VPCs, EKS clusters, RDS databases, and more.

## Module Structure

```
terraform/
├── modules/
│   ├── vpc/
│   ├── eks/
│   ├── rds/
│   └── s3/
├── environments/
│   ├── dev/
│   ├── staging/
│   └── production/
└── main.tf
```

## Usage

### VPC Module

```hcl
module "vpc" {
  source = "./modules/vpc"

  name               = "production-vpc"
  cidr               = "10.0.0.0/16"
  availability_zones = ["us-west-2a", "us-west-2b", "us-west-2c"]
  
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]
  
  enable_nat_gateway = true
  single_nat_gateway = false
  
  tags = {
    Environment = "production"
    Terraform   = "true"
  }
}
```

### EKS Module

```hcl
module "eks" {
  source = "./modules/eks"

  cluster_name    = "production-cluster"
  cluster_version = "1.28"
  
  vpc_id          = module.vpc.vpc_id
  subnet_ids      = module.vpc.private_subnets
  
  node_groups = {
    general = {
      desired_size = 3
      min_size     = 2
      max_size     = 10
      
      instance_types = ["t3.medium"]
      capacity_type  = "ON_DEMAND"
    }
  }
}
```

## State Management

We use S3 + DynamoDB for remote state:

```hcl
terraform {
  backend "s3" {
    bucket         = "terraform-state-prod"
    key            = "infrastructure/terraform.tfstate"
    region         = "us-west-2"
    encrypt        = true
    dynamodb_table = "terraform-locks"
  }
}
```

## Best Practices

1. **Use workspaces** for environment separation
2. **Lock provider versions** to avoid breaking changes
3. **Validate with `terraform plan`** before every apply
4. **Use data sources** instead of hardcoding resource IDs
5. **Enable drift detection** in CI/CD pipelines

## Cost Optimization

| Resource | Monthly Cost | Optimization |
|----------|-------------|--------------|
| NAT Gateway | ~$32/month | Use single NAT for dev |
| EKS Control Plane | $72/month | Consider Fargate for small workloads |
| RDS Multi-AZ | 2x cost | Single-AZ for non-prod |
