+++
title = "Day 3 - Private EC2 with Security Group"
date = "2026-05-19"
draft = false
weight = 3
+++

## What I did

- Created a new Security Group named `Database-SG`
- Configured inbound rule to allow SSH only from `WebServer-SG`
- Launched a private EC2 instance
- Disabled Auto-assign Public IP
- Verified the instance only received a private IPv4 address
- Learned the difference between public and private EC2 architecture

## Result

Successfully created a private EC2 instance that cannot be accessed directly from the internet.

## Architecture

Internet → Public EC2 (`sg-lab`) → Private EC2 (`private-dbb`)

## Images

![database-sg](/images/database-sg.png)

![disable-public-ip](/images/disable-public-ip.png)

![private-instance](/images/private-instance.png)