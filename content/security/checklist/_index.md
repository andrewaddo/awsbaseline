+++
title = "Security checklist"
date =  2020-06-13T16:20:15+08:00
weight = 5
+++

## Introduction

The goal of the minimum security baseline is to ensure key AWS Security Services and configuration settings are being enabled and leveraged. Many of the controls below can be applied at an AWS account level or "platform" level.
AWS Service specific security controls (Redshift, EMR, S3, RDS for example) should also be considered as part of your archiecture design review. 

[Review the AWS Security Documentation for service specific configurations.](https://docs.aws.amazon.com/security/)

## Asset Management

Control Objective: Ensure accurate inventory of all AWS accounts, systems, and resoruces to inform the security team to ensure completeness of security coverage.

* All accounts must have accurate account contact information (billing, operations, security)
* All accounts must be enrolled in the AWS Organization structure for centralized management
* Enable AWS Config for inventory management
* Use AWS Systems Manager Inventory to inventory software and applications

## Identity & Access Management

Control Objective: Ensure only authenticated and authorised individuals have the ability to interact with AWS resources.

* First choice should be to federate identity and not use AWS IAM users (AWS SSO, Third-Party (Okta, Ping Identity) or On-Premises Identity Provider)
* All console access must have multi-factor authentication enforced
* Strong password policy must be enforced
* Long term access keys should be replaced with temporary credentials (IAM Assume Role)
* Long term access keys if required should be rotated regularly
* Users should have their own accounts. No shared user accounts
* Users should have permissions appropriate for their job role
* AWS IAM roles should be validated frequently (Review permissions)

## Detective Controls

* Enable Multi-region CloudTrails
* Enable Amazon GuardDuty
* Enable IAM Access Analyzer
* Enable Amazon S3 access logs
* Enable AWS Security Hub (Enable applicable compliance standard: Security Foundations, PCI-DSS, CIS Benchmark)
* Leverage and integrate Trusted Advisor findings
* Enable VPC Flow Logs
* Centralize all logs (Cloudtrail, config, GuardDuty, SecurityHub, VPC Flow Logs) to SOC and review and action on alerts

## Data Protection

* Data-at-rest is encrypted (KMS)
* Data-in-transit is encrypted (TLS + ACM)
* Backups are restored in secure non-deletable locations (WORM)
* Certificates are managed appropriately and renewed before expiry (Leverage ACM)
* Resources are private (S3, EBS Snapshots and Volumes, RDS Snapshots, etc)
* Public S3 buckets are denied by default at an account level
* Public S3 buckets that are required are whitelisted and reviewed for sensitive content, frequent attestation.
* Secrets/keys/tokens should not be hard-coded. Use AWS Secrets Manager to store application/database secrets.

## Infrastructure Security

* Patch your resources frequently (Optional: Use AWS Systems Manager to do this)
* Vulnerability scan compute resource frequently
* Security Groups should be limited to only required flows (inbound and outbound)
* Internet facing applications are protected by WAF and Shield
* Internet facing applications leverage Route53 for DNS
* Internet facing applications leverage CloudFront for CDN
* Management services (SSH, RDP, etc) are not exposed to Internet
* Private resources must be in a private subnet with Internet access only provided via Nat Gateway
* Optional: Resources connect out to the Internet via egress filtering/proxy to inspect traffic (Sophos UTM, Palo Alto, etc)
* Optional: Use AWS Systems Manager (Session Manager) to access production servers if ever needed. System Manager logs all commands executed on the production host to be reviewed by the security team.

## Incident Response

* All AWS accounts have read-only infosec role created and granted to infosec team
* All AWS accounts have break-glass admin infosec role created for emergency incident response
* All AWS accounts/workloads have IR and BCP plans documented and regularly tested
* Runbooks have been developed and documented for common incident events
* Incident alerting thresholds are established (CloudWatch Alarms, GuardDuty)

Credit: <https://www.cloudsecurity.asia/policy.html>
