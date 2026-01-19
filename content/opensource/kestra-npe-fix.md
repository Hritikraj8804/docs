---
title: "Fix NPE in SetVariables when variables are null"
date: 2025-12-29
project: "Kestra"
repo: "kestra-io/kestra"
prNumber: "13776"
prLink: "https://github.com/kestra-io/kestra/pull/13776"
status: "merged"
tags: ["Java", "Bug Fix", "Backend"]
description: "Fixed NullPointerException in SetVariables task when execution variables are not initialized for webhook-triggered executions"
---

Fixed a NullPointerException in the `SetVariables` task when `overwrite: false` is used. The task assumed `execution.getVariables()` was non-null and attempted to call `containsKey(...)`, which caused a crash for webhook-triggered executions.

The fix defensively initializes a local variables map before performing duplicate checks and merges, preserving existing behavior while preventing the NPE.
