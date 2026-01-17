---
title: "Terraform State Lock Stuck"
date: 2026-01-05
tags: ["Terraform", "AWS", "DynamoDB"]
---

Got stuck with a Terraform state lock after a CI job was killed mid-apply.

## The Error

```
Error: Error acquiring the state lock

Lock Info:
  ID:        xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
  Path:      s3://bucket/path/terraform.tfstate
  Operation: OperationTypeApply
  Who:       runner@github-actions
```

## The Fix

Force unlock (use with caution!):

```bash
terraform force-unlock xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Or manually delete from DynamoDB:

```bash
aws dynamodb delete-item \
  --table-name terraform-locks \
  --key '{"LockID": {"S": "bucket/path/terraform.tfstate"}}'
```

**Warning:** Only force unlock if you're 100% sure no other process is running!
