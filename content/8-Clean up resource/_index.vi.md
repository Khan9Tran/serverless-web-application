---
title: "Dọn dẹp tài nguyên"
weight: 7 
chapter: false
pre: " <b> 8. </b> "
---


1. Dọn dẹp Lambda
- Chọn **Lambda serverless-web-application**
- Chọn **Actions**
- Chọn **Delete**

![Description](/images/8/8.1.png)

- Nhập `confirm`
- Chọn **Delete**

![Description](/images/8/8.2.png)

2. Dọn dẹp DynamoDB
- Chọn mục **Table**
- Tích chọn vào table **serverless-web-application**
- Chọn **Delete**
- Nhập `confirm`
- CHọn **Delete**

![Description](/images/8/8.3.png)

3. Dọn dẹp IAM role
- Chọn mục **Roles**
- Tích chọn vào role **serverless-web-application-on-aws**
- Chọn **Delete**

![Description](/images/8/8.4.png)

- Nhập `serverless-web-application-on-aws`
- Chọn **Delete**

![Description](/images/8/8.5.png)

4. Dọn dẹp Route 53
- Chọn mục **Hosted zones**
- Chọn vào zone **nguyenthanhhuy.id.vn**
- Chọn 2 record cuối
- Chọn **Delete**

![Description](/images/8/8.8.png)

- Chọn **Delete zone**
- Nhập `delete`
- Chọn **Delete**

![Description](/images/8/8.7.png)

5. Dọn dẹp S3 Bucket
- Truy cập vào S3 **serverless-web-application-on-aws-fcj**
- Chọn **Empty Bucket**
- Nhập `permanenty delete`
- Chọn **Empty**

![Description](/images/8/8.9.png)

- Sau đó, thực hiện xóa bucker **serverless-web-application-on-aws-fcj**
    +   Chọn **serverless-web-application-on-aws-fcj**
    +   Chọn **Delete**
    +   Nhập **serverless-web-application-on-aws-fcj**
    +   Chọn **Delete bucket**

![Description](/images/8/8.10.png)

6. Dọn dẹp CloudFront
- Truy cập vào CloudFront
- Chọn **Distributon** là Cloudfront chúng ta đang dùng
- Chọn **Disable** và xác nhận

![Description](/images/8/8.6.png)

- Đợi đến khi Cloudfront disable, ta chọn **Delete** 
- Xác nhận **Delete**

![Description](/images/8/8.11.png)

7. Xóa SSL Certificate
- Truy cập Certificate manager
- Chọn Certificate **nguyenthanhhuy.id.vn**
- Chọn **Delete**

![Description](/images/8/8.12.png)

- Nhập `delete`
- Chọn **Delete**

![Description](/images/8/8.13.png)

Như vậy, chúng ta đã dọn dẹp tài nguyên xong và kết thúc tại đây.
 
*Trần Lâm Nhựt Khang*