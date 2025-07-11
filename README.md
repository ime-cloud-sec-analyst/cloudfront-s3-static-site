# cloudfront-s3-static-site
Deploying a private S3 static site using Amazon CloudFront for secure public access with default root object.
📘 Title:
Deploying a Secure Static Website using Amazon S3 and CloudFront CDN

🧠 Lab Description and Discussion:
This lab demonstrates how to host a private static website on Amazon S3 and securely deliver its content through Amazon CloudFront — AWS’s Content Delivery Network (CDN). The primary goal was to restrict direct public access to the S3 bucket while enabling secure access through a CloudFront distribution.

Through this lab, I successfully configured an S3 bucket for private hosting, created a CloudFront distribution that points to the bucket, applied the correct bucket policy, defined a default root object (index.html), and validated access via the CloudFront public URL.

🎯 Scope of the Lab:
Build a static website using private S3 bucket

Create a CloudFront distribution for public delivery

Set the root object to index.html

Enable CloudFront to access private S3 using origin access

Make files accessible only via CloudFront

Deploy a functional public URL for file access

🛠️ Method and Approach:
S3 Bucket Setup:

Created an S3 bucket named secure-bucket-ime-ben.

Uploaded static files: index.html, file1.txt, and multiple image formats (.webp, .jpg, .avif).

Made the bucket private and blocked all public access.

CloudFront Distribution:

Launched a new CloudFront distribution.

Selected Amazon S3 as the origin.

Enabled “Allow private S3 bucket access to CloudFront” checkbox.

Used recommended origin settings and default cache behavior.

Skipped WAF (Web Application Firewall) for simplicity.

Set index.html as the default root object.

Policy Configuration:

CloudFront automatically added a bucket policy allowing only CloudFront to read from the bucket.

Testing and Verification:

Waited for CloudFront to finish deploying.

Accessed files via the CloudFront domain:
https://d24ccp5xkx7iul.cloudfront.net

Observed that all content was loading securely and correctly.

🚧 Challenges and Limitations:
Challenge	Solution
403 Forbidden error when accessing S3 URL directly	Ensured the bucket was private and access was only allowed via CloudFront
Delay in CloudFront distribution propagation	Waited up to 15 minutes before testing
Missing root object setup (index.html)	Went back to edit the distribution and added default root object
Directory listing not styled	Used plain HTML with basic links — no styling applied

💡 Techniques and Strategies Applied:
Security First: The S3 bucket was kept private and only accessible through CloudFront using a generated origin access control.

CDN Acceleration: Used CloudFront to cache and deliver content globally with low latency.

Step-by-step troubleshooting: Verified each part after deployment to locate issues like missing files or misconfigurations.

Policy Review: Validated IAM bucket policy to ensure CloudFront access was allowed and secure.

📚 Lessons Learned:
Always restrict direct S3 access when hosting through CloudFront for maximum security.

CloudFront default behavior can be customized, but you must explicitly define your root object (index.html) for static sites.

Patience is key — CloudFront deployments take time to reflect.

A simple website hosted in S3 with CloudFront can be used to distribute any type of static content securely and reliably.

🌍 Impact and Use Cases:
Ideal for hosting static websites, portfolios, file downloads, or landing pages.

Can be applied to enterprise setups where content security and delivery speed are critical.

Demonstrates real-world skills in cloud security, serverless web hosting, and CDN optimization.

📸 Lab Evidence:
✅ 21 images documenting:

Bucket creation

File uploads

CloudFront setup

Policy updates

Successful deployment

Final access through CloudFront

All screenshots are stored in the GitHub repository for verification.
