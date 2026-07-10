---
title: "PodEx - AI Kubernetes Workspace"
date: 2026-07-10
tags: ["Kubernetes", "Generative AI", "React", "Python", "FastAPI", "Developer Tools"]
description: "An AI-powered Kubernetes workspace that helps beginners learn, explore, and troubleshoot their local clusters."
source: "https://github.com/Hritikraj8804/podex"
featured: true
---

## Overview

**PodEx** is an AI-powered Kubernetes developer workspace designed to simplify local cluster operations for beginners and seasoned developers alike. By combining a modern web frontend with a fast **Python/FastAPI** backend and integrating a **Generative AI** assistant, PodEx helps users visualize, explore, and troubleshoot resource failures inside their Docker/kind Kubernetes clusters interactively.

## Key Features

- **🤖 AI Troubleshooter**: Ingests cluster event logs and pod diagnostics to identify issues and recommend precise shell commands for remediation.
- **📊 Real-time Visualizer**: Displays a clean, interactive hierarchy of namespaces, deployments, replica sets, and pods.
- **🛠️ One-Click Debugging**: Allows developers to view live pod logs, execute commands inside containers, and mock network failures effortlessly.
- **🐳 Local Native Integration**: Tailored to work out of the box with local container runtimes and Kubernetes configurations like Minikube and kind.

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **React / TypeScript** | Visual Dashboard UI |
| **Python / FastAPI** | High-performance Backend API |
| **Kubernetes Client** | Cluster State Ingestion |
| **Google Gemini API** | Intelligent Diagnostics & Remediation |

## Getting Started

```bash
# Clone the repository
git clone https://github.com/Hritikraj8804/podex.git
cd podex

# Start the Python FastAPI backend
cd backend
pip install -r requirements.txt
python main.py

# In a new terminal, start the React frontend
cd frontend
npm install
npm run dev
```

---

*Demystifying Kubernetes with AI-assisted local cluster diagnostics.*
