+++
title = "Ngày 4 - AWS CLI & IAM Deny"
date = "2026-04-30"
draft = false
weight = 4
+++

## Tôi đã làm

- Cài đặt AWS CLI trên máy tính.
- Cấu hình AWS CLI bằng IAM User (ChienUser).
- Xác minh danh tính bằng AWS STS.
- Liệt kê các S3 Bucket bằng AWS CLI.
- Tải tệp lên Amazon S3 thành công.
- Tạo IAM Policy với quyền từ chối (Deny) cho hành động `s3:PutObject`.
- Gán Policy vào IAM User.
- Kiểm tra tải tệp lại → AccessDenied.

## Các lệnh

```bash
aws configure
aws sts get-caller-identity
aws s3 ls
echo "hello aws cli" > test.txt
aws s3 cp test.txt s3://chien-s3-667802015889-us-east-1-an/
```

## Kết quả

- Xác thực AWS CLI thành công bằng IAM User.
- Xác minh đúng danh tính bằng AWS STS.
- Thực hiện tải tệp lên Amazon S3 bằng AWS CLI.
- Quan sát lỗi AccessDenied do IAM Policy có Explicit Deny.
- Xác nhận rằng quyền Deny luôn được ưu tiên hơn Allow trong IAM.