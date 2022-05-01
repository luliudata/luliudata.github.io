---
title:  "Getting started with AWS Step Functions 01"
mathjax: true
author: Lu
category: AWS
---

### What is Step Functions?

[AWS Step Functions](https://aws.amazon.com/step-functions/) 
is a serverless orchestration service that allows us to combine 
AWS Lambda functions and other AWS services to build applications.

### Why Step Functions?

Before we dive in, first, we might want to understand why we need a 'serverless orchestration service'. 
If we look at the modern applications we build nowadays, most likely, we can see them consisting of microservices. 
The advantage of the microservices is that each microservice can be built, 
deployed and maintained individually, which increases the scalability and fault-tolerance of the whole application. 
What's more, in an application, each microservice needs to talk to each other. 
This is where the step functions become very handy and useful to link different 
components together as a serverless orchestration service. 
It is easier to manage each component with Step Functions in the workflow, 
and we can also visualise the workflow in the AWS console or on our local machine (e.g., VSCode + AWS Toolkit extension). 
Step Functions also has error handling, retry & catch mechanism, it is also integrated with CloudWatch and X-Ray for us to 
be able to monitor its performance and help us debug.

In this blog, I'll assume you already have some basic understanding of the below AWS services such as Lambda and Glue.
The most common use cases for Step Functions are probably the integration with Lambda functions. 
Step Functions also supports the integration with AWS Glue and SageMaker. For example,
it can start a Glue job run or a SageMaker Batch Transform job. It can also run an Amazon ECS (Elastic Container Service) task, etc.

![image](https://user-images.githubusercontent.com/44141273/164944985-4a89c4ee-2405-4ffd-b781-f4f4b8ba388d.png)

Please check out [this page](https://docs.aws.amazon.com/step-functions/latest/dg/connect-to-services.html) 
to see what other AWS services are supported by Step Functions.

### How to define Step Functions state machines?

Below is a simple Step Function state machine:

![image](https://user-images.githubusercontent.com/44141273/164947490-e3e1ae83-fb37-4978-9bd9-bef8c98ebbcc.png)

It simply invokes a Lambda function and then starts a Glue job run.

There are a couple of different approaches to constructing the state machines. 
Below are two ways that I normally use:

* In AWS Step Functions console -> click right top 'Create State Machine' ->
select 'Design your workflow visually'

This allows us to use 'Workflow Studio' to define our state machines visually:

![image](https://user-images.githubusercontent.com/44141273/166143304-cbf8b639-56e1-4c79-97e4-dea9114c2bd8.png)

* Instead of using AWS console, we can also construct the state machines locally
with the help of Visual Studio Code + [AWS Toolkit extension](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/welcome.html?icmpid=docs_tookitvscode_console):

![image](https://user-images.githubusercontent.com/44141273/166143535-a2a9ea20-5c73-4e51-a629-f5e87854f438.png)

(Code example reference: [Error handling in Step Functions
](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-error-handling.html#error-handling-examples))

The state machine definitions use the Amazon States Language which is a JSON-based, 
structured language (see the left side of the image above).

The state machine definition uses a concept called 'States', which is basically the elementS/steps
that we use to define the actions in state machines. 
According to Step Function developer guide: "Individual states can make decisions based on their input, perform actions, and pass output to other states."
This will be covered in the follow-up blog 'Getting started with AWS Step Functions 02'. I'll go through some of the commonly-used
states and explain the usages based on our example state machine we used in this blog.


### Resources

* [AWS Step Function developer guide](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)
* [Amazon States Language](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html)
