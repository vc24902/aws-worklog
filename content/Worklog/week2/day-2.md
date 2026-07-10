+++
title = "Day 2 - IAM Role"
date = "2026-04-28"
draft = false
weight = 2
+++

## What I did
- Created IAM Role for EC2
- Attached AmazonS3ReadOnlyAccess policy
- Launched EC2 with IAM Role
- Connected to EC2 using browser SSH
- Tested S3 access using AWS CLI

## Commands

```bash
aws s3 ls
## Result

- Successfully attached the IAM Role to the EC2 instance.
- Verified that the EC2 instance could access Amazon S3 using the assigned IAM Role.
- Successfully listed S3 buckets using AWS CLI.
- Confirmed that no AWS access keys were required when using IAM Role.