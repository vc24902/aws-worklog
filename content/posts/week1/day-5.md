+++
title = "Day 5 - IAM Role & AWS CLI"
date = "2026-04-24"
draft = false
weight = 5
+++

## What I did

- Created IAM Role for EC2
- Attached AmazonS3ReadOnlyAccess policy
- Attached role to EC2
- Connected via SSH
- Tested AWS CLI

## Commands

## Result

- Successfully listed S3 buckets
- Upload failed due to missing permission

## CLI Lab Summary

- CLI is a tool used to interact with AWS services
- IAM Role provides permissions for EC2
- Permissions control access (allow/deny)
- AccessDenied occurs when permission is missing

## Images

![identity](/images/cli-identity.png)
![s3](/images/cli-s3-list.png)
![error](/images/cli-access-denied.png)