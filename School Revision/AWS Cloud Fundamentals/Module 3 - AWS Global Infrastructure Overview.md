# Module 3: AWS Global Infrastructure Overview

## Module overview
---
- AWS Global Infrastructure
- AWS service and service category overview

## Module objectives
---
After completing this module, you should be able to:
- Identify the difference between AWS Regions, Availability Zones, and edge locations
- Identify AWS service and service categories

## Section 1: AWS Global Infrastructure
---

### AWS Global Infrastructure

The AWS Global Infrastructure is designed and built to deliver a flexible, reliable, scalable, and secure cloud computing environment with high-quality global network performance.

### AWS Regions

-   AWS infrastructure is built around Regions, with a total of 22 Regions worldwide.
-   Each Region is a physical geographical location with one or more Availability Zones.
-   Availability Zones consist of one or more data centers.
-   Regions are isolated from one another for fault tolerance and stability.
-   Data stored in a specific Region is not replicated outside that Region.

![](https://i.imgur.com/p6lPzIK.png)


### Selecting a Region

-   Consider data governance and legal requirements
-   Local laws might restrict the Regions where you can offer content or services
-   Example: European Union (EU) Data Protection Directive

![](https://i.imgur.com/geWJZBM.png)


### Availability Zones

- Each AWS Region has multiple Availability Zones 
- Each Availability Zone is a fully isolated partition of the AWS infrastructure 
- Availability Zones consist of discrete data centers 
- They are designed for fault isolation 
- They are interconnected with other Availability Zones using high-speed private networking
- You are responsible for selecting the Availability Zones where your systems will reside 
- Systems can span multiple Availability Zones 
- AWS recommends replicating data and resources across Availability Zones for resiliency 
- You should design your systems to survive the temporary or prolonged failure of an Availability Zone in the case of a disaster.

![](https://i.imgur.com/Uo0Xk8o.png)


### AWS data centers

-   Data centers are the foundation for the AWS infrastructure
-   Availability Zone is the most granular level of specification for customers, but the actual data resides in the data center
-   Amazon operates highly available and state-of-the-art data centers
-   Data centers are designed with security and redundancy in mind, and are evaluated to mitigate environmental risk
-   Critical system components are backed up across multiple Availability Zones to ensure availability
-   AWS continuously monitors service usage to ensure capacity and support availability commitments
-   Data center locations are confidential and access to them is restricted
-   In case of failure, automated processes move data traffic away from the affected area
-   AWS uses custom network equipment from multiple original device manufacturers (ODMs) that design and manufacture products based on specifications from a second company, which then rebrands the products for sale.

![](https://i.imgur.com/wvlCkJ6.png)


### Points of Presence

-   Amazon CloudFront is a CDN used to reduce latency in content delivery.
-   Amazon Route 53 is a DNS service that routes requests to the nearest edge location.
-   AWS Points of Presence are located globally and improve near real-time user experience.
-   AWS Points of Presence are used by various AWS services such as CloudFront, Route 53, and AWS WAF.
-   Regional edge caches are used by default with Amazon CloudFront to provide alternative content when edge locations are not frequently accessed.

![](https://i.imgur.com/oo3ndMT.png)


### AWS infrastructure features

-   Elastic and scalable resources that can adjust dynamically to changes in capacity requirements
-   Built-in component redundancy for fault tolerance and continued operations despite failed components
-   Minimal to no human intervention while providing high availability with minimal downtime.

![](https://i.imgur.com/JC9KeMl.png)


### Key Takeaways

Some key takeaways from this section of the module include:
- The AWS Global Infrastructure consists of Regions and Availability Zones.
- Your choice of a Region is typically based on compliance requirements or to reduce latency.
- Each Availability Zone is physically separate from other Availability Zones and has redundant power, networking, and connectivity.
- Edge locations, and Regional edge caches improve performance by caching content closer to users.


## Section 2: AWS services and service category overview
---

### AWS foundational services

-   AWS Global Infrastructure consists of Regions, Availability Zones, and Points of Presence (edge locations)
-   Provides platform for a broad set of services including networking, storage, compute, and databases
-   Services delivered as an on-demand utility with pay-as-you-go pricing
-   Available in seconds.

![](https://i.imgur.com/zktfJhy.png)


### AWS categories of services

-   AWS offers a broad set of cloud-based services across 23 different categories
-   Course focuses on the most widely used and introductory services, as well as services likely to be covered in the AWS Certified Cloud Practitioner exam
-   Categories covered: Compute, Cost Management, Database, Management and Governance, Networking and Content Delivery, Security, Identity, and Compliance, Storage.

![](https://i.imgur.com/ASqOpnD.png)


### Storage service category

-   AWS storage services include:
    -   Amazon Simple Storage Service (S3) - object storage for websites, mobile apps, backup and restore, archive, enterprise applications, IoT devices, and big data analytics.
    -   Amazon Elastic Block Store (EBS) - high-performance block storage for use with EC2 for both throughput and transaction-intensive workloads.
    -   Amazon Elastic File System (EFS) - scalable, fully managed NFS file system for use with AWS Cloud services and on-premises resources.
    -   Amazon Simple Storage Service Glacier - secure, durable, and low-cost cloud storage class for data archiving and long-term backup.
-   S3 offers scalability, data availability, security, and performance
-   EBS is used for relational and non-relational databases, enterprise applications, containerized applications, big data analytics, file systems, and media workflows.
-   EFS is built to scale on demand to petabytes and reduce the need to provision and manage capacity
-   S3 Glacier delivers 11 9s of durability and comprehensive security and compliance capabilities.

![](https://i.imgur.com/dGngvBw.png)


### Compute service category

-   Amazon Elastic Compute Cloud (Amazon EC2) provides resizable compute capacity as virtual machines in the cloud.
-   Amazon EC2 Auto Scaling enables automatic adding or removing of EC2 instances based on defined conditions.
-   Amazon Elastic Container Service (Amazon ECS) is a scalable and high-performance container orchestration service supporting Docker containers.
-   Amazon Elastic Container Registry (Amazon ECR) is a fully-managed Docker container registry for easy storage, management, and deployment of Docker container images.
-   AWS Elastic Beanstalk is a service for deploying and scaling web applications and services on familiar servers such as Apache and Microsoft Internet Information Services (IIS).
-   AWS Lambda enables running code without provisioning or managing servers, with charges only for consumed compute time and no charge when the code is not running.
-   Amazon Elastic Kubernetes Service (Amazon EKS) makes it easy to deploy, manage, and scale containerized applications using Kubernetes on AWS.
-   AWS Fargate is a compute engine for Amazon ECS that allows running containers without managing servers or clusters.

![](https://i.imgur.com/SlN3Xu5.png)


### Database service category

-   Amazon Relational Database Service (Amazon RDS)
    -   Makes it easy to set up, operate, and scale a relational database in the cloud
    -   Provides resizable capacity
    -   Automates time-consuming administration tasks
-   Amazon Aurora
    -   MySQL and PostgreSQL-compatible relational database
    -   Up to five times faster than standard MySQL databases
    -   Three times faster than standard PostgreSQL databases
-   Amazon Redshift
    -   Enables running analytic queries against petabytes of data stored locally in Amazon Redshift
    -   Directly against exabytes of data stored in Amazon S3
    -   Delivers fast performance at any scale
-   Amazon DynamoDB
    -   Key-value and document database
    -   Delivers single-digit millisecond performance at any scale
    -   Built-in security, backup and restore, and in-memory caching

### Networking and content delivery service category

AWS Networking and Content Delivery Services:
-   Amazon VPC: Provision logically isolated sections of the AWS Cloud.
-   Elastic Load Balancing: Distribute incoming application traffic across multiple targets.
-   Amazon CloudFront: Fast content delivery network (CDN) service.
-   AWS Transit Gateway: Connect Amazon VPCs and on-premises networks to a single gateway.
-   Amazon Route 53: Scalable cloud Domain Name System (DNS) web service.
-   AWS Direct Connect: Dedicated private network connection from your data center or office to AWS.
-   AWS VPN: Secure private tunnel from your network or device to the AWS global network.

### Security, identity, and compliance service category

-   AWS Identity and Access Management (IAM): Enables management of access to AWS services and resources, creating and managing AWS users and groups with IAM permissions.
-   AWS Organizations: Restricts allowed services and actions in accounts.
-   Amazon Cognito: Adds user sign-up, sign-in, and access control to web and mobile apps.
-   AWS Artifact: Provides access to AWS security and compliance reports and agreements.
-   AWS Key Management Service (KMS): Enables creation and management of encryption keys for a wide range of AWS services and applications.
-   AWS Shield: Managed DDoS protection service for safeguarding applications running on AWS.

### AWS cost management service category

-   AWS Cost and Usage Report: comprehensive set of AWS cost and usage data including metadata about AWS services, pricing, and reservations
-   AWS Budgets: allows setting custom budgets and alerts when costs exceed the budgeted amount
-   AWS Cost Explorer: an interface to visualize, understand, and manage AWS costs and usage over time.

### Management and governance service category

-   AWS Management Console: A web-based user interface for accessing and managing AWS resources.
-   AWS Config: A service that helps track resource inventory and changes, providing insight into configuration changes made to AWS resources.
-   Amazon CloudWatch: A monitoring service that provides visibility into resource and application performance.
-   AWS Auto Scaling: A feature that allows you to automatically scale resources to meet demand.
-   AWS Command Line Interface (CLI): A unified tool to manage AWS services from the command line.
-   AWS Trusted Advisor: A tool that helps you optimize performance and security of your AWS infrastructure.
-   AWS Well-Architected Tool: A tool that helps review and improve the design and architecture of your workloads.
-   AWS CloudTrail: A service that tracks user activity and API usage, providing a historical view of actions taken in your AWS account.