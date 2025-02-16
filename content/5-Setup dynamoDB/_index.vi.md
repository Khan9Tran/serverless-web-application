---
title: "Thiết lập AWS DynamoDB"
weight: 4 
chapter: false
pre: " <b> 5. </b> "
---

Trong phần này, DynamoDB được sử dụng làm cơ sở dữ liệu NoSQL để lưu trữ và quản lý dữ liệu của ứng dụng web. Nó cho phép người dùng thực hiện các thao tác tạo, đọc, cập nhật, xóa (CRUD) các mục dữ liệu nhanh chóng và linh hoạt, phù hợp với ứng dụng serverless có lượng truy cập biến động.


1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **DynamoDB**
- Select **DynamoDB**

![Description](/images/5/5.1.png)

2. Trong giao diện DynamoDB chọn **Create Table**

![Description](/images/5/5.2.png)

3. Trong giao diện Create Table

- Nhập **Table name** là `serverless-web-application-on-aws`
- Nhập **Partition key** là `id`
- Cuộn xuống cuối trang, chọn **Create table**

![Description](/images/5/5.3.png)

4. Sau khi trạng thái của table chuyển sang **Active**
- Chọn table vừa tạo
- Chọn **Actions**, chọn mục **Explore items**


![Description](/images/5/5.4.png)

- Chọn **Create item**

![Description](/images/5/5.5.png)

5. Trong giao diện create item

- Chọn **Add new attibute**, chọn **Number**
- Nhập **Attribute name** là `views`
- Nhập lần lượt **value** là *0*, *1*
- Chọn **Create item**

![Description](/images/5/5.6.png)

6. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **IAM**
- Select **IAM**

![Description](/images/5/5.7.png)

2. Trong giao diện IAM
- Chọn mục **Role** tại thanh bên
- Chọn **Create role**

![Description](/images/5/5.8.png)

3. Trong giao diện Create role
- Trong mục **Trusted entity type** chọn **AWS Service**
- Trong mục **Use case**
    + Phần **Service or use case** chọn **Lambda**
- Chọn **Next**

![Description](/images/5/5.9.png)

4. Trong phần Add Permissions
- Tìm kiếm **dynamo**
- Chọn **AmazonDynamoDBFullAccess**
- Chọn **Next**

![Description](/images/5/5.10.png)

5. Trong phần Name, review and create
- Trong mục **Role name**, nhập `serverless-web-application`
- Cuộn đến cuối trang, chọn **Create role**

![Description](/images/5/5.11.png)
