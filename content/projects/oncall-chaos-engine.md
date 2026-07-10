---
title: "Oncall Chaos Engine"
date: 2026-03-15
tags: ["Go", "Chaos Engineering", "DevOps", "Kubernetes", "SRE"]
description: "A lightweight, robust chaos engineering engine written in Go to simulate on-call incident failure scenarios and validate alerting pathways."
source: "https://github.com/Hritikraj8804/oncall-chaos-engine"
featured: true
---

## Overview

**Oncall Chaos Engine** is a specialized reliability testing tool built in **Go**. It is designed for Site Reliability Engineers (SREs) and DevOps teams to proactively inject controlled failures—such as network latency, container crashes, and DNS failures—into infrastructure to verify that on-call alerting routing (PagerDuty, Opsgenie, etc.) triggers correctly.

## Key Features

- **💥 Automated Failure Injection**: Programmatically inject failures like high CPU load, memory exhaustion, packet loss, and process termination.
- **🚨 Alert Pathway Validation**: Ensures that alerts are successfully triggered, aggregated, and routed to the on-call engineer within SLAs.
- **🛡️ Safety Rollbacks**: Built-in automatic rollback mechanism to immediately stop failure simulation if critical service levels drop below safety margins.
- **⚡ Native Go Architecture**: Clean, compiled binary with low runtime overhead and seamless system integration.

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Go** | Core Engine Logic |
| **Kubernetes API** | Cluster Failure Injection |
| **Prometheus** | Metric Scraping & Telemetry |
| **Slack / PagerDuty** | Alert Channels Verification |

## Getting Started

```bash
# Clone the repository
git clone https://github.com/Hritikraj8804/oncall-chaos-engine.git
cd oncall-chaos-engine

# Build the binary
go build -o chaos-engine main.go

# Run the failure simulator configuration
./chaos-engine --config config.yaml
```

---

*Proactively verifying system resilience through automated chaos simulation.*
