+++
title = "Improve Performance with Caching"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This section discusses the importance of using Elasticache and Cloudfront to improve the performance of your applications. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand Elasticache and Cloudfront services
2. Successfully setup Elasticache and Cloudfront for your application

### Pre-requisites

1. None

## What is Elasticache

[Elasticache] (https://aws.amazon.com/elasticache/) is a web service that makes it easy to set up, manage, and scale a distributed in-memory cache environment in the cloud. Elasticache provides a high-performance, resizable, and cost-effective caching solution, while removing the complexity associated with deploying and managing a distributed cache environment.

ElastiCache works with other Amazon Web Services (such as [Amazon EC2] (https://aws.amazon.com/ec2/), [CloudWatch] (https://aws.amazon.com/cloudwatch/), and [Amazon SNS] (https://aws.amazon.com/sns/)) to provide a secure, high-performance and managed in-memory caching.

To start, watch the [video] (https://www.youtube.com/watch?v=QxcB53mL_oA&t=159s) below video that discusses Elasticache, use cases, caching strategies and best practices.


{{< youtube id="QxcB53mL_oA&t=159s" >}}


### What is Cloudfront 

[Amazon CloudFront] (https://aws.amazon.com/cloudfront/) is a web service that speeds up distribution of your static and dynamic web content (such as .html, .css, .js, and image files) to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations. 

You can watch the [video] (https://www.youtube.com/watch?v=AT-nHW3_SVI) below to have a quick overview of Cloudfront.


{{< youtube id="AT-nHW3_SVI" >}}

CloudFront speeds up the distribution of your content by routing each user request through the AWS backbone network to the edge location that can best serve your content. Typically, this is a CloudFront edge server that provides the fastest delivery to the viewer. 

Using the AWS network dramatically reduces the number of networks that your users' requests must pass through, which improves performance. Users get lower latency—the time it takes to load the first byte of the file—and higher data transfer rates.

If you are interested to learn more, you can read this [documentation] (https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html).

## Labs and Hands-on Resources

Looks like you are all set! To help you implement, here are some labs that we recommend you can practice on.

### Creating Amazon S3 Cache with Amazon Elasticache for Redis

This sample [project] (https://github.com/aws-samples/amazon-S3-cache-with-amazon-elasticache-redis) demonstrates how you can cache Amazon S3 objects with Amazon ElastiCache for Redis . This project also uses AWS CloudFormation & AWS Cloud9 as means to deploy, build and run this tutorial, although you can run this in your own environments as well.

### Creating a Cloudfront Distribution for Amazon S3

This [lab] (https://wellarchitectedlabs.com/security/100_labs/100_cloudfront_with_s3_bucket_origin/) will help you improves S3 access time using caching.

### Creating a Cloudfront Distribution for Amazon S3

This [video] (https://www.youtube.com/watch?v=DiIaoIcoKNY) tutorial will help you accelerate access of static content from Amazon S3 using Amazon Cloudfront.

{{< youtube id="DiIaoIcoKNY" >}}

## Diving Deep: Additional Resources

**Ensuring Cloudfront serve updated content from S3**
You can find the information and resolution in this [guideline] (https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serving-outdated-content-s3/)