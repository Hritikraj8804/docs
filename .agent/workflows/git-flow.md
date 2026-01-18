---
description: Git branching workflow best practices
---

# Git Branching Workflow

## Branch Naming Convention

- `feature/<name>` - New features (e.g., `feature/add-search`)
- `fix/<name>` - Bug fixes (e.g., `fix/sidebar-scroll`)
- `docs/<name>` - Documentation (e.g., `docs/update-readme`)
- `refactor/<name>` - Code improvements (e.g., `refactor/css-cleanup`)

## Workflow Steps

### 1. Create a new branch
// turbo
```bash
git checkout main
git pull origin main
git checkout -b feature/<branch-name>
```

### 2. Make changes and commit
```bash
git add -A
git commit -m "feat: description of changes"
```

**Commit message prefixes:**
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation
- `refactor:` - Code refactoring
- `style:` - Formatting/styling
- `test:` - Adding tests
- `chore:` - Maintenance tasks

### 3. Push branch to remote
```bash
git push -u origin feature/<branch-name>
```

### 4. Create Pull Request
- Go to GitHub repository
- Click "Compare & pull request"
- Add description and request review
- Merge after approval

### 5. Clean up after merge
// turbo
```bash
git checkout main
git pull origin main
git branch -d feature/<branch-name>
```

## Quick Reference

```bash
# See all branches
git branch -a

# Switch to existing branch
git checkout <branch-name>

# Delete local branch
git branch -d <branch-name>

# Delete remote branch
git push origin --delete <branch-name>
```
