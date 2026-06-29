+++
title = "Day 6 - Route Table and Public/Private Subnet"
date = "2026-05-09"
draft = false
weight = 6
+++

# Day 6 - Route Table and Public/Private Subnet

## Objective

Learn how AWS networking controls internet access using:

- Subnets
- Route Tables
- Internet Gateway
- Public and Private architecture

---

## Architecture

Internet  
↓  
Internet Gateway  
↓  
Public Route Table  
↓  
Public Subnet  
↓  
Public EC2

-------------------------

Private Route Table  
↓  
Private Subnet  
↓  
Private EC2

---

## What I Did

### 1. Created Public Subnet



Created subnet:

- Name: `public-subnet`
- CIDR: `172.31.240.0/24`

Purpose:  
Used for public resources that require internet access.

Examples:

- Bastion Host
- Web Server
- Load Balancer

---

### 2. Created Private Subnet



Created subnet:

- Name: `private-subnet`
- CIDR: `172.31.241.0/24`

Purpose:  
Used for internal resources that should not be publicly accessible.

Examples:

- Backend API
- Database
- Internal Services

---

### 3. Created Public Route Table


Created `Public-RT`.

Added route:

| Destination | Target |
|---|---|
| 0.0.0.0/0 | Internet Gateway |

Purpose:  
Allow internet traffic through the Internet Gateway.

---

### 4. Associated Public Subnet



Associated:

- `public-subnet`
- → `Public-RT`

Result:

EC2 instances inside `public-subnet` can access the internet.

---

### 5. Created Private Route Table



Created `Private-RT`.

Only local route exists:

| Destination | Target |
|---|---|
| 172.31.0.0/16 | local |

Purpose:  
Keep private subnet isolated from direct internet access.

---

### 6. Associated Private Subnet



Associated:

- `private-subnet`
- → `Private-RT`

Result:

EC2 instances inside `private-subnet` do not have internet routing.

---

## Key Concepts Learned

- VPC Networking
- CIDR Block
- Public Subnet
- Private Subnet
- Route Table
- Internet Gateway
- Routing
- Network Isolation
- Public vs Private Architecture

---

## Important Understanding

A subnet becomes:

- Public → if its Route Table contains:
  
```text
0.0.0.0/0 → Internet Gateway
```

- Private → if it does NOT contain internet routing.

The Route Table determines whether a subnet has internet access.

---

## Result

Successfully built:

- Public subnet with internet access
- Private subnet without internet access
- Public and private routing architecture

This is the foundation of real-world AWS production networking.