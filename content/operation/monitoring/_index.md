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

Amazon CloudWatch is a monitoring service for AWS cloud [resources] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/aws-services-cloudwatch-metrics.html) and the applications you run on AWS. You can collect and [track metrics] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html), create [dashboards] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html), collect and monitor log files, [set alarms] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html), and automatically react to changes in your AWS resources. 

You can watch the video below for a quick overview of Amazon Cloudwatch.

{{< youtube id="a4dhoTQCyRA" >}}

Amazon CloudWatch is essentially a metrics repository. To visualize, an AWS service—such as Amazon EC2—puts metrics into the repository, and you retrieve statistics based on those metrics. If you put your own custom metrics into the repository, you can retrieve statistics on these metrics as well.

<img src="C:\Users\mariamdn\Desktop\Baseline photos">

## Monitoring Amazon Cloudwatch 

Monitoring is important in maintaining the reliability, availability, and performance of your AWS solutions. You should collect data from all of the parts in your infrastructure so that you can more easily debug a multi-point failure if one occurs.

As every infrastructure differs, you should create a monitoring plan that should include: goals for monitoring, resources to monitor, frequency of monitoring, tools to use and notifications. After you defined your monitoring goals and created your monitoring plan, the next step is to establish a baseline performance in your environment.

***Amazon Cloudwatch Metrics***

To establish a baseline, you need to understand what metrics you can monitor, and decide within your organization how detailed you want to monitor. You can find the detailed metrics for EC2, Application Load Balancer (ALB) and RDS in the documentations:

   1. [EC2] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html) metrics: including instance (CPU utilization, byte read/write etc) and CPU credits.
   2. [Application Load Balancer] (https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-cloudwatch-metrics.html) metrics: including Active connection count, condumed LCUs and healthy host count.
   3. [RDS] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/MonitoringOverview.html) metrics: including etwork throughput, client connections, I/O for read, write, or metadata operations, and burst credit balances.

AWS Cloudwatch can monitor over 700 metrics from over 80 [services] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/aws-services-cloudwatch-metrics.html). You can choose the metrics and follow the steps [here] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/viewing_metrics_with_cloudwatch.html) to view them all. You can also search within all of the metrics in your account using targeted search terms by following this [guide] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/finding_metrics_with_cloudwatch.html).

***Amazon Cloudwatch Dashboard***

Once you determine the metrics you want to monitor and the baseline performance you are comfortable with, you can consolidate them in a dashboard for easier tracking. 

Amazon CloudWatch dashboards are customizable home pages in the CloudWatch console that you can use to monitor your resources in a single view, even those resources that are spread across different Regions. You can use CloudWatch dashboards to create customized views of the metrics and alarms for your AWS resources. You can follow this [tutorial] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_dashboard.html) on how to setup a basic dashboard.

Watch the video below to have a visual understanding to monitor multiple resources at once, view automatic dashboards that can be dynamically filtered, or create your own custom dashboards.

{{< youtube id="I7EFLChc07M" >}}

After creating your dashboard, you can have simple edits such as [adding/removing graphs] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/add_remove_graph_dashboard.html), [resizing graphs] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/move_resize_graph_dashboard.html) graphs, [editing graphs] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/edit_graph_dashboard.html)  and setting up [cross-account cross-region dashboards] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_xaxr_dashboard.html).

***Amazon Cloudwatch Alarms***

A CloudWatch Alarm is always in one of three states: OK, ALARM, or INSUFFICIENT_DATA. When the metric is within the range that you have defined as acceptable, the Monitor is in the OK state. When it breaches a threshold it transitions to the ALARM state. If the data needed to make the decision is missing or incomplete, the monitor transitions to the INSUFFICIENT_DATA state.

Alarms watch metrics and execute actions by publishing notifications to [Amazon SNS] (https://aws.amazon.com/sns/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) topics or by initiating Auto Scaling actions. SNS can deliver notifications using HTTP, HTTPS, Email, or an [Amazon SQS] (https://aws.amazon.com/sqs/) queue. Your application can receive these notifications and then act on them in any desired way.

Watch the seamless integration of AWS Cloudwatch and SNS (Email) in the tutorial below.

{{< youtube id="YC-sVSbeowA" >}}

Here are some of the baseline alarm setups that you can do:
   1. Setup [SNS] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/US_SetupSNS.html) Notifications 
   2. Create a CloudWatch Alarm Based on a [Static Threshold] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ConsoleAlarms.html)
   3. Creating a CloudWatch Alarm Based on [Anomaly Detection] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Create_Anomaly_Detection_Alarm.html)
   4. Creating a [Billing Alarm] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/monitor_estimated_charges_with_cloudwatch.html) to Monitor Your Estimated AWS Charges

If you have the time, we recommend watching the video below showing how BBC used Amazon CloudWatch.

{{< youtube id="uuBuc6OAcVY" >}}

You can check the comprehensive list of ***Customere References*** [here] (https://aws.amazon.com/cloudwatch/customers/) too.

## Labs and Hands-on Resources

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