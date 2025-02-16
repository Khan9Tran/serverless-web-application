---
title: "Thiết lập AWS CloudFront"
weight: 2 
chapter: false
pre: " <b> 3. </b> "
---

Amazon CloudFront là một dịch vụ mạng phân phối nội dung (CDN) giúp chúng ta phân phối nội dung tĩnh và động một cách dễ dàng, đáng tin cậy với hiệu năng tốc độ cao, khả năng bảo mật và dễ sử dụng với nhà phát triển. Ở phần này, chúng ta sẽ dùng CloudFront để phân phối nội dung từ kho lưu trữ S3

1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Tìm và chọn **CloudFront** hoặc có thể chọn trên màng hình chính

![Description](/images/3/3.1.png)

2. Trong giao diện CloudFront chọn **Create distribution**

![Description](/images/3/3.2.png)

3. Trong giao diện Create CloudFront

- Chọn Origin Domain là S3 vừa tạo
- Phần **Name** sẽ được sinh ra tự động

![Description](/images/3/3.3.png)

- Trong phần Origin access chọn **Origin access control setting**
- Tiếp tục, chọn **Create new OAC**

![Description](/images/3/3.4.png)

- Trong giao diện tạo OAC
    + Phần **name** nhập `serverless-web-application-on-aws-fcj.s3.us-east.amazonaws.com-1`
    + Chọn **Create**

![Description](/images/3/3.5.png)

- Trong phần **Web Application Firewall**, chọn **Do not enable security protections**

![Description](/images/3/3.6.png)

- Giữ nguyên các phần còn lại và cuộn đến cuối trang, chọn **Create distribution**

![Description](/images/3/3.7.png)

- Sau khi tạo xong, chọn **Copy policy**

![Description](/images/3/3.8.png)

- Quay lại phần S3 Bucket đã tạo
    + Vào tab **Permissions**
    + Trong phần **Bucket Policy**, chọn **Edit**
    + Trong giao diện **Edit bucket policy**, dán phần policy đang được copy
    + Ấn **Save change**

![Description](/images/3/3.9.png)

- Chuyển sang CloudFront, vào phần **Setting** chọn **Edit**

![Description](/images/3/3.10.png)

- Cuộn xuống phần **Default root object**, nhập `index.html`. Sau đó ấn **Save changes**

![Description](/images/3/3.11.png)



