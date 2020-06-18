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

AWS Compliance Center offers you a central location to research cloud-related regulatory requirements and how they impact your industry. AWS has customers throughout the world and is continually adapting to evolving regulations, so please contact us if your country of interest is not listed in the drop-down menu and you would like more information about AWS

You can find out more in the [Atlas] website (https://www.atlas.aws/)


### Enforce Compliance in Your Application with AWS Artifact

AWS Artifact is a service that allows you to download AWS security compliance reports such as ISO and PCI reports. Using AWS Artifact, a user in a master account can automatically accept agreements on behalf of all member accounts in an organization, even as new reports and accounts are added.

You can watch the [video](https://www.youtube.com/watch?v=ILEoLqpbfXM) below to understand more
{{< youtube id="ILEoLqpbfXM" >}}

### Setting Up AWS Artifact

This [tutorial] (https://docs.aws.amazon.com/artifact/latest/ug/getting-started.html#create-iam-policy) will show you how to setup IAM permissions to download report and agreement using AWS Artifact
