---
title: "KillMyPod"
date: 2026-03-25
tags: ["Kubernetes", "Chaos Testing", "Docker", "Web UI", "DevOps"]
description: "A lightweight web interface designed to simulate Kubernetes pod failures and test self-healing cluster behavior."
source: "https://github.com/Hritikraj8804/KillMyPod"
featured: false
---

## Overview

**KillMyPod** is an interactive, web-based chaos testing dashboard. It gives developers a visual way to manually kill pods inside their Kubernetes clusters to observe replica scaling, pod restart behavior, and traffic routing resilience in real-time.

## Key Features

- **🎯 Simple Interface**: Displays pods in a dashboard grid, allowing users to "terminate" a pod with a single click.
- **🔄 Visual Self-Healing**: Watch how the replica set automatically spins up a new pod in real-time to replace the killed one.
- **📈 Cluster Health Metrics**: Visual indicators for cluster namespaces, pending terminations, and node resources.

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML / CSS** | Client Web Dashboard |
| **Node.js** | Backend API serving Kubernetes endpoints |
| **Kubernetes API** | Cluster Pod deletion execution |

---

*Visual chaos testing to prove Kubernetes self-healing behaviors.*
