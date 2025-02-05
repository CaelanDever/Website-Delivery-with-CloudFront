# Website-Delivery-with-CloudFront

# Website Delivery with CloudFront

**Author:** Caelan Dever  
**Email:** caelanwd@gmail.com

---

![Image]( http://learn.nextwork.org/happy_amber_shy_newt/uploads/aws-networks-cloudfront_1dddddwe )

---

## Introducing Today's Project!

website delivery with cloud front.

### Tools and concepts

Services I used were s3, and CloudFront. Key concepts I learnt include content delivery network (CDN).

### Project reflection

This project took me approximately 1 hour The most challenging part was writing the JSON code. It was most rewarding to finally be able to have the website up and running with the security.

To develop AWS skills and technical thinking, it definately did. 

---

## Set Up S3 and Website Files

I started the project by creating an S3 bucket to store the website's files. I can't use CloudFront for this task because it is not a storage solution. CloudFront is a content delivery network that simply hosts content that is stored somewhere

The three files that make up my website are index.html, which is the main file for a website, style.css, which is where you write down the visual appearance of your website's HTML elements, and script.js, which refers to a JavaScript file.

I validated that my website files work by opening them in google chrome and seeing the webpage. 

<img width="685" alt="fwa" src="https://github.com/user-attachments/assets/2d3cb8e6-d3a9-452e-b052-91ec2bcf36a0" />

---


## Exploring Amazon CloudFront

Amazon CloudFront is a content delivery network, which means it speeds up the distribution of your static and dynamic web content, such as .html, .css, .js, and image files. Businesses and developers use CloudFront because content is delivered fast.

To use Amazon CloudFront, you set up distributions, which are a set of instructions that tells CloudFront how to deliver your content. I set up a distribution for my s3 bucket. The origin is nextwork-three-tier.

My CloudFront distribution's default root object is index.html. This means it is the file that CloudFront should serve when someone visits the root URL of your website.

<img width="612" alt="dsad" src="https://github.com/user-attachments/assets/78966ce8-b81b-4ee0-9c66-a87691c46af4" />

---

## Handling Access Issues

When I tried visiting my distributed website, I ran into an access denied error because the S3 buckets are private. CloudFront needs explicit permission to access the files in your bucket.

My distribution's origin access settings were public. This caused the access denied error because I still need to go to the S3 bucket and set all your objects to public for everyone to access them.

To resolve the error, I set up origin access control (OAC). OAC lets you keep your S3 bucket and objects not publicly accessible, while still making sure they can be accessed through CloudFront.


<img width="598" alt="412" src="https://github.com/user-attachments/assets/97637696-fd81-4915-831b-b4f6fa8d96bc" />

---

## Updating S3 Permissions

Once I set up my OAC, I still needed to update my bucket policy because the OAC's role is that it makes sure only CloudFront can access the files stored in the S3 bucket.

Creating an OAC automatically gives me a policy I could copy, which grants permissions to the s3 bucket.


---<img width="728" alt="bkpls" src="https://github.com/user-attachments/assets/e3ff33a8-e445-4c02-9364-9a72984eee3d" />


## S3 vs CloudFront for Hosting

For my project extension, I'm comparing S3 vs CloudFront I initially had an error with static website hosting because based on the hosted website's URLs, permission settings and performance.

I tried resolving this by unchecking Block all public access. I still ran into an error because unchecking Block all public access doesn't grant permission to access the objects.

I could finally see my S3 hosted website when I updated the JSON bucket policy. This worked because you still need a bucket policy to explicitly grant permissions. When you set up a bucket policy that allows public read access, you're telling AWS to 

Compared to the permission settings for my CloudFront distribution, using S3 meant you can restrict access to your S3 bucket by allowing only your CloudFront distribution to access it I preferred S3 Direct Access,anyone with the S3 object URL can.

---

## S3 vs CloudFront Load Times

Load time means how quickly content on your website loads. The load times for the CloudFront site were faster than the S3 site because CloudFront's CDN caches content closer to users globally.

A business would prefer CloudFront especially for users located far from your S3 bucket's region.

 S3 static website hosting might be sufficient when hosting serves files directly from a single region.



---<img width="412" alt="csac" src="https://github.com/user-attachments/assets/7ff50f56-2967-41a0-88a5-1b2204019383" />


---
