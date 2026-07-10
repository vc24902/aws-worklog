+++
title = "Ngày 3 - EC2 User Data"
date = "2026-04-29"
draft = false
weight = 3
+++

## Tôi đã làm

- Khởi tạo EC2 Instance.
- Cấu hình Security Group (SSH + HTTP).
- Thêm User Data Script.
- Tự động cài đặt Apache (httpd).
- Triển khai một trang web đơn giản.

## Kết quả

- EC2 được cấu hình tự động ngay khi khởi tạo.
- Máy chủ web Apache được cài đặt mà không cần SSH thủ công.
- Trang web được triển khai thành công bằng User Data.
- Có thể truy cập ứng dụng thông qua Public IP.

## User Data Script

```bash
echo "<h1>Hello from EC2 User Data</h1>" > /var/www/html/index.html
```