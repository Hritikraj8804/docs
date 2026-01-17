---
title: "Add ARM64 support for controller"
date: 2026-01-08
repo: "kubernetes-sigs/external-dns"
prNumber: "3456"
prLink: "https://github.com/kubernetes-sigs/external-dns/pull/3456"
status: "merged"
tags: ["Kubernetes", "ARM64", "Docker"]
---

Added multi-architecture Docker image builds to support ARM64 deployments (AWS Graviton, Apple Silicon, etc.).

## Changes

- Updated Dockerfile to use multi-arch base images
- Added GitHub Actions workflow for cross-compilation
- Updated documentation with ARM64 installation instructions

```yaml
# .github/workflows/build.yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: docker/setup-qemu-action@v3
      - uses: docker/setup-buildx-action@v3
      - uses: docker/build-push-action@v5
        with:
          platforms: linux/amd64,linux/arm64
          push: true
          tags: ghcr.io/external-dns:latest
```
