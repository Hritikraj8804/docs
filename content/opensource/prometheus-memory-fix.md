---
title: "Fix memory leak in metrics collector"
date: 2026-01-12
repo: "prometheus/prometheus"
prNumber: "12345"
prLink: "https://github.com/prometheus/prometheus/pull/12345"
status: "merged"
tags: ["Go", "Prometheus", "Performance"]
---

Fixed a memory leak in the TSDB metrics collector that occurred when scrape targets were frequently added and removed. The issue was caused by unbounded growth of the target metadata cache.

## The Problem

When running Prometheus with dynamic service discovery (Kubernetes, Consul, etc.), frequently changing targets caused the metadata cache to grow indefinitely.

## The Fix

Implemented an LRU cache with configurable size limits and proper cleanup on target removal.

```go
type MetadataCache struct {
    cache *lru.Cache
    mu    sync.RWMutex
}

func (c *MetadataCache) Set(target string, meta Metadata) {
    c.mu.Lock()
    defer c.mu.Unlock()
    c.cache.Add(target, meta)
}
```
