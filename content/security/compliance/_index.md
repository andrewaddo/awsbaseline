+++
title = "Staying Compliant with AWS"
date =  2020-06-13T16:20:15+08:00
weight = 2
+++

This section discusses AWS services such as Atlas and Artifact that you can use to stay compliant. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand the services you can leverage on to stay compliant

### Pre-requisites

1. None

### What is What is Compliance Center

[AWS Compliance Center] (https://www.atlas.aws/), **Atlas**, offers you a central location to research cloud-related regulatory requirements and how they impact your industry. AWS has customers throughout the world and is continually adapting to evolving regulations, so please contact us if your country of interest is not listed in the drop-down menu and you would like more information about AWS


### Enforce Compliance with AWS Artifact

[AWS Artifact] (https://aws.amazon.com/artifact/) is a service that allows you to download AWS security compliance reports such as [ISO] (https://aws.amazon.com/compliance/iso-certified/) and [PCI reports] (https://aws.amazon.com/compliance/pci-dss-level-1-faqs/). Using AWS Artifact, a user in a master account can automatically accept agreements on behalf of all member accounts in an organization, even as new reports and accounts are added.

You can watch the [video](https://www.youtube.com/watch?v=ILEoLqpbfXM) below to understand more
{{< youtube id="ILEoLqpbfXM" >}}

### Maintain Compliance with AWS Config

[AWS Config] (https://aws.amazon.com/config/) is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. Config continuously monitors and records your AWS resource configurations and allows you to automate the evaluation of recorded configurations against desired configurations. 

The AWS Config [best practices] (https://aws.amazon.com/blogs/mt/aws-config-best-practices/) include:

* Enable AWS Config in all accounts and Regions

* Record configuration changes to ALL resource types

* Record global resources (such as IAM resources) only in one Region

* Ensure that you have a secure Amazon S3 bucket to collect the configuration history and snapshot files

You can watch the [video] (https://www.youtube.com/watch?v=X_fznJtSyV8) below to understand more:

{{< youtube id="X_fznJtSyV8" >}}

## Labs and Hands-On Resources

### Setting Up AWS Artifact

This [tutorial] (https://docs.aws.amazon.com/artifact/latest/ug/getting-started.html#create-iam-policy) will show you how to setup IAM permissions to download report and agreement using AWS Artifact

### Setting Up AWS Config

This [tutorial] (https://docs.aws.amazon.com/config/latest/developerguide/getting-started.html) will show you multiple ways to setup AWS Config and AWS Config Rules.
