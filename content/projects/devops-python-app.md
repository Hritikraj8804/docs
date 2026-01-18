---
title: "DevOps Python App"
date: 2025-08-19
tags: ["Python", "Docker", "GitHub Actions", "CI/CD"]
description: "Application demonstrating DevOps practices with Python, automation, and CI/CD tooling"
source: "https://github.com/Hritikraj8804/devops-python-app"
---

## Overview

**DevOps Python App** serves as a practical demonstration of modern DevOps practices applied to a Python project. It features automated builds, testing, and Docker containerization.

## Key Features

- **🐳 Docker Integration**: Optimized Dockerfile for Python applications
- **🤖 GitHub Actions**: Automated CI/CD workflows
- **📦 Registry Management**: Automated pushing to Docker Hub
- **🧪 Testing**: Integration of unit tests in the build pipeline

## Getting Started

```bash
git clone https://github.com/Hritikraj8804/devops-python-app.git
cd devops-python-app

# Build Docker Image
docker build -t devops-python-app .

# Run Container
docker run -p 5000:5000 devops-python-app
```

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Python** | Application Logic |
| **Docker** | Containerization |
| **GitHub Actions** | Automation |
