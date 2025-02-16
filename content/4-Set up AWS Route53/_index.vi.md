---
title: "Thiết lập AWS Route53"
weight: 3 
chapter: false
pre: " <b> 4. </b> "
---

Route 53 giúp chúng ta cấu hình tên miền để trỏ đến website đã triển khai trên AWS, giúp truy cập thuận tiện hơn.

{{% notice note %}}
Trong phần này, chúng ta cần phải chuẩn bị tên miền. Tên miền muốn sử dụng được Hosted Zone trên Route 53 thì chỉ cần đăng ký hợp lệ và có quyền quản lý DNS.
Mình sử dụng tên miền mượn từ một người bạn nguyenthanhhuy.id.vn, các bạn cũng có thể đăng ký tên miền đuôi .id.vn miễn phí từ các nhà cung cấp dịch vụ tên miền như matbao, tenten, ...
{{% /notice %}}

1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **Route 53**
- Select **Route 53**

![Description](/images/4/4.1.png)

2. Trong giao diện Route 53 chọn **Started**
- Chọn **Create hosted zones**
- Chọn **Get started**

![Description](/images/4/4.2.png)

3. Trong giao diện Create Hosted Zone

- Nhập **Domain name** là tên miền của bạn
- Cuộn đến cuối trang, chọn **Create hosted zone**

![Description](/images/4/4.3.png)

4. Sau khi tạo Hosted zone, truy cập hosted zone vừa tạo
- Trong phần **Record**, copy giá trị trong mục **Value/Route traffic**

![Description](/images/4/4.4.png)

5/ Trong giao diện quản lý tên miền, dán 4 **Name server** vừa copy

{{% notice note %}}
Bỏ dấu chấm ở đuôi của các NS
{{% /notice %}}

![Description](/images/4/4.5.png)

6. Quay lại phần **Edit settings** của CloudFront
- Trong mục **Alternate domain name (CNAME)** nhập `fcj.nguyenthanhhuy.id.vn` 

{{% notice note %}}
Thay phần "nguyenthanhhuy.id.vn" bằng tên miền của bạn
{{% /notice %}}

- Trong mục **SSL Certificate**
+   Chọn **Request certificate**

![Description](/images/4/4.6.png)

+ Chọn **Next**

![Description](/images/4/4.7.png)

7. Tạo SSL Certificate trong phần Request public certificate
- Trong mục **Fully qualified domain name**, nhập `*.nguyenthanhhuy.id.vn`
- Cuộn đến cuối trang, chọn **Request**

![Description](/images/4/4.8.png)


8. Quay lại tab Edit Settings của CloudFront Distributions
- Trong mục **Custom SSL Certificate**, chọn certificate vừa tạo
- Cuộn đến cuối trang, chọn **Save changes**

![Description](/images/4/4.12.png)

9. Truy cập vào certificate đã tạo
- Trong phần **Records** chọn **Create record in Route 53**

![Description](/images/4/4.9.png)

- Chọn **Create records**

![Description](/images/4/4.10.png)

10. Quay lại Route 53 **nguyenthanhhuy.id.vn**
- Trong phần Record, ta thấy một **CNAME** vừa được tạo ra
- Chọn **Create Record**

![Description](/images/4/4.11.png)

11. Trong giao diện **Create record**
- **Recort name** nhập `fcj`
- Bật phần **Alias**
- Trong mục **Route traffic to**
    +   **Choose Endpont** chọn: `Alias to CloudFront distribution`
    +   **Choose distributon** chọn: `fcj.nguyenthanhhuy.id.vn`
- Chọn **Create record**

![Description](/images/4/4.13.png)

12. Kiểm tra truy cập website
- Trên thanh tìm kiếm của trình duyệt web, nhập `fcj.nguyenthanhhuy.id.vn`
- Nhập `Nhựt Khang` vào ô textbox
- Nhấn **Submit**

![Description](/images/4/4.14.png)

Màng hình hiển thị dòng text **Hello, Nhựt Khang!**