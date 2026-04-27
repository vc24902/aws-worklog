+++
title = "Day 1 - S3 Policy"
date = "2026-04-27"
draft = false
weight = 1
+++

## What I did

- Created S3 bucket
- Uploaded index.html
- Tested access (default private → Access Denied)
- Disabled Block Public Access
- Added bucket policy (public read)
- Tested public access → success

## Result

- S3 is private by default
- Bucket Policy controls access
- Block Public Access affects public access behavior

## Images

![s3-denied](/images/s3-denied.png)
![s3-block](/images/s3-block.png)
![s3-public](/images/s3-public.png)