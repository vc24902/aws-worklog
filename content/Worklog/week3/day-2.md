+++
title = "Day 2 - Security Group Web Server Rules"
date = "2026-05-05"
draft = false
weight = 2
+++

## What I did

- Created a custom Security Group for EC2
- Allowed SSH access only from my IP
- Allowed HTTP access from the internet
- Attached the new Security Group to EC2 instance
- Tested website access using public IP

## Result

Successfully configured Security Group rules and secured EC2 access.

## Security Rules

| Port | Purpose | Source |
|---|---|---|
| 22 | SSH | My IP |
| 80 | HTTP | 0.0.0.0/0 |

