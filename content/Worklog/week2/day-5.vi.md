+++
title = "Ngày 5 - RDS MySQL + Kết nối EC2"
date = "2026-05-01"
draft = false
weight = 5
+++

## Tôi đã làm

- Tạo cơ sở dữ liệu MySQL bằng Amazon RDS.
- Chọn phiên bản Free Tier (`db.t4g.micro`).
- Cấu hình tên người dùng và mật khẩu cơ sở dữ liệu.
- Cấu hình VPC, Subnet và Public Access.
- Khởi tạo EC2 để kết nối đến cơ sở dữ liệu.
- Cấu hình Security Group cho phép MySQL (cổng 3306).
- Cài đặt MySQL Client trên EC2.
- Kết nối thành công từ EC2 đến RDS.
- Kiểm tra kết nối bằng lệnh `SHOW DATABASES;`.

## Kết quả

- Kết nối thành công từ EC2 đến RDS MySQL.
- Hiển thị danh sách các cơ sở dữ liệu mặc định và `mydb`.
- Xác nhận cơ sở dữ liệu hoạt động bình thường.
- Xác minh cấu hình mạng và bảo mật chính xác.

## Các lệnh

```bash
sudo dnf install mariadb105 -y

mysql -h database-1.codukmk8sdp5.us-east-1.rds.amazonaws.com -u admin -p

SHOW DATABASES;
```

## Những gì tôi học được

- RDS cần được cấu hình Security Group phù hợp để cho phép truy cập.
- Cổng 3306 phải được mở cho kết nối MySQL.
- EC2 có thể được sử dụng như một cầu nối an toàn để kết nối với RDS.
- Hiểu về kết nối cơ sở dữ liệu và mạng trong VPC.
- RDS giúp giảm công sức quản trị so với việc tự quản lý cơ sở dữ liệu.

## Vấn đề và cách khắc phục

- Không thể kết nối đến RDS.
  → Khắc phục bằng cách mở cổng 3306 trong Security Group.

- `mysql: command not found`
  → Khắc phục bằng cách cài đặt MariaDB Client.

```bash
sudo dnf install mariadb105 -y
```

- Connection timeout.
  → Khắc phục bằng cách kiểm tra VPC, Subnet và Public Access.