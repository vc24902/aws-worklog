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

## Images

### CLI Configuration

![cli-config](/images/cli-config.png)

### IAM Identity Verification

![cli-identity](/images/cli-identity.png)

### Upload File to S3 (Success)

![s3-upload](/images/s3-upload.png)

### List Files in S3 Bucket

![s3-list](/images/s3-list.png)

### IAM Policy (Explicit Deny)

![iam-deny-policy](/images/iam-deny-policy.png)

### Access Denied (After Policy Applied)

![access-denied](/images/access-denied.png)
