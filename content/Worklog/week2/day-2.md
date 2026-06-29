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
