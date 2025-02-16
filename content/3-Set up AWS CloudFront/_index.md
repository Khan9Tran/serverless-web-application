---
title: "Set up AWS CloudFront"
weight: 2 
chapter: false
pre: " <b> 3. </b> "
---

Amazon CloudFront is a content delivery network (CDN) service that helps us distribute static and dynamic content easily, reliably, with high performance, security, and ease of use for developers. In this section, we will use CloudFront to distribute content from the S3 storage.

1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find and select **CloudFront** or you can select it on the main screen

![Description](/images/3/3.1.png)

2. In the CloudFront interface, select **Create distribution**

![Description](/images/3/3.2.png)

3. In the Create CloudFront interface

- Select the Origin Domain as the S3 you just created
- The **Name** will be generated automatically

![Description](/images/3/3.3.png)

- In the Origin access section, select **Origin access control setting**
- Next, select **Create new OAC**

![Description](/images/3/3.4.png)

- In the OAC creation interface
    + In the **name** section, enter `serverless-web-application-on-aws-fcj.s3.us-east.amazonaws.com-1`
    + Select **Create**

![Description](/images/3/3.5.png)

- In the **Web Application Firewall** section, select **Do not enable security protections**

![Description](/images/3/3.6.png)

- Keep the remaining sections as default and scroll to the bottom of the page, select **Create distribution**

![Description](/images/3/3.7.png)

- After creation, select **Copy policy**

![Description](/images/3/3.8.png)

- Go back to the created S3 Bucket
    + Go to the **Permissions** tab
    + In the **Bucket Policy** section, select **Edit**
    + In the **Edit bucket policy** interface, paste the copied policy
    + Click **Save changes**

![Description](/images/3/3.9.png)

- Switch to CloudFront, go to the **Setting** section, select **Edit**

![Description](/images/3/3.10.png)

- Scroll down to the **Default root object** section, enter `index.html`. Then click **Save changes**

![Description](/images/3/3.11.png)