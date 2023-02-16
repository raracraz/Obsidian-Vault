# Module 6: Compute

## Module overview
---
- Compute services overview
- Amazon EC2
- Amazon EC2 cost optimization
- Container services
- Introduction to AWS Lambda
- Introduction to AWS Elastic Beanstalk

## Module objectives
---
After completing this module, you should be able to:
- Provide an overview of different AWS compute services in the cloud
- Demonstrate why to use Amazon Elastic Compute Cloud (Amazon EC2)
- Identify the functionality in the EC2 console
- Perform basic functions in EC2 to build a virtual computing environment
- Identify EC2 cost optimization elements
- Demonstrate when to use AWS Elastic Beanstalk
- Demonstrate when to use AWS Lambda
- Identify how to run containerized applications in a cluster of managed servers

## Section 1: Compute services overview
---

### AWS compute services

-   Amazon EC2: resizable virtual machines
-   Amazon EC2 Auto Scaling: automatically launches or terminates EC2 instances to support application availability
-   Amazon ECR: stores and retrieves Docker images
-   Amazon ECS: container orchestration service that supports Docker
-   VMware Cloud on AWS: provisions a hybrid cloud without custom hardware
-   AWS Elastic Beanstalk: runs and manages web applications
-   AWS Lambda: serverless compute solution, pay only for the compute time used
-   Amazon EKS: runs managed Kubernetes on AWS
-   Amazon Lightsail: simple-to-use service for building an application or website
-   AWS Batch: tool for running batch jobs at any scale
-   AWS Fargate: runs containers that reduce the need to manage servers or clusters
-   AWS Outposts: runs select AWS services in on-premises data center
-   AWS Serverless Application Repository: discovers, deploys, and publishes serverless applications.

### Categorizing compute services

-   AWS compute services fall into four categories: virtual machines (VMs), serverless, container-based, and platform as a service (PaaS).
-   Amazon EC2 is a virtual machine service that provides infrastructure as a service (IaaS).
-   AWS Lambda is a serverless compute platform that enables you to run code without managing servers and paying only for consumed compute time.
-   Container-based services such as Amazon Elastic Container Service, Amazon Elastic Kubernetes Service, AWS Fargate, and Amazon Elastic Container Registry allow running multiple workloads on a single operating system and spin up more quickly than VMs.
-   AWS Elastic Beanstalk is a PaaS service that simplifies the deployment of applications by managing the OS, application server, and infrastructure components.

![](https://i.imgur.com/x2LqDGD.png)

### Choosing the optimal compute service

-   AWS offers various compute services because different use cases benefit from different compute environments.
-   The optimal compute service(s) for a specific use case depends on that use case.
-   Compute architecture is often determined by legacy code but it can be evolved to take advantage of cloud-native designs.
-   Best practices for compute services include evaluating available options, understanding configuration options, collecting computer-related metrics, using available elasticity of resources, and re-evaluating compute needs based on metrics.

## Section 2: Amazon EC2
---

### Amazon Elastic Compute Cloud (Amazon EC2)

-   Running servers on-premises can be expensive
-   Procuring hardware can be based on project plans rather than actual usage
-   Data centers are expensive to build, staff, and maintain
-   Unused server capacity is wasteful
-   Amazon Elastic Compute Cloud (Amazon EC2) provides virtual machines in the cloud
-   EC2 instances provide secure, resizable compute capacity
-   EC2 instances can support various workloads, including application, web, database, game, mail, media, catalog, file, computing, and proxy servers.

![](https://i.imgur.com/OTkiSka.png)

### Amazon EC2 overview

-   EC2 stands for Elastic Compute Cloud
-   Elastic refers to the ability to easily increase or decrease the number and size of servers
-   Compute refers to the hosting of running applications or processing of data, which requires compute resources like processing power and memory
-   Cloud refers to the fact that EC2 instances are hosted in the cloud
-   Amazon EC2 provides virtual machines with full administrative control over the operating system
-   Supported operating systems include Windows 2008, 2012, 2016, and 2019, Red Hat, SuSE, Ubuntu, and Amazon Linux
-   Instances can be launched in any Availability Zone worldwide in minutes from Amazon Machine Images (AMIs)
-   Traffic to and from instances can be controlled using security groups
-   Solutions can be built using multiple AWS services because servers run in the AWS Cloud.

### Launching an Amazon EC2 instance

-   The first time launching an Amazon EC2 instance, most users will likely use the AWS Management Console Launch Instance Wizard
-   The Launch Instance Wizard makes it easy to launch an instance with default settings in as few as six clicks
-   However, for most deployments, it is important to modify the default settings to match specific needs
-   The next series of slides introduce essential choices that must be made when launching an instance
-   Essential concepts are covered to help understand the available options and effects of the decisions made.

### Key Takeaways

Some key takeaways from this section of the module include:
- Amazon EC2 enables you to run Windows and Linux virtual machines in the cloud.
- You launch EC2 instances from an AMI template into a VPC in your account.
- You can choose from many instance types. Each instance type offers different combinations of CPU, RAM, storage, and networking capabilities.
- You can configure security groups to control access to instances (specify allowed ports and source).
- User data enables you to specify a script to run the first time that an instance launches. 
- Only instances that are backed by Amazon EBS can be stopped. 
- You can use Amazon CloudWatch to capture and review metrics on EC2 instances

## Section 3: Amazon EC2 cost optimization

### Amazon EC2 pricing models

-   Amazon offers different pricing models for running EC2 instances
-   Per-second billing is available for On-Demand Instances, Reserved Instances, and Spot Instances that run Amazon Linux or Ubuntu
-   On-Demand Instances have no upfront cost or long-term contracts and are a good choice for short-term, spiky, or unpredictable workloads
-   Dedicated Hosts are physical servers with instance capacity dedicated to the customer's use, allowing the use of existing per-socket, per-core, or per-VM software licenses
-   Dedicated Instances run in a virtual private cloud on hardware dedicated to a single customer, physically isolated at the host hardware level from instances belonging to other AWS accounts
-   Reserved Instances allow for reserving computing capacity for 1- or 3-year terms at lower hourly running costs with a fixed discounted usage price for the duration of ownership, providing savings for consistent, heavy use
-   Scheduled Reserved Instances allow for purchasing capacity reservations that recur on a daily, weekly, or monthly basis with a specified duration for a 1-year term, charging for the scheduled time even if not used
-   Spot Instances allow for bidding on unused EC2 instances to lower costs, with the hourly price fluctuating depending on supply and demand, and running whenever the bid exceeds the current market price.

### Amazon EC2 pricing models: Benefits

-   On-Demand Instances: most flexible, no long-term contract, low rates, good for short-term, spiky or unpredictable workloads.
-   Spot Instances: large scale at a significantly discounted price, bid on unused EC2 instances.
-   Reserved Instances: good for predictable or steady-state compute needs, lower hourly running costs for 1-year or 3-year term, fixed discounted usage price for the life of the instance.
-   Dedicated Hosts: good for software licensing restrictions, compliance or regulatory requirements, physical servers with dedicated instance capacity.
-   Dedicated Instances: physically isolated instances running in a virtual private cloud on hardware dedicated to a single customer.

![](https://i.imgur.com/zBfh034.png)

### Amazon EC2 pricing models: Use cases

-   On-Demand Instances: good for spiky workloads or short-term testing and development.
-   Spot Instances: good for fault-tolerant applications that can tolerate interruption, and workloads that constantly save data to persistent storage.
-   Reserved Instances: good for long-term workloads with predictable usage patterns.
-   Dedicated Hosts: good when you have existing software licenses or need to meet specific compliance and regulatory requirements.

![](https://i.imgur.com/hD0JZwG.png)

### The four pillars of cost optimization

-   Right-size instances by choosing the appropriate balance of instance types and monitoring server performance to identify instances that can be downsized or turned off.
-   Increase elasticity by designing deployments to minimize idle server capacity, using elastic deployments such as automatic scaling to handle peak loads.
-   Analyze available pricing options to determine the right mix of pricing models based on usage patterns.
-   Optimize storage choices by analyzing storage requirements, reducing unused storage overhead, and choosing less expensive storage options that meet performance requirements.

![](https://i.imgur.com/Iq8jDwu.png)


### Pillar 1: Right size

-   Right-sizing is the process of reviewing deployed resources to downsize instances when possible to optimize costs
-   To right-size, select the cheapest instance available that still meets performance requirements
-   Review CPU, RAM, storage, and network utilization to identify instances that could be downsized
-   Provision a variety of instance types and sizes in a test environment and test application on different deployments to identify best performance-to-cost ratio
-   Use techniques such as load testing and Amazon CloudWatch metrics to your advantage to optimize instance choices.

![](https://i.imgur.com/KE1gYWy.png)

### Pillar 2: Increase elasticity

-   Elasticity is a central tenet of the cloud, allowing you to create, start, or use EC2 instances when they're needed and then turn them off when they're not in use.
-   Customers often need to learn how to operationalize elasticity to drive cost savings.
-   Look for resources that are good candidates for stopping or hibernating, such as non-production environments, development workloads, or test workloads.
-   For production workloads, configure more precise and granular automatic scaling policies to take advantage of horizontal scaling and meet peak capacity needs while avoiding paying for peak capacity all the time.
-   Target 20-30% of your Amazon EC2 instances to run as On-Demand Instances or Spot Instances and actively look for ways to maximize elasticity.

![](https://i.imgur.com/uMV4Q7s.png)

### Pillar 3: Optimal pricing model

-   AWS provides several pricing models for Amazon EC2 to help customers save money.
-   Customers can combine multiple purchase types to optimize pricing based on their current and forecast capacity needs.
-   It is essential to consider your application architecture to determine if the functionality provided by your application needs to run on an EC2 virtual machine or if an AWS Lambda service could be used to decrease costs significantly.

![](https://i.imgur.com/AvI3OCH.png)

### Pillar 4: Optimize storage choices

-   AWS customers can reduce storage costs by trying to maintain storage performance and availability while reducing costs.
-   Resizing EBS volumes is one way to reduce costs. Customers can reduce the size of a volume that is larger than the storage space needed.
-   Customers should choose the least expensive EBS volume type that still meets their performance requirements.
-   EBS snapshots are commonly used for data backups, but customers should delete unneeded snapshots to save on costs.
-   Customers should identify the most appropriate destination for specific types of data. They should consider using Amazon S3 for storage instead of Amazon EBS when possible.
-   Configuring data lifecycle policies can help reduce costs by automating the migration of older infrequently accessed data to cheaper storage locations like Amazon S3 Glacier.

![](https://i.imgur.com/Z0WyF44.png)

### Measure, monitor, and improve

-   Cost optimization is an ongoing process that involves measuring and analyzing systems to continually improve and adjust costs.
-   Tagging helps provide information about what resources are being used by whom and for what purpose. Cost allocation tags can be activated in the Billing and Cost Management console, and AWS can generate a cost allocation report with usage and costs grouped by active tags.
-   Apply tags that represent business categories (such as cost centers, application names, or owners) to organize costs across multiple services.
-   Encourage teams to architect for cost and use free tools like AWS Cost Explorer to view graphs of costs, see spending patterns over time, identify areas that need further inquiry, and understand trends.
-   Use AWS services such as AWS Trusted Advisor to get real-time guidance on how to provision resources that follow AWS best practices.
-   Assign responsibility for cost optimization to an individual or team for more successful cost optimization efforts.

### Key Takeaways

Some key takeaways from this section of the module are:
- Amazon EC2 pricing modelsinclude On-Demand Instances, Reserved Instances, Spot Instances, Dedicated Instances, and Dedicated Hosts. Per second billing is available for On-Demand Instances, Reserved Instances, and Spot Instances that use only Amazon Linux and Ubuntu. 
- Spot Instances can be interrupted with a 2-minute notification. However,they can offer significant cost savings over On-Demand Instances
- The four pillars of cost optimization are
	- Right size
	- Increase elasticity
	- Optimal pricing model
	- Optimize storage choices

## Section 4: Container services
---

### Container basics



![](https://i.imgur.com/G1KZRzp.png)




























































