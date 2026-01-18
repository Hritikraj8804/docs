---
title: "EduKestra"
date: 2024-11-30
tags: ["Kestra", "GitHub Actions", "Automation", "Workflow"]
description: "Automated study content delivery platform powered by Kestra workflows and GitHub integration"
source: "https://github.com/Hritikraj8804/EduKestra"
---

## Overview

**EduKestra** is a fully automated content delivery platform. It solves the problem of notifying students about new study materials by orchestrating workflows between logical components using **Kestra** and **GitHub**.

## Key Features

- **🔄 Workflow Orchestration**: Kestra manages the entire data flow and notification logic
- **🔔 Smart Notifications**: Automatically notifies subscribers via Email and Telegram
- **📂 Git-as-Database**: Uses GitHub repositories to store subscriber data and content
- **⚡ Event-Driven**: GitHub Actions trigger workflows instantly when content is added

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Kestra** | Workflow Automation |
| **GitHub Actions** | CI/CD Triggers |
| **Telegram API** | Notifications |
| **HTML/CSS** | Frontend |

## How It Works

1. Student subscribes via generic web form
2. Data saved to GitHub repo
3. Admin pushes new study content to repo
4. GitHub Action triggers Kestra
5. Kestra reads subscribers and blasts notifications 🚀
