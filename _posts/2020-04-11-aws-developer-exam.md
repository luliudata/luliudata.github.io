---
title:  "How I passed my AWS Certified Developer Associate exam"
mathjax: true
author: Lu
category: AWS
lang: en
---


I passed my first AWS exam - Developer Associate exam on 22nd February 2020 (Woo-Hoo). Six months ago, I had zero experience in AWS or any other cloud platform. I am very lucky that my daily work provides me with the opportunities to get involved in a fair amount of hands-on tasks on AWS, which is helpful for my exam preparation. It's been a challenging six months, and I want to share it with you.

The motivation for this post is to share my studying process and list some useful learning resources that I used while preparing for the exam, and hopefully, it will give you some insights.

My studying process mainly included the following four resources:

1. The AWS Certified Developer - Associate 2020 course [A Cloud Guru](https://acloud.guru/)

2. AWS official documentation: [AWS Whitepaper](https://aws.amazon.com/whitepapers) & [AWS FAQs](https://aws.amazon.com/faqs/)

3. The Practice Tests by Stephane Maarek [Udemy](https://www.udemy.com/course/aws-certified-developer-associate-practice-tests-dva-c01/)

4. The Practice Tests by Jon Bonso [Udemy](https://www.udemy.com/course/aws-certified-developer-associate-practice-exams-amazon/)

I made lots of notes while studying A Cloud Guru course. I prefer taking notes which helps me better absorb new knowledge. Some topics I watched multiple times because it’s important to understand the key topics truly rather than just memorising the contents. Specifically, what services are exactly used for and how they can be linked with other services, etc. Additionally, I highly recommend the discussion forum on A Cloud Guru. For example, [a useful post](https://acloud.guru/forums/aws-cda-2018/discussion/-Lp1CEqTdDxyOJS_g9iz/infrastructure_guy_passed_dev) reflecting on someone’s feedback of passing the exam.

![0_ZIc8WltzbtKs3Smh](https://user-images.githubusercontent.com/44141273/149223092-9e520114-df2f-4e4f-986a-ed0d64cc5015.jpg)

####Some useful links:

* AWS Certified Developer Associate exam [official website](https://aws.amazon.com/certification/certified-developer-associate/)

* [Qwiklabs](https://www.qwiklabs.com/) — provides AWS hands-on training

* [Whizlabs](https://www.whizlabs.com/aws-developer-associate/) — with AWS free tests

* [Quizlet](https://quizlet.com/147972512/aws-certified-developer-associate-flash-cards/)

I discovered this website after I finished my exam, but I still want to share it with you, because I found there are quite a lot of free quizzes that you can use as practice tests.

* [AWS blog by Jeff Barr](https://aws.amazon.com/blogs/aws/author/jbarr/) (AWS Vice President & Chief Evangelist) — delivers regular updates on AWS technologies

* A Cloud Guru — [AWS This Week](https://acloud.guru/series/aws-this-week)

####Some topics I encountered and some notes:

Heavy topics: Lambda, API Gateway, DynamoDB, Elastic BeanStalk, CI/CD Pipeline (CodeCommit, CodeBuild, CodeDeploy and CodePipeline)

Lighter topics: IAM, S3, EC2, SQS, SNS, CloudWatch, X-Ray, Web Identity Federation (Cognito), KMS, Systems Manager Parameter Store, Kinesis.

Quite a lot of questions are about Lambda, some of the in-depth questions require a really good understanding of Lambda. For example:

1. Lambda authorizer is an API Gateway feature that uses a Lambda function to control access to your API.

2. The usage of environment variables.

3. RDS can’t trigger Lambda directly, but it can be configured to send a notification to SNS so that we can use SNS to trigger Lambda functions.

4. Use the API Gateway stage variable to manage Lambda functions.

* For each AWS account, Export names must be unique within a region (CloudFormation).

* SQS supports ‘Dead-letter queue’, other queues can target for messages that can’t be processed successfully, DLQ is useful for debugging because they let you isolate problematic messages to determine why their processing doesn’t succeed.

* STS (Security Token Security) is a web service, and it doesn’t support API Gateway.

* The process of creating a thumbnail for the image file that is uploaded to an S3 bucket:

    1. First, create a Lambda function. S3 will invoke this Lambda function when the objects are created.
    
    2. Once the Lambda function is invoked, it can read the image object from the source bucket and create a thumbnail image target bucket.

* In CloudFormation:
    
    1. ‘DeletionPolicy’ attribute can be used to preserve a specific resource when its stack is deleted.

    2. ‘Stack Termination Protection’ feature enables protection against accidental deletion of an entire stack, but it can’t save a specific resource.

    3. ‘CloudFormation: Delete Stack’ action will delete the whole stack.

    4. By default, if CloudFormation encounters an error, it’ll terminate and roll back all resources created on failure.

* CloudWatch logs & X-Ray logs

* What services are serverless? (Lambda, S3, DynamoDB, API Gateway, SNS etc.)

* What services are not serverless? (RDS, EC2, Elastic BeanStalk)

* The difference between ‘Local Secondary Index’ and ‘Global Secondary Index’ (DynamoDB).

* Calculation of Read / Write Capacity Unit (DynamoDB).

* DynamoDB Accelerator (DAX) & Elaticache.

* ElastiCache strategies — Lazy-loading (also called ‘cache-aside’) & Write-Through

* S3 Encryption related questions

* Secured way to share files with others in S3: Use pre-signed URL & Use bucket policy.

* In S3:
    1. One single PUT operation is maximum 5GB. If the uploaded file is larger than 5GB, you need to use a multipart upload API.
    
    2. For an individual object — maximum 5TB in total.

    3. The total volume of data and the number of objects you can store are unlimited.

* Trouble-shooting related questions, for example:

    1. Add ‘Exponential backoff’ to the application logic can solve ‘Throttling Exception errors’ when writing items to DynamoDB tables.

    2. If the application stops responding, Elastic Load Balancing responds with ‘504 Error (Gateway Timeout)’, this means a server-side problem instead of ELB.

    3. When a user attempts to call the API using a new API key, the user receives a ‘403 Forbidden Error’, one possible solution might be: call the ‘importAPIkeys’ to import the newly created API keys.

* What tool you use to authenticate your applications against a web ID provider like Facebook — Cognito (especially for mobile applications).

    1. Cognito uses ‘User Pools’ to manage sign-up & sign-in.
    
    2. Cognito uses ‘Identity Pools’ to create unique identities.

    3. Cognito uses ‘Push Synchronisation’ to push updates and synchronise across multiple devices.

* By default, CloudWatech can’t see how much storage space is left or how much is still available — RAM Utilisation is a custom metric. Default metrics consist of CPU, Network, Disk and Status Check.

* SQS & SNS & SES:
    
    1. SQS is a pull-based service. The maximum message (in size) is 256KB. The default retention period is 4 days and a maximum of 14 days. Default Visibility Timeout is 30 seconds and a maximum of 12 hours. SQS delayed queues (postpone the delivery of the new messages), the default delay for a queue is 0 second and a maximum delay of 15 minutes. Difference between ‘Short-Polling’ and ‘Long-Polling’.

    2. SNS is a push-based service (follows ‘publish-subscribe’ messaging paradigm). It supports various formats including SMS, Email, SQS queues and any HTTP endpoint.

    3. SES only supports Emails.

* The difference between Kinesis Streams and Kinesis Firehose.

* Definition of ‘Shard’ in Kinesis Streams (The total capacity of the stream is the sum of the capacity of its shards).

Those notes helped me immensely in the exam (I apologise if the order seems a bit random), some of them are from AWS documentation, some are summarised by myself. In the exam, around 85% of the questions are scenario-based, and I found questions with multiple are harder than those with a single choice.

Based on different levels of experience in AWS, your exam preparation process might vary, and the topics you will encounter in the real exam might differ as well. But I do hope you find this useful and please feel free to share your experiences and thoughts after completing your exam. Good luck!
