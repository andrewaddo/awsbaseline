+++
title = "Schedule Resource Stop/Start"
date =  2020-06-13T05:40:01+08:00
weight = 5
+++

The AWS Instance Scheduler is a simple AWS-provided solution that enables customers to easily configure custom start and stop schedules for their Amazon Elastic Compute Cloud (Amazon EC2) and Amazon Relational Database Service (Amazon RDS) instances. The solution is easy to deploy and can help reduce operational costs for both development and production environments. Customers who use this solution to run instances during regular business hours can save up to 70% compared to running those instances 24 hours a day.

### What are expected outcomes?

1. Immediate actions that can reduce your AWS costs

### Pre-requisites

1. A workload with either EC2 instances or RDS or both

### Step-by-Step Guide

1. Access the [Instance Scheduler] (https://aws.amazon.com/solutions/implementations/instance-scheduler/).
1. Review the architecture and understand which components will be deployed.
1. Follow the instructions from [here](https://docs.aws.amazon.com/solutions/latest/instance-scheduler/deployment.html).
1. Among many strategies to schedule stopping and starting resources, a quick-win strategy is to shutdown resources during weekend and evening time (e.g. 17-9)
1. Review the saving before and after using Instance Scheduler

![Image: InstanceScheduler.png](../img/InstanceScheduler.png)