+++
title = "Architecting for High Availability"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This section discusses the importance and various requirements to take into consideration when creating a highly available infrastructure. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand what a highly available infrastructure is
2. Successfully setup highly available EC2 and RDS environment
3. Succesfully test your environment’s resilience

### Pre-requisites

1. None

## What is a Highly Available Infrastructure

Highly available systems are reliable and continue to operate even when critical components fail. They are also resilient and are able to recover from failure with minimum data loss and service disruption.

We’ll show how AWS can help you achieve high availability for cloud workloads, across compute, SQL databases and storage services

To start, you can find the [video] (https://www.youtube.com/watch?v=6uE2XULbT3o) below that discusses the best practices in building a highly available and fault tolerant system. You will learn about Designing for Failure, Multi-AZ, Scaling, Self-healing and Loose Coupling.

{{< youtube id="6uE2XULbT3o" >}}

## Baseline Requirement for High Availability


Creating a highly available environment is done according to the needs of internal stakeholders, regulators and integrating partner’s. This section provides high availability and multi-AZ in AWS, along with a comprehensive list of requirements that you must consider before configuring your architecture.

#### Internal Requirements
<>
<>

#### Regulatory Requirements
<>
<>

#### Integrating Partner's Requirements
<>
<>

## Setting Up a Highly Available Environment

Looks like you are all set! To help you implement, here are some labs that we recommend you can practice on.

### Creating a Highly Available EC2 Instance

The Elastic Load Balancer distributes traffic between two or more EC2 instances, each of which can potentially be deployed in a separate subnet that resides in a separate Amazon Availability Zone. These instances can be part of an Auto-Scaling Group, with additional instances launched on demand.

This [tutorial] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-increase-availability.html) will help you ensure availability and maintain multiple EC2 instances using EC2 Auto Scaling and Elastic Load Balancing.

### Creating a Highly Available RDS

The Multi-AZ feature of Amazon RDS operates two databases in multiple Availability Zones with synchronous replication, thus creating a highly available environment with automatic failover.

To start, you can watch the [video] (https://www.youtube.com/watch?v=uiiS1h4PSI8) below that discusses Amazon RDS and how to configure it.

{{< youtube id="uiiS1h4PSI8" >}}

This [documentation] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html) will help you create a highly available and failover ready RDS environment using Multi-AZ deployments. 


### Designing for Failure in your EC2 instances

It is not sufficient to only design for failure, you must also test to ensure that you understand how the failure will cause your systems to behave. This [lab] (https://wellarchitectedlabs.com/reliability/200_labs/200_testing_for_resiliency_of_ec2/) will allow you to conduct tests and will give you the ability to create playbooks how to investigate failures.

### Testing for Resiliency 

This [lab] (https://wellarchitectedlabs.com/reliability/300_labs/300_testing_for_resiliency_of_ec2_rds_and_s3/) will help ensure your implementation is resilient to failure by injecting failure modes into your application. 
