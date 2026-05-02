+++
title = "Day 5 - RDS MySQL + EC2 Connection"
date = "2026-05-01"
draft = false
weight = 5
+++

## What I did

* Created MySQL database using Amazon RDS
* Selected Free Tier instance (db.t4g.micro)
* Configured database username and password
* Configured VPC, subnet and public access
* Launched EC2 instance for database connection
* Configured Security Group to allow MySQL (port 3306)
* Installed MySQL client on EC2
* Connected EC2 to RDS successfully
* Verified connection using `SHOW DATABASES;`

## Result

* Successfully connected EC2 → RDS MySQL
* Retrieved list of default databases and `mydb`
* Confirmed database is accessible and working
* Verified networking and security configuration

## Commands

```bash
sudo dnf install mariadb105 -y

mysql -h database-1.codukmk8sdp5.us-east-1.rds.amazonaws.com -u admin -p

SHOW DATABASES;
```

## What I learned

* RDS requires proper Security Group configuration to allow access
* Port 3306 must be open for MySQL connections
* EC2 can be used as a secure bridge to connect to RDS
* Understanding of VPC networking and database connectivity
* Managed database (RDS) reduces operational overhead compared to self-hosted DB

## Issues & Fixes

* Cannot connect to RDS
  → Fixed by opening port 3306 in Security Group

* `mysql: command not found`
  → Fixed by installing MariaDB client:

```bash
sudo dnf install mariadb105 -y
```

* Connection timeout
  → Fixed by checking VPC, subnet and Public access settings

## Images

![ec2-launch](/images/ec2-launch-rds.png)

![rds-create](/images/rds-create.png)

![security-group](/images/sg-3306.png)

![connect-success](/images/connect-success.png)

![db-result](/images/db-result.png)
