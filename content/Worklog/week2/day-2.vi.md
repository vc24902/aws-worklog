+++
title = "Ngày 2 - IAM Role"
date = "2026-04-28"
draft = false
weight = 2
+++

## Tôi đã làm

- Tạo IAM Role cho EC2.
- Gán quyền AmazonS3ReadOnlyAccess.
- Khởi tạo EC2 với IAM Role.
- Kết nối đến EC2 bằng Browser SSH.
- Kiểm tra truy cập Amazon S3 bằng AWS CLI.

## Các lệnh

```bash
aws s3 ls
```

## Kết quả

- Gắn IAM Role vào EC2 thành công.
- Xác nhận EC2 có thể truy cập Amazon S3 bằng IAM Role đã được gán.
- Liệt kê thành công các S3 Bucket bằng AWS CLI.
- Xác nhận không cần sử dụng AWS Access Key khi dùng IAM Role.