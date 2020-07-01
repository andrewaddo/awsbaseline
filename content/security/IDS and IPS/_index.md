+++
title = "IDS and IPS Threat Detection"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This section will give you an introduction to AWS Identity Access Management (IAM) and and a step-by-step guide to setting it up. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand IDS and IPS
2. Understand Security Hub and GuardDuty

### Pre-requisites

1. AWS Account

## What are IDS and IPS

**Intrusion Detection Systems (IDS)** monitor networks and/or systems for malicious activity or policy violation, and report them to systems administrators or to a security information and event management (SIEM) system. 

**Intrusion Prevention Systems (IPS)** are positioned
behind firewalls and provide an additional layer of security by scanning and analyzing suspicious content for potential threats. Placed in the direct communication path, an IPS will take automatic action on suspicious traffic within the network.

These are the reasons why you need to implement IDS and IPS for your system:

* ***Detect Vulnerability in your EC2 Instances***: by monitoring inbound and outbound packets from the EC2 instance, and may evaluate system files for changes

* ***Protect Your EC2 Instances from Attacks***: by having e always-on detection to safeguard your EC2 instances

* ***Respond to Intrusion or Attacks Against your EC2 Instances***: by performing  threat analysts to rapidly assess the nature and extent of incidents and take the
proper measures to respond to it

Here are some [IDS/IPS solutions from AWS Marketplace] (https://aws.amazon.com/marketplace/solutions/infrastructure-software/ids-ips) that you can use and apply for your architecture.

## Amazon GuardDuty

Amazon GuardDuty is a continuous security monitoring service that analyzes and processes the following data sources: [VPC Flow Logs] (https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html), [AWS CloudTrail event logs] (https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events-console.html), and [DNS logs] (https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/logging-monitoring.html).

You can watch the [video] (https://www.youtube.com/watch?v=ocZjGirQT9A) below to have an overview of GuardDuty and how you can complement your IDS/IPS solutions.

{{< youtube id="ocZjGirQT9A" >}}

GuardDuty helps identify potentially unauthorized and malicious activities such as:
* Uses of exposed credentials
* Escalations of privileges
* Communication with malicious IP addresses, URLs, or domains
* Compromised EC2 instances serving malware or mining bitcoin
* Unauthorized nfrastructure deployments

GuardDuty informs you of the status of your AWS environment by producing security findings that you can view in the GuardDuty console or through [Amazon CloudWatch events] (https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_findings_cloudwatch.html). You can find the [pricing here] (https://aws.amazon.com/guardduty/pricing/).

## AWS Security Hub

AWS Security Hub provides you with a comprehensive view of your security state in AWS and helps you check your environment against security industry standards and best practices.

Security Hub collects security data from across AWS accounts, services, and supported third-party partner products and helps you analyze your security trends and identify the highest priority security issues.

You can [video] (https://www.youtube.com/watch?v=K7V5kNBjGCI&t=6s) below to understand more about Security Hub and how it helps in detecting threats.

{{< youtube id="K7V5kNBjGCI&t=6s" >}}

When you enable Security Hub, it begins to consume, aggregate, organize, and prioritize findings from AWS services that you have enabled, such as [Amazon GuardDuty] (https://aws.amazon.com/guardduty/), [Amazon Inspector] (https://aws.amazon.com/inspector/), and [Amazon Macie] (https://aws.amazon.com/macie/). 

You can also [integrate AWS Security Hub with partner security products and solutions] (https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-partner-providers.html). 

## Labs and Hands-On Resources

### Enabling GuardDuty an Security Hub

You can check these tutorials  to setup [GuardDuty] (https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_settingup.html) and [Security Hub] (https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-settingup.html).

### Testing against multiple intrusion scenarios

These [labs] (https://hands-on-guardduty.awssecworkshops.com/) will walk you through a scenario covering threat detection and remediation using Amazon GuardDuty. The labs has 3 components:
* [Compromised EC2 Instance] (https://hands-on-guardduty.awssecworkshops.com/scenario1/)
* [Compromised IAM Credentials] (https://hands-on-guardduty.awssecworkshops.com/scenario2/)
* [IAM Role Exfiltration] (https://hands-on-guardduty.awssecworkshops.com/scenario3/)

### Monitoring Host-Based Intrusion Detection System Alerts

You can follow this [tutorial] (https://aws.amazon.com/blogs/security/how-to-monitor-host-based-intrusion-detection-system-alerts-on-amazon-ec2-instances/) to leverage on [Amazon Cloudwatch Logs] (https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html) to collect and aggregate alerts.