+++
title = "Three-Tier Reference Architecture"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This section discusses the importance of building a 3-tier application and the best practices you can follow. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand the components of a 3-tier application

### Pre-requisites

1. None

## Overview of a 3-tier Architecture

The 3-tier application is a cornerstone architecture that provides a general framework to ensure decoupled and independently scalable application components that can be separately developed, managed, and maintained (often by distinct teams).

It generally consists of the following components:
* **Presentation tier**: the component that user directly interacts with (web page, mobile app UI, etc.)
* **Logic tier**: the code required to translate user actions to application functionality (CRUD database operations, data processing, etc.)
* **Data tier**: the storage media (databases, object stores, caches, file systems, etc.) that hold the data relevant to the application 

The image below is the recommended architecture that you can follow.

![Cloudwatch](../img/3 tier.png)

### Security Best Practices

1. **Access control**

Control access to infrastructure using [AWS Identity and Access Management (IAM)] (https://www.awsbaseline.com/security/iam/).

2. **Data protection**

Encrypt data at rest (e.g. RDS, S3) with [AWS Key Management Service (KMS)] (https://aws.amazon.com/kms/). 

You can watch the [video] (https://www.youtube.com/watch?v=-5MPXHvKDnc) below to understand more about KMS and how to set it up.

{{< youtube id="-5MPXHvKDnc" >}}

Encrypt data in transit with TLS using certificates provided by [AWS Certificate Manager] (https://aws.amazon.com/certificate-manager/). 

Enhance data encryption protection with hardware security module using [AWS CloudHSM] (https://aws.amazon.com/cloudhsm/).

3. **Application protection**

Harden OSes following standards (e.g. CIS). Adopt antivirus and code scanner for vulnerability detection.

4. **Network protection**

Mitigate [Distributed Denial of Service (DDoS)] (https://www.awsbaseline.com/security/ddos/) with [AWS Shield] (https://aws.amazon.com/shield/) (Network and Transport layers) and [AWS Web Application Firewall (WAF)] (https://aws.amazon.com/waf/) (Application layer) in Open Systems Interconnection (OSI) Model. 

Protect outbound communication with [NAT gateway] (https://aws.amazon.com/premiumsupport/knowledge-center/nat-gateway-vpc-private-subnet/) and [AWS Direct Connect] (https://aws.amazon.com/directconnect/).

5. **Limit exposure**

Serve inbound communication through [Application Load Balancer] (https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html) and Proxies placed in the DMZ (Public subnet and security group). 

Place sensitive components (application, database) in the protected layers (Private subnets and security groups). Configure security groups to allow only required accesses.

6. **Logging and auditing**

Collect and analyze logs using [Amazon CloudWatch] (https://www.awsbaseline.com/operation/monitoring/). Collect and analyze audit records using [AWS CloudTrail] (https://aws.amazon.com/cloudtrail/).

7. **Compliance** 

Maintain compliant state of the infrastructure using [AWS Config] (https://www.awsbaseline.com/security/compliance/). Configure notifications to be triggered when the desired state changes.


### Reliability Best Practices

**Fault tolerance and Disaster recovery**
Maintain business continuity by multi-AZs setup with auto-scale to recover in case of fault or disaster events. You can check more [here] (https://www.awsbaseline.com/reliability/high-availability/).


### Operational Best Practices

**Security Information Event Management**

Set up security information and event management to have real-time analysis and alerts in case of security risks. Define runbooks and conduct gamedays to maintain resiliency. You can leverage of IDS and IPS for this.

