+++
title = "Day 7 - Mini Enterprise Network Project"
date = "2026-05-20"
draft = false
weight = 7
+++

# Day 7 - Mini Enterprise Network Project

## Objective

Build a mini enterprise-style AWS architecture using:

- Public Subnet
- Private Subnet
- Route Tables
- Bastion Host
- Security Groups
- Private Networking

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
Bastion / Web Server  
↓  
Private Subnet  
↓  
Private App Server

---

## What I Did

### 1. Created Bastion Security Group

![bastion-sg](/images/bastion-sgg.png)

Created `Bastion-SG` with:

| Type | Source |
|---|---|
| SSH | My IP |
| HTTP | 0.0.0.0/0 |

Purpose:

- Allow SSH access from my laptop
- Allow public web access from the internet

---

### 2. Created Private Security Group

![private-sg](/images/private-sgg.png)

Created `Private-SG` with:

| Type | Source |
|---|---|
| SSH | Bastion-SG |

Purpose:

Allow SSH access only from the Bastion Host.

---

### 3. Launched Public Bastion/Web Server

![bastion-web](/images/bastion-web.png)

Created EC2 instance:

- Name: `bastion-web`
- Subnet: `public-subnet`
- Public IP: Enabled
- Security Group: `Bastion-SG`

Purpose:

This instance acts as:

- Bastion Host
- Public Web Server

---

### 4. Configured Apache Web Server

![web-browser-test](/images/web-browser-testt.png)

Used EC2 User Data to automatically install Apache.

```bash
#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd
echo "PUBLIC WEB SERVER" > /var/www/html/index.html
```

Result:

Successfully accessed the web server from browser using the Public IP.

---

### 5. Launched Private App Server

![private-app](/images/private-app.png)

Created EC2 instance:

- Name: `private-app`
- Subnet: `private-subnet`
- Public IP: Disabled
- Security Group: `Private-SG`

Purpose:

Create an internal server isolated from the public internet.

---

## Testing Architecture

### 6. Direct SSH To Private Server Failed

![private-timeout](/images/private-timeout.png)

Tested:

```bash
ssh -i new-key.pem ec2-user@172.31.241.248
```

Result:

```text
Connection timed out
```

Meaning:

- Private subnet has no internet route
- Private EC2 has no public IP
- Internet cannot directly access the server

---

### 7. SSH Into Bastion Host

![ssh-bastion](/images/ssh-bastionn.png)

Successfully connected from laptop to Bastion Host.

```bash
ssh -i new-key.pem ec2-user@32.197.42.166
```

---

### 8. SSH From Bastion To Private Server

![ssh-private](/images/ssh-privatee.png)

From Bastion Host:

```bash
chmod 400 new-key.pem

ssh -i new-key.pem ec2-user@172.31.241.248
```

Successfully connected to the private EC2 instance.

---

## Key Concepts Learned

- Public Subnet
- Private Subnet
- Route Table
- Internet Gateway
- Bastion Host
- Security Group Reference
- SSH Jump Server
- Network Isolation
- Internal vs Public Architecture

---

## Important Understanding

Public subnet:

```text
0.0.0.0/0 → Internet Gateway
```

Meaning:

- Internet access enabled
- Public resources allowed

---

Private subnet:

```text
No internet route
```

Meaning:

- No direct internet access
- Only trusted internal systems can communicate

---

## Final Result

Successfully built a mini enterprise AWS architecture:

- Public Bastion/Web Server
- Private Internal Server
- Internet routing separation
- Secure SSH access pattern
- Network isolation using Route Tables and Security Groups

This architecture is commonly used in real-world AWS production environments.