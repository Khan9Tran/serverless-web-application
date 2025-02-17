---
title: "Set up AWS DynamoDB"
weight: 4 
chapter: false
pre: " <b> 5. </b> "
---

In this section, DynamoDB is used as a NoSQL database to store and manage the data of the web application. It allows users to perform create, read, update, delete (CRUD) operations on data items quickly and flexibly, suitable for serverless applications with fluctuating traffic.

1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **DynamoDB**
- Select **DynamoDB**

![Description](/images/5/5.1.png)

2. In the DynamoDB interface, select **Create Table**

![Description](/images/5/5.2.png)

3. In the Create Table interface

- Enter **Table name** as `serverless-web-application-on-aws`
- Enter **Partition key** as `id`
- Scroll to the bottom of the page, select **Create table**

![Description](/images/5/5.3.png)

4. After the table status changes to **Active**
- Select the newly created table
- Select **Actions**, then select **Explore items**

![Description](/images/5/5.4.png)

- Select **Create item**

![Description](/images/5/5.5.png)

5. In the create item interface

- Select **Add new attribute**, choose **Number**
- Enter **Attribute name** as `views`
- Enter **value** sequentially as *0*, *1*
- Select **Create item**

![Description](/images/5/5.6.png)

6. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **IAM**
- Select **IAM**

![Description](/images/5/5.7.png)

2. In the IAM interface
- Select **Role** from the sidebar
- Select **Create role**

![Description](/images/5/5.8.png)

3. In the Create role interface
- In the **Trusted entity type** section, select **AWS Service**
- In the **Use case** section
    + In the **Service or use case** field, select **Lambda**
- Select **Next**

![Description](/images/5/5.9.png)

4. In the Add Permissions section
- Search for **dynamo**
- Select **AmazonDynamoDBFullAccess**
- Select **Next**

![Description](/images/5/5.10.png)

5. In the Name, review and create section
- In the **Role name** field, enter `serverless-web-application`
- Scroll to the bottom of the page, select **Create role**

![Description](/images/5/5.11.png)