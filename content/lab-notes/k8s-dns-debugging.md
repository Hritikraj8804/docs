---
title: "Debugging K8s Pod DNS Resolution"
date: 2026-01-15
tags: ["Kubernetes", "DNS", "Troubleshooting"]
---

Spent two hours debugging why pods couldn't resolve external hostnames. The culprit? CoreDNS was crashing due to memory limits.

## Symptoms

```bash
$ kubectl exec -it myapp -- nslookup google.com
;; connection timed out; no servers could be reached
```

## Diagnosis

```bash
# Check CoreDNS pods
$ kubectl get pods -n kube-system -l k8s-app=kube-dns
NAME                       READY   STATUS             RESTARTS
coredns-5d78c9869d-xxxxx   0/1     CrashLoopBackOff   15

# Check logs
$ kubectl logs -n kube-system coredns-5d78c9869d-xxxxx
OOMKilled
```

## Fix

Increased CoreDNS memory limits:

```yaml
resources:
  limits:
    memory: 256Mi  # Was 170Mi
  requests:
    memory: 128Mi
```

## Lesson Learned

Always check `kube-system` pods when networking issues arise. DNS is often the root cause.
