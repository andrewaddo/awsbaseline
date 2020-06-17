+++
title = "Protecting Against DDOS Attacks"
date =  2020-06-13T16:20:15+08:00
weight = 2
+++

This chapter discusses DDOS attacks and the AWS services you can use to combat against them. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are expected outcomes?

1. Learn about AWS Shield and WAF
2. Successfully setup an environment resilient to DDOS attacks

### Pre-requisites

1. None

### What is a DDOS Attack

A Denial of Service (DoS) attack is a malicious attempt to affect the availability of a targeted system, such as a website or application, to legitimate end users. Typically, attackers generate large volumes of packets or requests ultimately overwhelming the target system. In case of a Distributed Denial of Service (DDoS) attack, and the attacker uses multiple compromised or controlled sources to generate the attack.

You can find more information [here](https://aws.amazon.com/shield/ddos-attack-protection/).

To understand how you can protect yourself from DDOS attacks, you can watch the [video](https://www.youtube.com/watch?v=d0EE1HuZSEU) below for an overview.
{{< youtube id="d0EE1HuZSEU" >}}

### Best Practices for DDOS Resiliency

There are different types of attacks and AWS provides different services for each of them.
[Image: image.png]

#### Infrastructure Layer Attacks

Infrastructure Layer Attacks The most common DDoS attacks, UDP reflection attacks and SYN floods, are infrastructure layer attacks. An attacker can use either of these methods to generate large volumes of traffic that can inundate the capacity of a network or tie up resources on systems like a server, firewall, IPS, or load balancer. While these attacks can be easy to identify, to effectively mitigate them, you must have a network or systems that scale up capacity more rapidly than the inbound traffic flood.

#### Application Layer Attacks

An attacker may target the application itself by using a layer 7 or application layer attack. In these attacks, similar to SYN flood infrastructure attacks, the attacker attempts to overload specific functions of an application to make the application unavailable or extremely unresponsive to legitimate users. 

You can watch the [video](https://www.youtube.com/watch?v=HnoZS5jj7pk&t=3s) below to find out more:
{{< youtube id="HnoZS5jj7pk" >}}
It is important to learn the mitigation techniques for different attacks. You can find this comprehensive documentation containing DDOS Best Practices [here](https://d1.awsstatic.com/whitepapers/Security/DDoS_White_Paper.pdf).

### What is AWS Shield and Why You Should Use It

AWS Shield is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS. AWS Shield provides always-on detection and automatic inline mitigations that minimize application downtime and latency, so there is no need to engage AWS Support to benefit from DDoS protection. There are two tiers of AWS Shield - Standard and Advanced.

**Standard protection** provides automatic defense against the most common network and transport layer DDoS attacks for any AWS resource, in any AWS Region. It provides comprehensive defense against all known network and transport layer attacks when using Amazon CloudFront and Amazon Route 53.

**Advanced Protection** provides attack visibility and enhanced detection. It also has Cost Protection to mitigate economic attack vectors with fast escalation to the AWS DDoS Response Team (DRT) to assist with complex edge case.

**Pricing:** Standard protection is available to ALL AWS customers at no additional cost. Advanced protection is a paid service that provides additional protections, features, and benefits.

You can find out more in this [documentation](https://docs.aws.amazon.com/waf/latest/developerguide/ddos-overview.html).

### What is AWS WAF and Why You Should Use It

AWS WAF is a web application firewall that helps protect your web applications or APIs against common web exploits that may affect availability, compromise security, or consume excessive resources. 

AWS WAF gives you control over how traffic reaches your applications by enabling you to create security rules that block common attack patterns, such as SQL injection or cross-site scripting, and rules that filter out specific traffic patterns you define. 

AWS WAF provides: web traffic filtering with custom rules, malicious request blocking and active monitoring and tuning.

You can watch the [video](https://www.youtube.com/watch?v=2lAcE3NA2UU) below to understand more
{{< youtube id="2lAcE3NA2UU" >}}

### HANDS-ON LAB TO PROTECT AGAINST DDOS ATTACKS

#### Activating AWS Shield Advanced for Your Application (Step-by-step Guide)

This [documentation](https://docs.aws.amazon.com/waf/latest/developerguide/enable-ddos-prem.html) will show you how to activate AWS Shield Advanced

#### Protecting against network and host-level attacks with AWS WAF

This [lab](https://wellarchitectedlabs.com/Security/200_CloudFront_with_WAF_Protection/README.html) will show you hot setup AWS WAF and Amazon Cloudfront to protect against network based attacks



