+++
title = "Day 4 - Network ACL (NACL)"
date = "2026-05-19"
draft = false
weight = 4
+++

## What I did

- Created a custom Network ACL named Web-NACL
- Associated Web-NACL with subnet 172.31.16.0/20
- Configured inbound rules:
  - Allow HTTP (80) from anywhere
  - Allow SSH (22) only from my IP
- Configured outbound rules:
  - Allow all outbound traffic
- Tested web server access from browser successfully

## Result

Successfully configured a custom Network ACL for subnet-level traffic control.

Learned the difference between:

- Security Group (instance-level firewall)
- Network ACL (subnet-level firewall)

Also understood that NACL is stateless, so both inbound and outbound rules are required.

## Images

![web-nacl-create](/images/web-nacl-create.png)

![web-nacl-subnet](/images/web-nacl-subnet.png)

![web-nacl-inbound](/images/web-nacl-inbound.png)

![web-nacl-outbound](/images/web-nacl-outbound.png)

![web-nacl-browser-test](/images/web-nacl-browser-test.png)