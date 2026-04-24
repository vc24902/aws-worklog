+++
title = "Day 3 - VPC"
date = "2026-04-22"
draft = false
+++

## What I did

- Created custom VPC (10.0.0.0/16)
- Created subnets:
  - Public subnet (10.0.1.0/24)
  - Private subnet (10.0.2.0/24)

- Attached Internet Gateway (IGW)

- Configured route tables:
  - Public route → 0.0.0.0/0 → IGW
  - Private route → local only

- Enabled auto-assign public IPv4

## Result

Network architecture successfully configured

## Images

![vpc](/images/vpc-overview.png)
![igw](/images/internet-gateway.png)
![public](/images/public-subnet.png)
![private](/images/private-subnet.png)
![rt1](/images/public-route-table.png)
![rt2](/images/private-route-table.png)