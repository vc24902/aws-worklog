+++
title = "Day 4 - AWS CLI & IAM Deny"
date = "2026-04-30"
draft = false
weight = 4
+++

## What I did

* Installed AWS CLI on local machine
* Configured AWS CLI using IAM User (ChienUser)
* Verified identity using AWS STS
* Listed S3 buckets using CLI
* Uploaded file to S3 successfully
* Created IAM policy with explicit Deny (s3:PutObject)
* Attached policy to IAM User
* Tested upload again → AccessDenied

## Commands

```bash
aws configure
aws sts get-caller-identity
aws s3 ls
echo "hello aws cli" > test.txt
aws s3 cp test.txt s3://chien-s3-667802015889-us-east-1-an/
```

## Result

* Successfully authenticated AWS CLI with IAM User
* Verified correct identity using STS
* Demonstrated S3 upload via CLI
* Observed AccessDenied due to explicit deny policy
* Confirmed that Deny overrides Allow in IAM


