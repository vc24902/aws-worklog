+++
title = "Ngày 5 - IAM Role & AWS CLI"
date = "2026-04-24"
draft = false
weight = 5
+++

## Tôi đã làm

- Tạo IAM Role cho EC2.
- Gán quyền AmazonS3ReadOnlyAccess.
- Gắn IAM Role vào EC2.
- Kết nối bằng SSH.
- Kiểm tra AWS CLI.

## Các lệnh

## Kết quả

- Liệt kê thành công các S3 Bucket.
- Tải tệp lên không thành công do thiếu quyền.

## Tóm tắt bài thực hành AWS CLI

- AWS CLI là công cụ dùng để tương tác với các dịch vụ AWS.
- IAM Role cung cấp quyền cho EC2.
- Quyền truy cập kiểm soát các hành động cho phép hoặc từ chối.
- Lỗi AccessDenied xảy ra khi thiếu quyền truy cập.