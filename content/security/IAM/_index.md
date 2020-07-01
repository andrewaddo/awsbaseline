+++
title = "Identity Access Management"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This section will give you an introduction to AWS Identity Access Management (IAM) and and a step-by-step guide to setting it up. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand IAM and IAM Best Practices
2. Successfully setup IAM Users, Group and Roles
3. Successfully configure policies and MFA

### Pre-requisites

1. None

## What is IAM

[AWS Identity and Access Management (IAM)] (https://aws.amazon.com/iam/) is a web service that helps you securely control access to AWS resources. You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources.

You can watch the video below to have a quick overview of IAM

{{< youtube id="Ul6FW4UANGc" >}}


AWS IAM is an integral part of a secure environment, and highlighted below are some of the [benefits] (https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html#intro-video):

* **Shared access to your AWS account**: You can grant other people permission to administer and use resources in your AWS account without having to share your password or access key.

* **Granular permissions**: You can grant different permissions to different people for different resources. 

* **Multi-factor authentication (MFA)**: You can add two-factor authentication to your account and to individual users for extra security. With MFA you or your users must provide not only a password or access key to work with your account, but also a code from a specially configured device.

## Best Practices for AWS IAM Setup

It is important to ensure that your environment is secure and only the right users have the right access.

These are some of the [security best practices] (https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) we recommend you follow:

**Root Account Protection**

You use an access key (an access key ID and secret access key) to make programmatic requests to AWS. However, do not use your [AWS account root user] (https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html) access key. 

The access key for your AWS account root user gives full access to all your resources for all AWS services, including your billing information. You cannot reduce the permissions associated with your AWS account root user access key.
Therefore, protect your root user access key like you would your credit card numbers or any other sensitive secret.

You can watch the [video] (https://www.youtube.com/watch?v=ZaxCLDZgZBo&list=PLhr1KZpdzukf2K67aldy_A1pAC-SkpPWz&index=4&t=1s) below for an overview of root account protection.

{{< youtube id="ZaxCLDZgZBo" >}}

When you are done, read this documentation for the [best practices for managing AWS access keys] (https://docs.aws.amazon.com/general/latest/gr/aws-access-keys-best-practices.html#root-password). 

**Grant Least Privilege**

In a gist, grant only the permissions required to perform a task. Determine what users (and roles) need to do and then craft policies that allow them to perform only those tasks.

Start with a minimum set of permissions and grant additional permissions as necessary. Doing so is more secure than starting with permissions that are too lenient and then trying to tighten them later.

**User Permissions on Groups**

Instead of defining permissions for individual IAM users, it's usually more convenient to create groups that relate to job functions (administrators, developers, accounting, etc.). Next, define the relevant permissions for each group. Finally, assign IAM users to those groups. All the users in an IAM group inherit the permissions assigned to the group. That way, you can make changes for everyone in a group in just one place. As people move around in your company, you can simply change what IAM group their IAM user belongs to.

**Enable MFA**

Wwe recommend that you require multi-factor authentication (MFA) for all users in your account. 

Set up a [multi-factor authentication (MFA) device] (https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_configure-api-require.html) to protect access keys that have only API access. Using MFA can also help fine-tune which API commands require an MFA token to proceed.

If you suspect that a password or access key pair has been exposed:

* [Rotate all access key pairs] (https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_RotateAccessKey)

* [Change your root user password] (https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_change-root.html)

Watch the video below to understand more about MFA

{{< youtube id="A3AObXBJ4Lw" >}}

You can find a comprehensive list in this [documentation]
(https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) and we recommend that you enforce them.

## Setting Up AWS IAM

Setting IAM is quick and easy as you will see in the video below:

{{< youtube id="wRzzBb18qUw" >}}

### Creating a new AWS Account 

This [lab] (https://wellarchitectedlabs.com/security/100_labs/100_aws_account_and_root_user/) will guide you in creating an AWS account and securing the root user.

### Creating IAM User, Group and Roles 

This [lab] (https://wellarchitectedlabs.com/security/100_labs/100_basic_identity_and_access_management_user_group_role/) will help you create and protect AWS credentials while implementing least privilege

This [workshop] (http://aws-core-services.ws.kabits.com/getting-started-with-iam/) will help you understand the concepts and setup even better

### Creating and Attaching Your First Customer Managed Policy 

This [tutorial] (https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_managed-policies.html) will help you create, attach and test your policies

### Configuring Credential and MFA 

This [tutorial] (https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_users-self-manage-mfa-and-creds.html) will help you access AWS services with MFA

### Authenticating and Authorizing with IAM

This comprehensive [training] (https://www.aws.training/Details/Video?id=16484) will introduce you to IAM and discuss how the service helps you manage permissions to your AWS services. It will also cover policy documents and IAM identities.
