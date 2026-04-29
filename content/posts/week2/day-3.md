+++
title = "Day 3 - EC2 User Data"
date = "2026-04-29"
draft = false
weight = 3
+++

## What I did

- Launched EC2 instance
- Configured Security Group (SSH + HTTP)
- Added User Data script
- Automatically installed Apache (httpd)
- Deployed simple web page

## Images

![user-data](/images/user-data.png)
![ec2-running](/images/ec2-running.png)
![ec2-web](/images/ec2-web-data.png)-
## User Data Script

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd

echo "<h1>Hello from EC2 User Data</h1>" > /var/www/html/index.html
