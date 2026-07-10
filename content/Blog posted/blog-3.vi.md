+++
title = "Blog 3 - Tự động hóa nâng cấp AWS Storage Gateway lên AL2023 bằng Infrastructure as Code"
date = "2026-07-01"
draft = false
weight = 3
+++

⚠️ Lưu ý: Nội dung dưới đây chỉ mang tính tham khảo. Vui lòng không sao chép nguyên văn vào báo cáo của bạn.

# TỰ ĐỘNG HÓA NÂNG CẤP AWS STORAGE GATEWAY LÊN AL2023 BẰNG INFRASTRUCTURE AS CODE

Amazon Linux 2 sẽ kết thúc hỗ trợ vào năm 2026. AWS khuyến nghị tự động hóa quá trình nâng cấp Storage Gateway lên Amazon Linux 2023 bằng Infrastructure as Code.

## Những điểm chính cần biết

- Terraform tạo EC2 AL2023 mới.
- Tự động kế thừa cấu hình mạng.
- Ansible thực hiện di chuyển EBS.
- Cache Disk được giữ nguyên.
- DNS hoặc Elastic IP được chuyển sang máy mới.
- Gateway ID được giữ nguyên.
- Giảm thời gian downtime.

Giải pháp Infrastructure as Code giúp việc nâng cấp Storage Gateway trở nên nhanh chóng, nhất quán và dễ quản lý.

---

## Hình ảnh

![blog 3 ](/images/blog3.jpg)

---

## Liên kết

https://www.facebook.com/groups/awsstudygroupfcj/permalink/2200302014068092/?rdid=9X5NjrHKM6BsWmWU#
---

## Tài liệu

https://docs.aws.amazon.com/storagegateway/