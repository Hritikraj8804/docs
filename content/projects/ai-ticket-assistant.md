---
title: "AI Ticket Assistant"
date: 2025-06-28
tags: ["MERN Stack", "Generative AI", "Google Gemini", "TailwindCSS"]
description: "Smart support ticket system powered by Google Gemini AI for automated triage and skill matching"
source: "https://github.com/Hritikraj8804/AI-ticket-assistant"
---

## Overview

**AI Ticket Assistant** is a modern MERN stack application that leverages **Google Gemini AI** to revolutionize help desk operations. It automates ticket analysis, categorization, and assigns tickets based on agent skills.

## Key Features

- **🤖 AI-Powered Triage**: Uses Google Gemini to analyze ticket content and sentiment
- **👥 Smart Assignment**: Matches tickets to agents based on normalized skills
- **📊 Admin Dashboard**: Comprehensive analytics and user management
- **🔄 Background Processing**: Heavy AI tasks handled asynchronously via **Inngest**
- **🔔 Notifications**: Automated email alerts using Nodemailer

## Project Architecture

1. **Frontend**: React + Vite + TailwindCSS (DaisyUI)
2. **Backend**: Express.js REST API
3. **Database**: MongoDB for persistent storage
4. **AI Layer**: Google Gemini API via Inngest background jobs

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Google Gemini** | AI Intelligence |
| **React** | Frontend UI |
| **Node.js/Express** | Backend API |
| **MongoDB** | Database |
| **Inngest** | Background Jobs |

## Getting Started

```bash
# Clone
git clone https://github.com/Hritikraj8804/AI-ticket-assistant.git

# Backend Setup
cd backend
npm install
# Set GEMINI_API_KEY in .env

# Frontend Setup
cd frontend
npm install

# Run (requires 4 terminals)
# 1. Mongo, 2. Inngest, 3. Backend, 4. Frontend
```

---

*Automating support workflows with the power of Generative AI.*
