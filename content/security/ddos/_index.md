+++
title = "Protecting Against DDOS Attacks"
date =  2020-06-13T16:20:15+08:00
weight = 2
+++

This section discusses DDOS attacks and the AWS services you can use to combat against them. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Learn about AWS Shield and WAF.
2. Successfully setup an environment resilient to DDOS attacks.

### Pre-requisites

1. None

### What is a DDOS Attack

A Denial of Service (DoS) attack is a deliberate attempt to make your website or application unavailable to users, such as by looding it with network traffic. The attacker uses multiple sources— such as distributed groups of malware infected computers, routers, IoT devices, and other endpoints—to orchestrate an attack against a target. The attacker's goal is to consume large amounts of network bandwidth or tie up other system resources, disrupting access for legitimate users. 

DDoS attacks can be segregated by which [OSI Layer](https://aws.amazon.com/shield/ddos-attack-protection/) they attack.

To understand how you can protect yourself from DDOS attacks, you can watch the [video](https://www.youtube.com/watch?v=d0EE1HuZSEU) below for an overview.
{{< youtube id="d0EE1HuZSEU" >}}

### Best Practices for DDOS Resiliency

#### AWS Shield

[AWS Shield] (https://aws.amazon.com/shield/) is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS.There are two tiers of AWS Shield - Standard and Advanced.

**Standard protection** provides automatic defense against the most common network and transport layer DDoS attacks for any AWS resource, in any AWS Region. It provides comprehensive defense against all known network and transport layer attacks when using [Amazon CloudFront] (https://aws.amazon.com/cloudfront/) and [Amazon Route 53] (https://aws.amazon.com/route53/).

Note: All AWS customers benefit from the automatic protections of AWS Shield Standard at
no additional charge. AWS Shield Standard defends against most common, frequently
occurring network and transport layer DDoS attacks that target your web site or
applications. 

**Advanced Protection** provides attack visibility and enhanced detection. It also has Cost Protection to mitigate economic attack vectors with fast escalation to the AWS DDoS Response Team (DRT) to assist with complex edge case.

**Pricing:** Standard protection is available to ALL AWS customers at no additional cost. Advanced protection is a paid service that provides additional protections, features, and benefits.

You can read this [documentation] (https://docs.aws.amazon.com/waf/latest/developerguide/ddos-overview.html#ddos-help-me-choose) to help you decide between staying with Standard Protection or upgrading to Advance.

You can watch the [video](https://www.youtube.com/watch?v=HnoZS5jj7pk&t=3s) below to find out more:
{{< youtube id="HnoZS5jj7pk" >}}

#### Elastic Load Balancing

Large DDoS attacks can overwhelm the capacity of a single Amazon EC2 instance, so adding load balancing can help your resiliency. 

With [Elastic
Load Balancing (ELB)] (https://aws.amazon.com/elasticloadbalancing/), you can reduce the risk of overloading your application by distributing traffic across many backend instances. ELB can scale automatically, allowing you to manage larger volumes when you have unanticipated extra traffic, for example, due to flash crowds or DDoS attacks.

#### AWS WAF 

When your application runs on AWS, you can leverage both Amazon CloudFront and
AWS WAF to help defend against application layer DDoS attacks.

[AWS WAF] (https://aws.amazon.com/waf/) is a web application firewall that helps protect your web applications or APIs against common web exploits that may affect availability, compromise security, or consume excessive resources.

AWS WAF gives you control over how traffic reaches your applications by enabling you to create security rules that block common attack patterns, such as SQL injection or cross-site scripting, and rules that filter out specific traffic patterns you define.

AWS WAF provides: web traffic filtering with custom rules, malicious request blocking and active monitoring and tuning.

You can watch the [video](https://www.youtube.com/watch?v=2lAcE3NA2UU) below to understand more
{{< youtube id="2lAcE3NA2UU" >}}

### Setting Up Against DDOS Attacks

#### Protecting against network and host-level attacks with AWS WAF

This [lab](https://wellarchitectedlabs.com/security/200_labs/200_basic_ec2_with_waf_protection/) will show you how to set up AWS WAF to protect your workload behind Application Load Balancer.

This [lab](https://wellarchitectedlabs.com/Security/200_CloudFront_with_WAF_Protection/README.html) will show you how to set up AWS WAF and Amazon Cloudfront to protect against network based attacks.

#### Activating AWS Shield Advanced for Your Application (Step-by-step Guide)

This [documentation](https://docs.aws.amazon.com/waf/latest/developerguide/enable-ddos-prem.html) will show you how to activate AWS Shield Advanced.
