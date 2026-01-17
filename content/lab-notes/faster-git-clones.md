---
title: "Quick Tip: Faster Git Clones"
date: 2026-01-10
tags: ["Git", "Performance"]
---

When cloning large repos in CI/CD, use shallow clones to save time:

```bash
# Instead of full clone
git clone https://github.com/org/huge-repo.git

# Use shallow clone
git clone --depth 1 https://github.com/org/huge-repo.git

# Or for a specific branch
git clone --depth 1 --branch main https://github.com/org/huge-repo.git
```

**Result:** Reduced clone time from 3 minutes to 15 seconds for our monorepo.

For GitHub Actions:

```yaml
- uses: actions/checkout@v4
  with:
    fetch-depth: 1  # Shallow clone
```
