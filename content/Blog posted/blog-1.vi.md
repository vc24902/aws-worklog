+++
title = "Blog 1 - Session Policies trong Amazon EKS Pod Identity"
date = "2026-06-29"
draft = false
weight = 1
+++


# SESSION POLICIES TRONG AMAZON EKS POD IDENTITY

Amazon EKS Pod Identity đã bổ sung tính năng Session Policies, cho phép giới hạn quyền IAM của từng Pod mà không cần tạo nhiều IAM Role riêng biệt.

## Những điểm chính cần biết

- Session Policy là một IAM Policy dạng inline.
- Quyền thực tế là phần giao nhau giữa IAM Role và Session Policy.
- Session Policy chỉ có thể thu hẹp quyền, không thể mở rộng quyền.
- Có thể tái sử dụng một IAM Role cho nhiều workload khác nhau.
- Giúp áp dụng nguyên tắc Least Privilege hiệu quả hơn.
- Hỗ trợ cả truy cập cùng tài khoản và khác tài khoản.
- Giảm số lượng IAM Role cần quản lý.
- Có thể cấu hình thông qua AWS Console, AWS CLI hoặc AWS SDK.

Tính năng này giúp Amazon EKS Pod Identity trở nên an toàn hơn, dễ quản lý hơn và phù hợp với các môi trường Kubernetes quy mô lớn.

---

## Hình ảnh

![blog 1 ](/images/blog1.jpg)

---

## Liên kết

https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203023237129303/?rdid=X5P0romMAosoDmk5#
---

## Tài liệu

https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html