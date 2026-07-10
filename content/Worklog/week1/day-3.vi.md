+++
title = "Ngày 3 - VPC"
date = "2026-04-22"
draft = false
weight = 3
+++

## Tôi đã làm

- Tạo VPC tùy chỉnh (10.0.0.0/16).
- Tạo các Subnet:
  - Public Subnet (10.0.1.0/24)
  - Private Subnet (10.0.2.0/24)
- Gắn Internet Gateway (IGW).
- Cấu hình Route Table:
  - Public Route → 0.0.0.0/0 → IGW
  - Private Route → chỉ sử dụng mạng nội bộ
- Bật tự động gán Public IPv4.

## Kết quả

Hoàn thành cấu hình kiến trúc mạng thành công.