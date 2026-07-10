+++
title = "Ngày 6 - EC2 Web Server + Kết nối RDS"
date = "2026-05-02"
draft = false
weight = 6
+++

## Tôi đã làm

- Khởi tạo EC2 Instance.
- Cài đặt Apache (httpd) và PHP.
- Cấu hình Security Group cho phép HTTP (cổng 80).
- Tạo tệp PHP để kết nối đến RDS MySQL.
- Triển khai ứng dụng web trên EC2.
- Kết nối thành công từ EC2 đến RDS thông qua ứng dụng web.

## Các lệnh

```bash
sudo dnf install httpd php php-mysqlnd -y

sudo systemctl start httpd
sudo systemctl enable httpd

cd /var/www/html
sudo nano index.php
```

## Mã PHP

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

## Kết quả

- Triển khai máy chủ web thành công trên EC2.
- Ứng dụng PHP kết nối thành công đến cơ sở dữ liệu RDS.
- Có thể truy cập ứng dụng thông qua Public IP.
- Xác nhận hoạt động của kiến trúc EC2 → Web → RDS.

## Những gì tôi học được

- EC2 có thể chạy máy chủ web Apache kết hợp với PHP.
- Cổng HTTP (80) cần được mở trong Security Group.
- PHP có thể kết nối trực tiếp đến Amazon RDS.
- Hiểu luồng hoạt động: Người dùng → EC2 Web → RDS Database.
- Đây là kiến trúc cơ bản của một ứng dụng web trên AWS.

## Vấn đề và cách khắc phục

- Không thể truy cập website.
  → Khắc phục bằng cách mở cổng 80 trong Security Group.

- PHP không kết nối được đến RDS.
  → Khắc phục bằng cách kiểm tra cổng 3306 và Security Group của RDS.

- Trang web hiển thị trắng.
  → Khắc phục bằng cách kiểm tra tệp `index.php` và dịch vụ `httpd`.