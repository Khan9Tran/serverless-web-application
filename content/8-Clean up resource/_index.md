---
title: "Clean up resources"
weight: 7 
chapter: false
pre: " <b> 8. </b> "
---

1. Clean up Lambda
- Select **Lambda serverless-web-application**
- Select **Actions**
- Select **Delete**

![Description](/images/8/8.1.png)

- Enter `confirm`
- Select **Delete**

![Description](/images/8/8.2.png)

2. Clean up DynamoDB
- Select the **Table** section
- Check the table **serverless-web-application**
- Select **Delete**
- Enter `confirm`
- Select **Delete**

![Description](/images/8/8.3.png)

3. Clean up IAM role
- Select the **Roles** section
- Check the role **serverless-web-application-on-aws**
- Select **Delete**

![Description](/images/8/8.4.png)

- Enter `serverless-web-application-on-aws`
- Select **Delete**

![Description](/images/8/8.5.png)

4. Clean up Route 53
- Select the **Hosted zones** section
- Select the zone **nguyenthanhhuy.id.vn**
- Select the last 2 records
- Select **Delete**

![Description](/images/8/8.8.png)

- Select **Delete zone**
- Enter `delete`
- Select **Delete**

![Description](/images/8/8.7.png)

5. Clean up S3 Bucket
- Access S3 **serverless-web-application-on-aws-fcj**
- Select **Empty Bucket**
- Enter `permanently delete`
- Select **Empty**

![Description](/images/8/8.9.png)

- Then, delete the bucket **serverless-web-application-on-aws-fcj**
    + Select **serverless-web-application-on-aws-fcj**
    + Select **Delete**
    + Enter **serverless-web-application-on-aws-fcj**
    + Select **Delete bucket**

![Description](/images/8/8.10.png)

6. Clean up CloudFront
- Access CloudFront
- Select the **Distribution** we are using
- Select **Disable** and confirm

![Description](/images/8/8.6.png)

- Wait until CloudFront is disabled, then select **Delete**
- Confirm **Delete**

![Description](/images/8/8.11.png)

7. Delete SSL Certificate
- Access Certificate Manager
- Select the certificate **nguyenthanhhuy.id.vn**
- Select **Delete**

![Description](/images/8/8.12.png)

- Enter `delete`
- Select **Delete**

![Description](/images/8/8.13.png)

Thus, we have cleaned up the resources and concluded here.

*Trần Lâm Nhựt Khang*