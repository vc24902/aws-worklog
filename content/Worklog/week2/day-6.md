+++
title = "Day 6 - EC2 Web Server + RDS Connection"
date = "2026-05-02"
draft = false
weight = 6
+++

## What I did

* Launched EC2 instance
* Installed Apache (httpd) and PHP
* Configured Security Group to allow HTTP (port 80)
* Created PHP file to connect to RDS MySQL
* Deployed web application on EC2
* Connected EC2 → RDS successfully via web

## Commands

```bash
sudo dnf install httpd php php-mysqlnd -y

sudo systemctl start httpd
sudo systemctl enable httpd

cd /var/www/html
sudo nano index.php
```

## PHP Code

```php
<?php
$conn = new mysqli(
  "database-1.codukmk8sdp5.us-east-1.rds.amazonaws.com",
  "admin",
  "YOUR_PASSWORD",
  "mydb"
);

if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}

echo "🔥 Connected to RDS successfully!";
?>
```

## Result

* Web server deployed successfully on EC2
* PHP application connected to RDS database
* Application accessible via public IP
* Verified full stack: EC2 → Web → RDS

## What I learned

* EC2 có thể chạy web server (Apache + PHP)
* HTTP (port 80) phải mở trong Security Group
* PHP có thể connect trực tiếp tới RDS
* Hiểu flow: User → EC2 Web → RDS Database
* Đây là kiến trúc cơ bản của web app trên AWS

## Issues & Fixes

* Web không truy cập được
  → Fix: mở port 80 trong Security Group

* PHP không connect được RDS
  → Fix: kiểm tra port 3306 + Security Group RDS

* Blank page
  → Fix: kiểm tra file index.php và service httpd

## Images

![httpd](/images/ec2-httpd.png)

![sg](/images/sg-http.png)

![php](/images/index-php.png)

![web](/images/web-result.png)
