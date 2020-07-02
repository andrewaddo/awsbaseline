+++
title = "Security Checklist"
date =  2020-06-13T16:20:15+08:00
weight = 5
+++

## Introduction

The goal of the minimum security baseline is to ensure key AWS Security Services and configuration settings are being enabled and leveraged. Many of the controls below can be applied at an AWS account level or "platform" level.
AWS Service specific security controls ([Redshift](https://aws.amazon.com/redshift/), [EMR] (https://aws.amazon.com/emr/#:~:text=Amazon%20EMR%20is%20the%20industry,%2C%20Apache%20Hudi%2C%20and%20Presto.), [S3] (https://aws.amazon.com/s3/), [RDS] (https://aws.amazon.com/rds/) for example) should also be considered as part of your archiecture design review. 

[Review the AWS Security Documentation for service specific configurations.](https://docs.aws.amazon.com/security/)

## Asset Management

Objective: Ensure accurate inventory of all AWS accounts, systems, and resourcess to inform the security team to ensure completeness of security coverage.

* All accounts must have accurate account contact information (billing, operations, security)
* All accounts must be enrolled in the [AWS Organization] (https://www.awsbaseline.com/security/organizations/) structure for centralized management
* Enable [AWS Config] (https://www.awsbaseline.com/security/compliance/) for inventory management
* Use [AWS Systems Manager Inventory] (https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-inventory.html) to inventory software and applications. You can watch these Inventory Services [1] (https://www.youtube.com/watch?v=z4n3Oh1MJDQ) and [2] (https://www.youtube.com/watch?v=0GgSTttRENU) videos to understand more.



## Identity & Access Management

Objective: Ensure only authenticated and authorised individuals have the ability to interact with AWS resources.

* First choice should be to [federate identity] (https://aws.amazon.com/identity/federation/) and not use AWS IAM users (AWS SSO, Third-Party (Okta, Ping Identity) or On-Premises Identity Provider)
* All console access must have multi-factor authentication enforced
* Strong password policy must be enforced
* Long term access keys should be replaced with temporary credentials (IAM Assume Role)
* Long term access keys if required should be rotated regularly
* Users should have their own accounts. No shared user accounts
* Users should have permissions appropriate for their job role
* AWS IAM roles should be validated frequently (Review permissions)

## Detective Controls

* Enable Multi-region [CloudTrails] (https://aws.amazon.com/cloudtrail/)
* Enable [Amazon GuardDuty] (https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_settingup.html)
* Enable [IAM Access Analyzer] (https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-getting-started.html)
* Enable [Amazon S3 access logs] (https://docs.aws.amazon.com/AmazonS3/latest/user-guide/server-access-logging.html)
* Enable [AWS Security Hub] (https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-settingup.html) (Enable applicable compliance standard: Security Foundations, PCI-DSS, CIS Benchmark)
* Leverage and integrate [Trusted Advisor] (https://aws.amazon.com/premiumsupport/technology/trusted-advisor/) findings
* Enable [VPC Flow Logs] (https://aws.amazon.com/blogs/aws/vpc-flow-logs-log-and-view-network-traffic-flows/#:~:text=Enabling%20VPC%20Flow%20Logs,tab%20of%20the%20VPC%20dashboard.)
* Centralize all logs (Cloudtrail, config, GuardDuty, SecurityHub, VPC Flow Logs) to SOC and review and action on alerts

## Data Protection

* Data-at-rest is encrypted ([KMS] (https://aws.amazon.com/kms/))
* Data-in-transit is encrypted (TLS + [AWS Certificate Manager] (https://aws.amazon.com/certificate-manager/))
* Backups are restored in secure non-deletable locations ([WORM] (https://aws.amazon.com/blogs/aws/glacier-vault-lock/))
* Certificates are managed appropriately and renewed before expiry (Leverage [AWS Certificate Manager] (https://aws.amazon.com/certificate-manager/))
* Resources are private (S3, EBS Snapshots and Volumes, RDS Snapshots, etc)
* Public S3 buckets are denied by default at an account level
* Public S3 buckets that are required are whitelisted and reviewed for sensitive content, frequent attestation.
* Secrets/keys/tokens should not be hard-coded. Use AWS Secrets Manager to store application/database secrets.

## Infrastructure Security

* Patch your resources frequently (Optional: Use [AWS Systems Manager] (https://aws.amazon.com/systems-manager/#:~:text=AWS%20Systems%20Manager%20gives%20you,tasks%20across%20your%20AWS%20resources.) to do this)
* Vulnerability scan compute resource frequently
* Security Groups should be limited to only required flows (inbound and outbound)
* Internet facing applications are protected by [AWS WAF] (https://aws.amazon.com/waf/) and [AWS Shield] (https://aws.amazon.com/shield/)
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

This content is contributed by our Security Specialist [here] (https://www.cloudsecurity.asia/policy.html)

## Next Steps

If you are ready,  you can use this go-to **[Reference Guide]** (https://d1.awsstatic.com/training-and-certification/ramp-up-guides/RampUp_Security_102019_final.pdf) to ramp up your knowledge of fundamentals, concepts, and best practices for securing the AWS Cloud.


