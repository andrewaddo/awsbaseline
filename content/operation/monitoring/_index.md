+++
title = "Monitoring Your Applications"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This chapter discusses the importance of monitoring your applications with Amazon Cloudwatch, and how to set it up. You will find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are expected outcomes?

1. Understand how to monitor your EC2, Application Load Balancer and RDS with Cloudwatch
2. Successfully setup Cloudwatch monitoring and health checks

### Pre-requisites

1. None

## Monitoring with Amazon Cloudwatch

Monitoring is an important part of maintaining the reliability, availability, and performance of your Amazon Elastic Compute Cloud (Amazon EC2) instances and your AWS solutions. You should collect monitoring data from all of the parts in your AWS solutions so that you can more easily debug a multi-point failure if one occurs.

### What is Amazon Cloudwatch

Amazon CloudWatch is a monitoring service for AWS cloud resources and the applications you run on AWS. You can use Amazon CloudWatch to collect and track metrics, collect and monitor log files, set alarms, and automatically react to changes in your AWS resources. 

You can watch the video below for a quick overview of Amazon Cloudwatch.

{{< youtube id="a4dhoTQCyRA" >}}

## Monitoring with Amazon Cloudwatch

It is important that you decide what additional metrics are important to your business for monitoring.

You can find the baseline metrics to monitor for [EC2] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring_ec2.html), [ALB](http://monitor%20your%20application%20load%20balancer%20with%20amazon%20cloudwatch/) (Application Load Balancer) and [RDS] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.LoggingAndMonitoring.html).


## Setting Up Resource Monitoring

### Monitoring Your Resources with AWS Cloudwatch

This [lab] (https://wellarchitectedlabs.com/performance-efficiency/100_labs/100_monitoring_with_cloudwatch_dashboards/) will show you how to access Cloudwatch Dashboard to monitor your resources

### Enable or Disable detailed Monitoring for Your Instances 

This [documentation] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-cloudwatch-new.html) will help you turn on monitoring for your EC2 instances


### Creating Notifications When Resource Changes are Made with Amazon Cloudwatch

This [lab] (https://aws.amazon.com/premiumsupport/knowledge-center/iam-cloudwatch-sns-rule/) will help you create notifications for Cloudwatch

### Setting Enhanced Monitoring for Your RDS Application 

This [documentation] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.OS.html) will show you how to enable Enhanced Monitoring for your DB instance

## Diving Deep: Additional Resources

### Understanding Cloudwatch Logs

This [course] (https://www.aws.training/Details/Video?id=16391) intoduces Amazon CloudWatch Logs, share common use cases, and demonstrate the service.

### Understanding CloudTrail

This is [course] (https://www.aws.training/Details/Video?id=16453) intoduces Amazon CloudWatch Logs, benefits, and demonstrate the service.