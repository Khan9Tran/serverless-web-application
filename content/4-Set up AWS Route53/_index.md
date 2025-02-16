---
title: "Set up AWS Route53"
weight: 3 
chapter: false
pre: " <b> 4. </b> "
---

Route 53 helps us configure domain names to point to the website deployed on AWS, making access more convenient.

{{% notice note %}}
In this section, we need to prepare a domain name. The domain name to be used with the Hosted Zone on Route 53 only needs to be validly registered and have DNS management rights.
I am using a domain borrowed from a friend, nguyenthanhhuy.id.vn. You can also register a free .id.vn domain from domain service providers like matbao, tenten, etc.
{{% /notice %}}

1. Go to [AWS Management Console](https://aws.amazon.com/console/)
- Find **Route 53**
- Select **Route 53**

![Description](/images/4/4.1.png)

2. In the Route 53 interface, select **Started**
- Select **Create hosted zones**
- Select **Get started**

![Description](/images/4/4.2.png)

3. In the Create Hosted Zone interface

- Enter **Domain name** as your domain name
- Scroll to the bottom of the page, select **Create hosted zone**

![Description](/images/4/4.3.png)

4. After creating the Hosted zone, access the newly created hosted zone
- In the **Record** section, copy the values in the **Value/Route traffic** field

![Description](/images/4/4.4.png)

5. In the domain management interface, paste the 4 **Name servers** you just copied

{{% notice note %}}
Remove the dot at the end of the NS
{{% /notice %}}

![Description](/images/4/4.5.png)

6. Go back to the **Edit settings** section of CloudFront
- In the **Alternate domain name (CNAME)** field, enter `fcj.nguyenthanhhuy.id.vn`

{{% notice note %}}
Replace "nguyenthanhhuy.id.vn" with your domain name
{{% /notice %}}

- In the **SSL Certificate** section
+ Select **Request certificate**

![Description](/images/4/4.6.png)

+ Select **Next**

![Description](/images/4/4.7.png)

7. Create an SSL Certificate in the Request public certificate section
- In the **Fully qualified domain name** field, enter `*.nguyenthanhhuy.id.vn`
- Scroll to the bottom of the page, select **Request**

![Description](/images/4/4.8.png)

8. Go back to the Edit Settings tab of CloudFront Distributions
- In the **Custom SSL Certificate** section, select the certificate you just created
- Scroll to the bottom of the page, select **Save changes**

![Description](/images/4/4.12.png)

9. Access the created certificate
- In the **Records** section, select **Create record in Route 53**

![Description](/images/4/4.9.png)

- Select **Create records**

![Description](/images/4/4.10.png)

10. Go back to Route 53 **nguyenthanhhuy.id.vn**
- In the Record section, you will see a newly created **CNAME**
- Select **Create Record**

![Description](/images/4/4.11.png)

11. In the **Create record** interface
- Enter `fcj` in the **Record name** field
- Enable the **Alias** option
- In the **Route traffic to** section
    + **Choose Endpoint** select: `Alias to CloudFront distribution`
    + **Choose distribution** select: `fcj.nguyenthanhhuy.id.vn`
- Select **Create record**

![Description](/images/4/4.13.png)

12. Check website access
- In the web browser's search bar, enter `fcj.nguyenthanhhuy.id.vn`
- Enter `Nhựt Khang` in the textbox
- Click **Submit**

![Description](/images/4/4.14.png)

The screen displays the text **Hello, Nhựt Khang!**