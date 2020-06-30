+++
title = "Monitoring Your Applications"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This chapter discusses the importance of monitoring your applications with Amazon Cloudwatch, and how to set it up. You will find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand how to monitor your EC2, Application Load Balancer and RDS with Cloudwatch
2. Successfully setup Cloudwatch monitoring and health checks

### Pre-requisites

1. None

### What is Amazon Cloudwatch

Amazon CloudWatch is a monitoring service for AWS cloud [resources] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/aws-services-cloudwatch-metrics.html) and the applications you run on AWS. You can collect and track [metrics] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html), create [dashboards] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_dashboard.html), collect and monitor log files, set [alarms] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html), and automatically react to changes in your AWS resources. 

You can watch the video below for a quick overview of Amazon Cloudwatch.

{{< youtube id="a4dhoTQCyRA" >}}

Amazon CloudWatch is essentially a metrics repository. To visualize, an AWS service—such as Amazon EC2—puts metrics into the repository, and you retrieve statistics based on those metrics. If you put your own custom metrics into the repository, you can retrieve statistics on these metrics as well.

<img src="C:\Users\mariamdn\Desktop\Baseline photos">

## Monitoring with Amazon Cloudwatch

Monitoring is important in maintaining the reliability, availability, and performance of your AWS solutions. You should collect data from all of the parts in your infrastructure so that you can more easily debug a multi-point failure if one occurs.

As every infrastructure differs, you should create a monitoring plan that should include: goals for monitoring, resources to monitor, frequency of monitoring, tools to use and notifications. After you defined your monitoring goals and created your monitoring plan, the next step is to establish a baseline performance in your environment.

To establish a baseline, you need to understand what metrics you can monitor, and decide within your organization how detailed you want to monitor. You can find the metrics for [EC2] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html), [ALB] (https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-cloudwatch-metrics.html) and [RDS] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/MonitoringOverview.html) in the documentations.

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