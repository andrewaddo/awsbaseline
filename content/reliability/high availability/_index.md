+++
title = "Architecting for High Availability"
date =  2020-06-13T05:13:08+08:00
weight = 1
+++

This section discusses how AWS can help you achieve high availability for cloud workloads, across compute, SQL databases and storage services. You will also find hands-on labs that you can try at the end of the section before configuring your own system. Let’s begin!

### What are the expected outcomes?

1. Understand what a highly available infrastructure is
2. Successfully setup highly available EC2 and RDS environment
3. Succesfully test your environment’s resilience

### Pre-requisites

1. None

## What is a Highly Available Infrastructure

Highly available systems are reliable and continue to operate even when critical components fail. They are also resilient and are able to recover from failure with minimum data loss and service disruption.

**Understanding Your Availability Needs**

Availability goals will differ according to the needs of your business. Availability goals can vary from those applicable to internal tools (for
example, 99% availability) to those for mission critical workloads (for example,
99.999% or even higher.) Based on the necessary availability, the level of effort
that’s required of engineering and operations, and the services that are
appropriate to use to deliver the application will vary. Costs can be considerable
to achieve the highest levels of availability. 

As you go through this section, it is importnt to take a step back and discuss what your availability goals will be like.

**Design Principles for Availability**

When designing your  architecture, it is best to keep in mind below general best practices:

***Fault Isolation Zones***

Increasing a system’s availability beyond the availability of individual
components is to make use of multiple independent components in parallel (i.e. multi-AZ, [cross-Region] (https://aws.amazon.com/s3/features/replication/) replication for Amazon S3 and the ability to copy various [snapshots] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-copy-snapshot.html) and Amazon Machine Images [(AMIs)] (https://aws.amazon.com/premiumsupport/knowledge-center/copy-ami-region/) to other Regions)

You can watch the video below to understand more about Amazon S3 Cross-Regional Replication
{{< youtube id="kAaPjE9-a2A" >}}

***Redundant components***

An important design principle is the avoidance of single points of failure in underlying physical infrastructure.  Similarly, systems are built to be resilient to failure of
a single compute node, single storage volume, or single instance of a database. 

***Microservice architecture***

Microservices are an architectural and organizational approach to software development where software is composed of small independent services that communicate over well-defined APIs. These services are owned by small, self-contained teams.

[Microservices] (https://aws.amazon.com/microservices/) architectures make applications easier to scale and faster to develop, enabling innovation and accelerating time-to-market for new features.

You can watch the video below to understand the difference and evolution from monolithic to microservice architecture

{{< youtube id="Ijs55IA8DIk" >}}

This is can be an advance topic for you but if you are interested, you can try this [module] (https://aws.amazon.com/getting-started/hands-on/break-monolith-app-microservices-ecs-docker-ec2/) which guides you from a monolithic to microservice architecture.

***Recovery Oriented Computing (ROC)***

ROC suggests focusing on having the right
mechanisms to detect failures (such as Elastic Load Balancing [ELB] (https://aws.amazon.com/elasticloadbalancing/#:~:text=Elastic%20Load%20Balancing%20automatically%20distributes,or%20across%20multiple%20Availability%20Zones.) or Route53 health checks)

You can watch the video below on how to create Amazon Route 53 Health Checks

{{< youtube id="PnOFP4EZ6hs" >}}


**Customer Reference**: You can watch the video below that shows Skyscanner utilising principles such as fault isolation zone (multi-region), microservices, redundant components to ensure a highly available architecture for their 80M customers globally.

{{< youtube id="99nNHsbwBpg&t=345s" >}}

**Setting up a Highly Available Architecture**

To have a visual overview, you can find the [video] (https://www.youtube.com/watch?v=6uE2XULbT3o) below that discusses the best practices in building a highly available and fault tolerant system. You will learn about Designing for Failure, Multi-AZ, Scaling, Self-healing and Loose Coupling.

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


As you fill find in the tutorial below, your application can face traffic increase to the point that you require more than one instance to meet the demand. In this case, you can launch multiple EC2 instances from your AMI and then use Elastic Load Balancing [(ELB)] (https://aws.amazon.com/elasticloadbalancing/) to distribute incoming traffic for your application across these EC2 instances. 

This [tutorial] (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-increase-availability.html) will help you ensure availability for your EC3 instances.

If you have the time, you can watch the video below for a step-by-step on creating a highly scalable and available website (i.e. wordpress). 

{{< youtube id="p4ttBpRedFQ" >}}

### Creating a Highly Available RDS

The Multi-AZ feature of Amazon RDS operates two databases in multiple Availability Zones with synchronous replication, thus creating a highly available environment with automatic failover.

To start, you can watch the [video] (https://www.youtube.com/watch?v=uiiS1h4PSI8) below that discusses Amazon RDS and how to configure it.

{{< youtube id="uiiS1h4PSI8" >}}

This [documentation] (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html) will help you create a highly available and failover ready RDS environment using Multi-AZ deployments. 


### Designing for Failure in your EC2 instances

It is not sufficient to only design for failure, you must also test to ensure that you understand how the failure will cause your systems to behave. This [lab] (https://wellarchitectedlabs.com/reliability/200_labs/200_testing_for_resiliency_of_ec2/) will allow you to conduct tests and will give you the ability to create playbooks how to investigate failures.

### Testing for Resiliency 

This [lab] (https://wellarchitectedlabs.com/reliability/300_labs/300_testing_for_resiliency_of_ec2_rds_and_s3/) will help ensure your implementation is resilient to failure by injecting failure modes into your application. 
