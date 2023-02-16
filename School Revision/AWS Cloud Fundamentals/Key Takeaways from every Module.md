
# Module 1: Cloud Concepts Overview

## Section 1: Introduction to cloud computing

Some key takeaways from this section of the module include:
- Cloud computing is the on-demand delivery of IT resources via the internet with pay-as-you-go pricing.
- Cloud computing enables you to think of (and use) your infrastructure as software.
- There are three cloud service models: IaaS, PaaS, and SaaS.
- There are three cloud deployment models: cloud, hybrid, and on-premises or private cloud.
- There are many AWS service analogs for the traditional, on-premises IT space

## Section 2: Advantages of cloud computing

The key takeaways from this section of the module include the six advantages of cloud computing:
- Trade capital expense for variable expense
- Massive economies of scale
- Stop guessing capacity
- Increase speed and agility
- Stop spending money on running and maintaining data centers
- Go global in minutes

## Section 3: Introduction to Amazon Web Services (AWS)

The key takeaways from this section of the module include:
- AWS is a secure cloud platform that offers a broad set of global cloud-based products called services that are designed to work together.
- There are many categories of AWS services, and each category has many services to choose from.
- Choose a service based on your business goals and technology requirements.
- There are three ways to interact with AWS services.

## Section 4: Moving to the AWS Cloud - The AWS Cloud Adoption Framework (AWS CAF)

The key takeaways from this section of the module include:
- Cloud adoption is not instantaneous for most organizations and requires a thoughtful, deliberate strategy and alignment across the whole organization.
- The AWS CAF was created to help organizations develop efficient and effective plans for their cloud adoption journey.
- The AWS CAF organizes guidance into six areas of focus, called perspectives.
- Perspectives consist of sets of business or technology capabilities that are the responsibility of key stakeholders.
	- Business
		- Business
		- People
		- Governance
	- Technical
		- Platform
		- Security
		- Operations

# Module 2: Cloud Economics and Billing

## Section 1: Fundamentals of pricing

To summarize:
-   AWS has a flexible pricing model where you pay only for what you use each month, without any long-term contracts.
-   To estimate costs, you can consider the characteristics of each service, estimate your usage, and compare it to the prices listed on the AWS website.
-   There are several free AWS services, including:
    -   Amazon VPC
    -   Elastic Beanstalk
    -   AWS CloudFormation
    -   IAM
    -   Automatic scaling services
    -   AWS OpsWorks
    -   Consolidated Billing
-   Some resources that the free services provide may still come with a cost.
-   Inbound data transfer and transfer between other AWS services within the same region are usually free, but there may be exceptions.
-   Outbound data transfer costs are tiered and can be confirmed before using the service

## Section 2: Total Cost of Ownership

On premise vs On cloud


## Section 3: AWS Organizations

## Section 4: AWS Billing and Cost Management

# Module 3: AWS Global Infrastructure Overview

## Section 1: AWS Global Infrastructure

Some key takeaways from this section of the module include:
- The AWS Global Infrastructure consists of Regions and Availability Zones.
- Your choice of a Region is typically based on compliance requirements or to reduce latency.
- Each Availability Zone is physically separate from other Availability Zones and has redundant power, networking, and connectivity.
- Edge locations, and Regional edge caches improve performance by caching content closer to users.

## Section 2: AWS services and service category overview

# Module 4: AWS Cloud Security

## Section 1: AWS shared responsibility model

Some key takeaways from this section of the module include:
- AWS and the customer share security responsibilities–
	- AWS is responsible for security ofthe cloud
	- Customer is responsible for security inthe cloud
- AWS is responsible for protecting the infrastructure—including hardware, software, networking, and facilities—that run AWS Cloud services
- For services that are categorized as infrastructure as a service (IaaS), the customer is responsible for performing necessary security configuration and management tasks
	- For example, guest OS updates and security patches, firewall, security group configurations

## Section 2: AWS Identity and Access Management (IAM)

Some key takeaways from this section of the module include:
- IAM policies are constructed with JavaScript Object Notation (JSON) and define permissions.
- IAM policies can be attached to any IAM entity.
- Entities are IAM users, IAM groups, and IAM roles.
- An IAM user provides a way for a person, application, or service to authenticate to AWS.
- An IAM group is a simple way to attach the same policies to multiple users.
- An IAM role can have permissions policies attached to it,and can be used to delegate temporary access to users or applications.

## Section 3: Securing a new AWS account

The key takeaways from this section of the module are all related to best practices for securing an AWS account. Those best practice recommendations include:
- Secure logins with multi-factor authentication (MFA).
- Delete account root user access keys.
- Create individual IAM users and grant permissions according to the principle of least privilege.
- Use groups to assign permissions to IAM users.
- Configure a strong password policy.
- Delegate using roles instead of sharing credentials.
- Monitor account activity using AWS CloudTrail

## Section 4: Securing accounts


## Section 5: Securing data on AWS

## Section 6: Working to ensure compliance

Some key takeaways from this section of the module include:
- AWS security compliance programs provide information about the policies, processes, and controls that are established and operated by AWS.
- AWS Config is used to assess, audit, and evaluate the configurations of AWS resources.
- AWS Artifact provides access to security and compliance reports.

# Module 5: Networking and Content Delivery

## Section 1: Networking basics

## Section 2: Amazon VPC

Some keytakeaways from this section of the module include:
- A VPC is a logically isolated section of the AWS Cloud.
- A VPC belongs to one Region and requires a CIDR block.
- A VPC is subdivided into subnets.
- A subnet belongs to one Availability Zone and requires a CIDR block.
- Route tables control traffic for a subnet.
- Route tables have a built-in local route.
- You add additional routes to the table.
- The local route cannot be deleted

## Section 3: VPC networking

Some key takeaways from this section of the module include:
- There are several VPC networking options, which include:
	- Internet gateway: Connects your VPC to the internet
	- NAT gateway: Enables instances in a private subnet to connect to the internet
	- VPC endpoint: Connects your VPC to supported AWS services
	- VPC peering: Connects your VPC to other VPCs
	- VPC sharing: Allows multiple AWS accounts to create their application resources into shared, centrally-managed Amazon VPCs
	- AWS Site-to-Site VPN: Connects your VPC to remote networks
	- AWS Direct Connect: Connects your VPC to a remote network by using a dedicated network connection
	- AWS Transit Gateway: A hub-and-spoke connection alternative to VPC peering
- You can use the VPC Wizard to implement your design.

## Section 4: VPC security

The key takeaways from this section of the module are:
- Build security into your VPC architecture.
- Security groups and network ACLs are firewall options that you can use to secure your VPC

## Section 5: Amazon Route 53

Some keytakeaways from this section of the module include:
- Amazon Route 53 is a highly available and scalable cloud DNS web service that translates domain names into numeric IP addresses.
- Amazon Route 53 supports several types of routing policies.
- Multi-Region deployment improves your application’s performance for a global audience.
- You can use Amazon Route 53 failover to improve the availability of your applications

## Section 6: Amazon CloudFront

Some keytakeaways from this section of the module include:
- A CDN is a globally distributed system of caching servers that accelerates delivery of content.
- Amazon CloudFront is a fast CDN service that securely delivers data, videos, applications, and APIs over a global infrastructure with low latency and high transfer speeds.
- Amazon CloudFront offers many benefits, including:
- Fast and global
- Security at the edge
- Highly programmable
- Deeply integrated with AWS
- Cost-effective

# Module 6: Compute

## Section 1: Compute services overview

## Section 2: Amazon EC2

Some key takeaways from this section of the module include:
- Amazon EC2 enables you to run Windows and Linux virtual machines in the cloud.
- You launch EC2 instances from an AMI template into a VPC in your account.
- You can choose from many instance types. Each instance type offers different combinations of CPU, RAM, storage, and networking capabilities.
- You can configure security groups to control access to instances (specify allowed ports and source).
- User data enables you to specify a script to run the first time that an instance launches. 
- Only instances that are backed by Amazon EBS can be stopped. 
- You can use Amazon CloudWatch to capture and review metrics on EC2 instances

## Section 3: Amazon EC2 cost optimization

Some key takeaways from this section of the module are:
- Amazon EC2 pricing modelsinclude On-Demand Instances, Reserved Instances, Spot Instances, Dedicated Instances, and Dedicated Hosts. Per second billing is available for On-Demand Instances, Reserved Instances, and Spot Instances that use only Amazon Linux and Ubuntu. 
- Spot Instances can be interrupted with a 2-minute notification. However,they can offer significant cost savings over On-Demand Instances
- The four pillars of cost optimization are
	- Right size
	- Increase elasticity
	- Optimal pricing model
	- Optimize storage choices

## Section 4: Container services

Some key takeaways from this section include:
- Containers can hold everything that an application needs to run.
- Docker is a software platform that packages software into containers. 
- A single application can span multiple containers.
- Amazon Elastic Container Service (Amazon ECS) orchestrates the running of Docker containers.
- Kubernetes is open source software for container orchestration. 
- Amazon Elastic Kubernetes Service (Amazon EKS) enables you to run Kubernetes on AWS
- Amazon Elastic Container Registry (Amazon ECR) enables you to store, manage, and deploy your Docker containers

## Section 5: Introduction to AWS Lambda

Some key takeaways from this section of the module include:
- Serverless computing enables you to build and run applications and services without provisioning or managing servers. 
- AWS Lambda is a serverless compute service that provides built-in fault tolerance and automatic scaling.
- An event source is an AWS service or developer-created application that triggers a Lambda function to run. 
- The maximum memory allocation for a single Lambda function is 10,240 MB. 
- The maximum run time for a Lambda function is 15 minutes

## Section 6: Introduction to AWS Elastic Beanstalk

Some key takeaways from this section of the module include:
- AWS Elastic Beanstalk enhances developer productivity.
	- Simplifies the process of deploying your application.
	- Reduces management complexity.
- Elastic Beanstalk supports Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker.
- There is no charge for Elastic Beanstalk. Pay only for the AWS resources you use. 

# Module 7: Storage

## Section 1: Amazon Elastic Block Store (Amazon EBS)

- Amazon EBS provides block-level storage volumes for use with Amazon EC2 instances
- EBS volumes persist independently from the life of an instance, and are analogous to virtual disks in the cloud 
- EBS offers three volume types: General Purpose SSD, Provisioned IOPS SSD, and magnetic, with different performance characteristics and cost
- EBS provides additional benefits, including replication in the same Availability Zone, easy and transparent encryption, elastic volumes, and backup by using snapshots.

Amazon EBS features:
- Persistent and customizable block storage for Amazon EC2
- HDD and SSD types
- Replicated in the same Availability Zone
- Easy and transparent encryption
- Elastic volumes
- Back up by using snapshots

## Section 2: Amazon Simple Storage Service (Amazon S3)

- Amazon S3 is a fully managed cloud storage service.
- You can store a virtually unlimited number of objects.
- You pay for only what you use.
- You can access Amazon S3 at any time from anywhere through a URL.
- Amazon S3 offers rich security controls

## Section 3: Amazon Elastic File System (Amazon EFS)

- Amazon EFS provides file storage over a network.
- Perfect for big data and analytics, media processing workflows, content management, web serving, and home directories.
- Fully managed service that eliminates storage administration tasks.
- Accessible from the console, an API, or the CLI.
- Scales up or down as files are added or removed and you pay for what you use.

## Section 4: Amazon S3 Glacier 

- Amazon S3 Glacier is a data archiving service that is designed for security, durability, and an extremely low cost.
- Amazon S3 Glacier pricing is based on Region.
- Its extremely low-cost design works well for long-term archiving.
- The service is designed to provide 11 9s of durability for objects.

# Module 8: Databases

## Section 1: Amazon Relational Database Service

With Amazon RDS, you can set up, operate, and scale relational databases in the cloud.
- Features
	- Managed service•Accessible via the console, AWS Command Line Interface (AWS CLI), or application programming interface (API) calls
	- Scalable (compute and storage)
	- Automated redundancy and backup are available
	- Supported database engines:
		- Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle, Microsoft SQL Server

## Section 2: Amazon DynamoDB

Amazon DynamoDB:
- Runs exclusively on SSDs.
- Supports document and key-value store models.
- Replicates your tables automatically across your choice of AWS Regions.
- Works well for mobile, web, gaming, adtech, and Internet of Things (IoT) applications.
- Is accessible via the console, the AWS CLI, and API calls.
- Provides consistent, single-digit millisecond latency at any scale.
- Has no limits on table size or throughput.

## Section 3: Amazon Redshift

Amazon Redshift features:
- Fast, fully managed data warehouse service
- Easily scale with no downtime
- Columnar storage and parallel processing architectures
- Automatically and continuously monitors cluster
- Encryption is built in

## Section 4: Amazon Aurora

Amazon Aurora features:
- High performance and scalability
- High availability and durability
- Multiple levels of security
- Compatible with MySQL and PostgreSQL
- Fully managed

# Module 9: Cloud Architecture

## Section 1: AWS Well-Architected Framework

Some keytakeaways from this section of the module include:
- The AWS Well-Architected Framework provides a consistent approach to evaluate cloud architectures and guidance to help implement designs
- The AWS Well-Architected Framework documents a set of design principles and best practices that enable you to understand if a specific architecture aligns well with cloud best practices. 
- The AWS Well-Architected Framework is organized into six pillars.
- Each pillar includes its own set of design principles and best practices

## Section 2: Reliability and availability

Some key takeaways from this section of the module include:
- Reliability is a measure of your system’s ability to provide functionality when desired by the user, and it can be measured in terms of MTBF. 
- Availability is the percentage of time that a system is operating normally or correctly performing the operations expected of it (or normal operation time over total time).
- Three factors that influence the availability of your applications are fault tolerance, scalability, and recoverability.
- You can design your workloads and applications to be highly available, but there is a cost tradeoff to consider

## Section 3: AWS Trusted Advisor

Some keytakeaways from this section of the module include:
- AWS Trusted Advisor is an online tool that provides real-time guidance to help you provision your resources by following AWS best practices. 
- AWS Trusted Advisor looks at your entire AWS environment and gives you real-time recommendations in five categories.
- You can use AWS Trusted Advisor to help you optimize your AWS environment as soon as you start implementing your architecture designs.

# Module 10: Auto Scaling and Monitoring

## Section 1: Elastic Load Balancing

Some keytakeaways from this section of the module include:
- Elastic Load Balancing distributes incoming application or network traffic across multiple targets(such as Amazon EC2 instances, containers, IP addresses, and Lambda functions) in one or more Availability Zones.
- Elastic Load Balancing supports three types of load balancers:•Application Load Balancer•Network Load Balancer
- Classic Load Balancer
- Elastic Load Balancing offers several monitoring tools for continuous monitoring and logging for auditing and analytics.

## Section 2: Amazon CloudWatch

Some key takeaways from this section of the module include:
- Amazon CloudWatch helps you monitor your AWS resources—and the applications that you run on AWS—in real time.
- CloudWatch enables youto –
	- Collect and track standard and custom metrics.
	- Set alarms to automatically send notifications to SNS topics or perform Amazon EC2 Auto Scaling or Amazon EC2 actions based on the value of the metric or expression relative to a threshold over a number of time periods.
	- Define rules that match changes in your AWS environment and route these events to targets for processing

## Section 3: Amazon EC2 Auto Scaling

Some key takeaways from this section of the module include:
- Scaling enables you to respond quickly to changes in resource needs.
- Amazon EC2 Auto Scaling helps you maintain application availability,and enables you to automatically add or remove EC2 instances according to your workloads.
- An Auto Scaling group is a collection of EC2 instances.
- A launch configuration is an instance configuration template.
- You can implement dynamic scaling with Amazon EC2 Auto Scaling, Amazon CloudWatch, and Elastic Load Balancing.

AWS Auto Scaling is a separate service that monitors your applications, and it automatically adjusts capacity for the followingresources:
- Amazon EC2 instances and Spot Fleets
- Amazon ECS tasks
- Amazon DynamoDB tables and indexes
- Amazon Aurora Replicas



