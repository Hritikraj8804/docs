---
title: "Docker Multi-Stage Builds"
date: 2026-01-05
tags: ["Docker", "Go", "Optimization"]
description: "Reducing Docker image sizes from 1.2GB to 12MB with multi-stage builds"
---

## The Problem

Our Go application's Docker image was 1.2GB. Deploying it was slow, and storage costs were adding up.

## The Solution

Multi-stage builds let us separate the build environment from the runtime environment.

### Before (1.2GB)

```dockerfile
FROM golang:1.21
WORKDIR /app
COPY . .
RUN go build -o main .
CMD ["./main"]
```

### After (12MB)

```dockerfile
# Build stage
FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w" -o main .

# Runtime stage
FROM scratch
COPY --from=builder /app/main /main
COPY --from=builder /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/
ENTRYPOINT ["/main"]
```

## Key Techniques

1. **Alpine base image** - Much smaller than Debian
2. **Scratch final image** - No OS, just the binary
3. **Static linking** - `CGO_ENABLED=0`
4. **Strip debug symbols** - `-ldflags="-s -w"`

## Results

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Image Size | 1.2GB | 12MB | 99% smaller |
| Pull Time | 45s | 2s | 95% faster |
| Storage Cost | $15/mo | $0.15/mo | 99% cheaper |
