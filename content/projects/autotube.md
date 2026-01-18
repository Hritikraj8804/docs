---
title: "AutoTube"
date: 2025-12-10
tags: ["Python", "n8n", "AI", "Docker", "YouTube API"]
description: "Automated YouTube Shorts factory powered by AI agents, n8n workflows, and Docker"
source: "https://github.com/Hritikraj8804/Autotube"
---

## Overview

**AutoTube** is an end-to-end automated YouTube Shorts factory. It combines AI agents (Ollama/LLaMA), n8n workflows, and Python automation to generate scripts, create visuals, synthesize voiceovers, and upload finished videos directly to YouTube.

## Key Features

- **🎬 End-to-End Automation**: From topic to published video, fully automated
- **🧠 AI Scripting**: Uses Ollama/LLaMA for engaging script writing
- **🎨 AI Visuals**: Generates dynamic image slideshows using Pollinations.ai/Z-Image
- **🎞️ Professional Editing**: Automated Ken Burns effects, transitions, and overlays
- **🔄 Visual Workflow**: Orchestrated via n8n with error handling and monitoring
- **🐳 Dockerized**: Fully containerized microservices architecture

## Project Architecture

1. **Orchestration**: n8n manages the workflow state and triggers
2. **AI Layer**: Ollama (Script), OpenTTS (Voice), Pollinations.ai (Images)
3. **Video Engine**: Python service for composition and rendering
4. **Integration**: YouTube Data API v3 for upload and metadata

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Python** | Video generation & Logic |
| **n8n** | Workflow Orchestration |
| **Ollama** | Local LLM inference |
| **Docker** | Containerization |
| **PostgreSQL** | State management |

## Getting Started

```bash
# Clone the repository
git clone https://github.com/Hritikraj8804/Autotube.git
cd Autotube/short_automation

# Configure Environment
cp .env.example .env
# Set N8N_BASIC_AUTH_USER, POSTGRES_PASSWORD, etc.

# Start Services
docker-compose up -d

# Access n8n Dashboard
# Navigate to http://localhost:5678
```

---

*A powerful demonstration of agentic AI workflows and media automation.*
