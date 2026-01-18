---
title: "My Node DevOps App"
date: 2025-08-19
tags: ["Node.js", "Docker", "GitHub Actions", "CI/CD"]
description: "Reference Node.js application demonstrating containerization and automated deployment pipelines"
source: "https://github.com/Hritikraj8804/my-node-devops-app"
---

## Overview

**My Node DevOps App** serves as a practical demonstration of modern DevOps practices applied to a Node.js ecosystem. It acts as a reference for containerizing web apps and setting up CI/CD workflows.

## Key Features

- **🐳 Dockerization**: Optimized Dockerfile for Node.js (multi-stage builds)
- **🔄 CI/CD**: Automated testing and build pipelines
- **🧪 Testing**: Integration of unit tests in the build process
- **🚀 Deployment**: Ready-to-deploy structure for cloud platforms

## Getting Started

```bash
git clone https://github.com/Hritikraj8804/my-node-devops-app.git
cd my-node-devops-app

# Build Docker Image
docker build -t node-devops-app .

# Run Container
docker run -p 3000:3000 node-devops-app
```

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Node.js** | Runtime |
| **Docker** | Containerization |
| **GitHub Actions** | CI/CD |
