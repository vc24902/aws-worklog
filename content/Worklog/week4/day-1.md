+++
title = "Day 1 - Launch Template & Auto Scaling Group"
date = "2026-05-11"
draft = false
weight = 1
+++

## What I did

* Created an EC2 Launch Template
* Selected Amazon Linux 2023 AMI
* Configured t3.micro instance type
* Added Security Group and Key Pair
* Configured EC2 User Data to install Apache automatically
* Created an Auto Scaling Group using the Launch Template
* Configured Desired Capacity = 1
* Configured Minimum Capacity = 1
* Configured Maximum Capacity = 2
* Selected two Availability Zones
* Verified Auto Scaling Group launched EC2 instance successfully

## Result

* Successfully created Launch Template
* Successfully created Auto Scaling Group
* EC2 instance launched automatically
* Apache Web Server installed successfully
* Verified instance health status is Healthy
