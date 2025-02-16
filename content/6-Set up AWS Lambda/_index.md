---
title: "Set up AWS Lambda"
weight: 5 
chapter: false
pre: " <b> 6. </b> "
---

In this section, AWS Lambda is used to handle the business logic of the web application without the need to manage servers. Lambda will execute the source code to handle user requests, such as creating, reading, updating, and deleting (CRUD) data on DynamoDB, helping to build a flexible and cost-effective serverless application.

1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **Lambda**
- Select **Lambda**

![Description](/images/6/6.1.png)

2. In the Lambda interface, select **Create Function**

![Description](/images/6/6.2.png)

3. In the Create Function interface

- Enter **Function name** as `serverless-web-application-on-aws`
- Select **Runtime** as **Python 3.13**
- Expand the **Change default execution role** section

![Description](/images/6/6.3.png)

4. In the **Change default execution role** section
- In the **Execution role** field, select **Use an existing role**
- In the **Existing role** field, select **serverless-web-application-on-aws**

![Description](/images/6/6.4.png)

5. In the **Additional Configurations** section
- Enable **Enable function URL**
- In the **Auth type** field, select **NONE**

![Description](/images/6/6.5.png)

- In the **Invoke mode** field, enable **Configure cross-origin resource sharing**
- Select **Create function**

![Description](/images/6/6.6.png)

6. Test the Lambda function
- In the interface of the newly created lambda, copy the Function URL

![Description](/images/6/6.7.png)

- Paste the copied URL into a web browser

![Description](/images/6/6.8.png)

7. Change the code in the lambda
- Copy the code from the *lambda-function.py* file that was downloaded earlier

![Description](/images/6/6.9.png)

- Paste the code into the lambda and click **Deploy**

![Description](/images/6/6.10.png)

{{% notice note %}}
The lambda function above increases the views by 1 after each request (Reload web - Count the number of website views)
{{% /notice %}}

- Check the **views** field after a few web reloads in the **function URL** link, it will increase according to the number of website reloads

![Description](/images/6/6.12.png)

8. Change the **Lambda URL** in the *script.js* file in S3
- Paste the previously copied URL into the *script.js* file
- Upload the *script.js* file to S3 to replace the old file in the **Object** section of S3
+ Select **Upload**

![Description](/images/6/6.13.png)

+ Select **Add file**
+ Select **script.js**

![Description](/images/6/6.14.png)

+ Select **Upload**

We have completed the setup for the Serverless Web Application.