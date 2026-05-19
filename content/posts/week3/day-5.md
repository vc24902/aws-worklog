+++
title = "Day 5 - Bastion Host Architecture"
date = "2026-05-19"
draft = false
weight = 5
+++

# Day 5 - Bastion Host Architecture

## Objective

Learn how to secure private EC2 instances using a Bastion Host architecture.

---

## Architecture

Laptop
↓
Public EC2 (Bastion Host)
↓
Private EC2 (private-app)

---

## What I Did

### 1. Created Bastion Security Group

![bastion-sg](images/bastion-sg.png)

Created `Bastion-SG` with:

- SSH (22)
- Source: My IP

Purpose:
Allow only my laptop to SSH into the bastion server.

---

### 2. Updated Database Security Group

![database-sg](images/database-sg.png)

Modified `Database-SG`:

- SSH (22)
- Source: Bastion-SG

Purpose:
Allow SSH access only from the bastion host.

---

### 3. Created Private EC2

![private-ec2](images/private-ec2.png)

Launched EC2 instance:

- Name: `private-app`
- Amazon Linux 2023
- t3.micro
- No Public IP
- Attached `Database-SG`

Purpose:
Simulate a production private server.

---

### 4. SSH Into Bastion Host

![ssh-bastion](images/ssh-bastion.png)

Connected from local machine to public EC2.

```bash
ssh -i new-key.pem ec2-user@98.94.13.22
```

---

### 5. Copied PEM Key To Bastion

![copy-pem](images/copy-pem.png)

Copied PEM key from local machine to bastion host.

```bash
scp -i new-key.pem new-key.pem ec2-user@98.94.13.22:/home/ec2-user/
```

Purpose:
Allow bastion host to SSH into private EC2.

---

### 6. SSH Into Private EC2

![ssh-private](images/ssh-private.png)

From bastion host:

```bash
chmod 400 new-key.pem

ssh -i new-key.pem ec2-user@172.31.16.121
```

Successfully connected to private server.

---

## Verification

### Hostname

![hostname-test](images/hostname-test.png)

```bash
hostname
```

Result:

```text
ip-172-31-16-121.ec2.internal
```

---

### Private IP

![private-ip](images/private-ip.png)

```bash
hostname -I
```

Result:

```text
172.31.16.121
```

---

### Ping Test

![ping-test](images/ping-test.png)

```bash
ping google.com
```

Ping failed because ICMP traffic was blocked by NACL configuration.

This helped demonstrate the difference between:

- SSH (TCP)
- Ping (ICMP)

---

## Key Concepts Learned

- Bastion Host
- Public vs Private EC2
- Security Group Reference
- Private Networking
- SSH Jump Server
- Stateful vs Stateless Firewall
- Security Group vs NACL
- Layered Security Architecture

---

## Result

Successfully implemented a Bastion Host architecture:

- Public EC2 acts as jump server
- Private EC2 has no public IP
- Access controlled through Security Groups
- Private server isolated from direct internet access

This architecture is commonly used in real-world AWS production environments.