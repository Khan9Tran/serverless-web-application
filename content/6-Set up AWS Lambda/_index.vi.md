---
title: "Thiết lập AWS Lambda"
weight: 5 
chapter: false
pre: " <b> 6. </b> "
---

Trong phần này, AWS Lambda được sử dụng để xử lý logic nghiệp vụ của ứng dụng web mà không cần quản lý server. Lambda sẽ thực thi mã nguồn để xử lý yêu cầu từ người dùng, như thao tác tạo, đọc, cập nhật, xóa (CRUD) dữ liệu trên DynamoDB, giúp xây dựng ứng dụng serverless linh hoạt và tiết kiệm chi phí.


1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **Lambda**
- Select **Lambda**

![Description](/images/6/6.1.png)

2. Trong giao diện Lambda chọn **Create Function**

![Description](/images/6/6.2.png)

3. Trong giao diện Create Function

- Nhập **Function name** là `serverless-web-application-on-aws`
- Chọn **Runtime** là **Python 3.13**
- Mở rộng phần **Change default execution role**

![Description](/images/6/6.3.png)

4. Trong phần **Change default execution role**
- Mục **Excution role** chọn **Use an existing role**
- Mục **Existing role**, chọn **serverless-web-application-on-aws**

![Description](/images/6/6.4.png)

5. Trong phần **Additional Configurations
- Bật **Enable function URL**
- Trong mục **Auth type**, chọn **NONE**

![Description](/images/6/6.5.png)

- Trong mục **Invoke mode**, bật **Configure cross-origin resource sharing**
- Chọn **Create function**

![Description](/images/6/6.6.png)


6. Kiểm tra hoạt động của Lambda
- Trong giao diện của lambda vừa tạo, copy Function URL

![Description](/images/6/6.7.png)

- Dán url vừa copy vào trình duyệt web

![Description](/images/6/6.8.png)


7. Thay đổi code trong lambda
- Copy code trong file *lambda-function.py* đã tải trước đó

![Description](/images/6/6.9.png)


- Dán đoạn code vào lambda và ấn **Deploy**

![Description](/images/6/6.10.png)

{{% notice note %}}
Hàm lambda trên có tác dụng tăng views lên 1 sau mỗi lần request (Reload web - Tính lượt xem của website)
{{% /notice %}}

- Kiểm tra trường **views** sau vài lần reload web trong link **function url** sẽ tăng lên theo số lần reload website

![Description](/images/6/6.12.png)

8. Thay đổi **Lambda URL** trong file *script.js* trong S3
- Dán url đã copy trước đó vào file *script.js*
- Upload file *script.js* vào S3 thay cho file cũ trong phần **Object** của S3
+   Chọn **Upload**

![Description](/images/6/6.13.png)

+   Chọn **Add file**
+   Chọn **script.js**

![Description](/images/6/6.14.png)

+   Chọn **Upload**

Chúng ta đã set up xong tất cả cho Serverless Web Application

