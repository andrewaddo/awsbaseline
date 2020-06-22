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

### Why Backup and Restore with AWS

AWS offer the most storage services, data-transfer methods, and networking options to build solutions that protect your data with unmatched durability and security.

For an overview, watch this [video] (https://aws.amazon.com/backup-restore/)/

Here are some of the reasons to backup with AWS:

* **Data Durability**: AWS provides 99.999999999% data durability. Data uploaded to Amazon S3 and Amazon S3 Glacier are created and stored across at least three devices in a single AWS Region.
* **Flexibility & scalability**: With AWS, you no longer need to wait weeks-to-months to procure tapes, disks, and other IT resources to increase your storage infrastructure. This ability to scale on demand can improve operational flexibility, innovation, and business agility.
* **Cost efficiency**: Spend efficiently with pay-as-you-go pricing, cost-management tools, data lifecycle policies, and the EFS and S3 Storage Classes. With these capabilities, you can cost-effectively protect data in the cloud without sacrificing performance. 

You can find out more [here] (https://aws.amazon.com/backup-restore/).


### Baseline Requirement for Backup and Restore in AWS

Setting up backup and restore is done according to the needs of internal stakeholders, regulators and integrating partner’s. This section provides an overview of backup, restore and disaster recovery in AWS, along with a comprehensive list of requirements that you must consider before configuring your architecture.

You can watch the video  below to understand more.

(https://www.youtube.com/watch?v=cBh_Tlg-2yM&list=PLhr1KZpdzukf2K67aldy_A1pAC-SkpPWz&index=8&t=0s)
{{< youtube id="cBh_Tlg-2yM&list=PLhr1KZpdzukf2K67aldy_A1pAC-SkpPWz&index=8&t=0s" >}}


#### Internal Requirements
<>
<>

#### Regulatory Requirements
<>
<>

#### Integrating Partner's Requirements
<>
<>

### Setting Up for Common Backup and Restore Cases

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

## Diving Deep: Additional Resources

**Doing native backup with SQL Server in AWS**

You can find the information and resolution in this [guideline] (https://aws.amazon.com/premiumsupport/knowledge-center/route-53-create-alias-records/)