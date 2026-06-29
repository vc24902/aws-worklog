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
## Result

- EC2 was automatically configured on launch
- Apache web server installed without manual SSH
- Web page deployed successfully using User Data
- Application accessible via public IP

## User Data Script


echo "<h1>Hello from EC2 User Data</h1>" > /var/www/html/index.html
