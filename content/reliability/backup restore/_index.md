+++
title = "Backup and Restore"
date =  2020-06-13T16:20:15+08:00
weight = 2
+++

This chapter discuss the importance of backup and restore, along with the baseline steps to build durable and disaster-ready solutions in AWS. You can also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand the importance of backup and restore with AWS
2. Understand the different requirement that will impact your backup and restore configuration
3. Successfully setup back and restore for your S3, EC2 and RDS resources

### Pre-requisites

1. Recovery point objective (RPO) for your application

### Overview

AWS offer the most storage services, data-transfer methods, and networking options to build solutions that protect your data with unmatched durability and security.

For an overview, watch this quick [video] (https://aws.amazon.com/backup-restore/) to understand why you should backup and restore with AWS.

### Baseline Requirement for Backup and Restore in AWS

Setting up backup and restore is done according to the needs of internal stakeholders, regulators and integrating partner’s. This section provides an overview of backup, restore and disaster recovery in AWS, along with a comprehensive list of requirements that you must consider before configuring your architecture.

You can watch the [video] (https://www.youtube.com/watch?v=cBh_Tlg-2yM&list=PLhr1KZpdzukf2K67aldy_A1pAC-SkpPWz&index=8&t=34s) below to understand more.
{{< youtube id="cBh_Tlg-2yM&list=PLhr1KZpdzukf2K67aldy_A1pAC-SkpPWz&index=8&t=0s" >}}

Setting up backup and retore depend on the requirements from regulatory bodies, partners and internal requirements which we will discuss below.

#### Internal Requirements
<>
<>

#### Regulatory Requirements
<>
<>

#### Integrating Partner's Requirements
<>
<>

### Backup and Archival Services 

The most basic services you can use for backup and archival are [Amazon S3] (https://aws.amazon.com/s3/) and [Amazon Glacier] (https://aws.amazon.com/glacier/). They both offer unlimited capacity and require no volume or media management as backup data sets grow. The  pay-for-whatyou-use model and low cost per GB/month make these services a good fit for data protection use cases.

**Amazon S3**

You can use Amazon S3 to store and retrieve any amount of data, at any time, from anywhere on the web. Amazon S3 offers a range of storage classes designed for different use cases. These include:
- Amazon S3 Standard for general-purpose storage of frequently
accessed data.
- Amazon S3 Standard for infrequent Access for long-lived, but less
frequently accessed data.
- Amazon Glacier for long-term archive

When choosing the Amazon S3 tier that will best suit you, some of the factors to consider are:

* Access frequency (how often do you need to read/write objects)
* Durability and Availability of objects
* Pricing (such as min capacity charge, min storage duration charge, retrieval fee)

You can view details of the different [storage classes] (https://aws.amazon.com/s3/storage-classes/), which can help you decide in setting up your architecture.

**Amazon Glacier**

Amazon Glacier is an extremely low-cost, cloud archive storage service that provides secure and durable storage for data archiving and online backup. To keep costs low, Amazon Glacier is optimized for data that is infrequently accessed and for which retrieval times of several hours are acceptable. 

You can view a [detailed pricing comparison] ((https://aws.amazon.com/s3/pricing/)) of Amazon S3 classes and Amazon Glacier.

**AWS Backup**

[AWS Backup] (https://aws.amazon.com/backup/) is a fully managed backup service that makes it easy to centralize and automate the backup of data across AWS services in the cloud and on premises. AWS Backup automates and consolidates backup tasks that were previously performed service-by-service, and removes the need to create custom scripts and manual processes. 

AWS Backup support backup and restore for: [Amazon EFS] (https://aws.amazon.com/efs/), [DynamoDB] (https://aws.amazon.com/dynamodb/), [Amazon EC2] (https://aws.amazon.com/ec2/), [Amazon EBS] (https://aws.amazon.com/ebs/), [Amazon RDS] (https://aws.amazon.com/rds/), [Amazon Aurora] (https://aws.amazon.com/rds/aurora/) and [AWS Storage Gateway] (https://aws.amazon.com/storagegateway/). If you are interested to understand how AWS Backup integrated with these services, visit this [documentation] (https://docs.aws.amazon.com/aws-backup/latest/devguide/working-with-other-services.html).

You can watch the [video] (https://www.youtube.com/watch?v=QDiXzFx2iMU&t=34s) below to have an overview of AWS Backup

{{< youtube id="QDiXzFx2iMU&t=34s" >}}

### Backing Up EC2 with EBS Snapshots

[Amazon EBS] (https://aws.amazon.com/ebs/) provides the ability to create snapshots (backups) of any Amazon EBS volume. It takes a copy of the volume and places it in Amazon S3, where it is stored redundantly in multiple Availability Zones. The first snapshot is a full copy of the volume; ongoing snapshots store incremental block-level changes only.

You can watch the [video] (https://www.youtube.com/watch?v=TKEUrhhEy34) below to understand more about EBS, how to create EBS snapshot, monitoring of snapshot costs and automating snapshot management.

{{< youtube id="TKEUrhhEy34" >}}

You can check these documentations for some key actions you can do with EBS: [create snapshot] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-snapshot.html), [delete snapshot] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-snapshot.html), [copy snapshot] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-copy-snapshot.html), [share snapshot] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-modifying-snapshot-permissions.html) and [automate snapshot] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/snapshot-lifecycle.html).

### RDS Backup Approach

Amazon RDS includes features for automating database backups. Amazon RDS creates a storage volume snapshot of your database instance, backing up the entire DB instance, not just individual databases. 

DB snapshots are user-initiated backups that enable you to back up your DB instance to a known state as frequently as you like, and then restore to that state at any time. The steps are easy and you can find them [here] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html).


### Labs and Hands-on Resources

Looks like you are all set! To help you implement, here are some labs that we recommend you can practice on.

#### Creating Periodic Backup of AWS Resources

This [lab] (https://wellarchitectedlabs.com/reliability/200_labs/200_testing_backup_and_restore_of_data/) will teach you how to create, test and automate backup strategy for mission-critical data in AWS. It will cover backup for EBS Volumes, RDS Databases, DynamoDB Tables and EFS File Systems. 

#### Creating asynchronous backup of data in S3

This [lab] (https://wellarchitectedlabs.com/reliability/200_labs/200_bidirectional_replication_for_s3/) will help you create S3 data backup automatically and autoamate disaster recover for objects in S3.

#### Creating EBS Backup for EC2 Instance 

This [documentation] (https://aws.amazon.com/premiumsupport/knowledge-center/back-up-instance-store-ebs/) provide the steps to preparing a backup of the instance store volume of EC2 using Amazon EBS.

#### Creating DB Snapshot for Relational Database Service 

This [documentation] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html) provide the steps to creating a storage volume snapshot for your DB instance.

#### Restoring Data from DB Snapshot of Relational Database Service

This [documentation] (https://aws.amazon.com/premiumsupport/knowledge-center/restore-rds-instance-from-snapshot/) provide the steps to restore data from both manual and automatic DB snapshots.

#### Backing Up and Restoring with AWS Backup

This [tutorial] (https://docs.aws.amazon.com/aws-backup/latest/devguide/getting-started.html) shows you how to perform the tasks necessary to back up and restore your resources using AWS Backup.

## Diving Deep: Additional Resources

**Doing native backup with SQL Server in AWS**

You can find the information and resolution in this [guideline] (https://aws.amazon.com/premiumsupport/knowledge-center/route-53-create-alias-records/)