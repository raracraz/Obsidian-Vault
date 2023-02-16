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

- Containers are a method of operating system virtualization
- Benefits:
	- Repeatable
	- Self-contained environments
	- Software runs the same in different environments
		- Dev laptop, test, production
	- Faster to launch or stop or terminate than virtual machines

![](https://i.imgur.com/G1KZRzp.png)

### What is Docker?

- Docker enables you to build, test and deploy containers quickly
- A container has everything a software application needs to run

![](https://i.imgur.com/DbT6kcR.png)

### Containers versus virtual machines

-   Virtual machines run directly on a hypervisor, while containers can run on any Linux OS with appropriate kernel feature support and Docker daemon
-   Containers are highly portable and can run on various hosts, including laptops, VMs, EC2 instances, and bare metal servers
-   The right side of the diagram shows a virtual machine-based deployment where each EC2 instance runs its own VM to provide process isolation for each app
-   The left side of the diagram shows a container-based deployment where only one EC2 instance runs a virtual machine with three containers, each running its own app with process isolation
-   Containers communicate directly to the kernel in the Linux guest OS and are unaware of their container silo
-   The Docker engine manages how the containers run on the Linux guest OS and provides essential management functions throughout the container lifecycle.

![](https://i.imgur.com/LNc2zB3.png)

### Amazon Elastic Container Service (Amazon ECS)

-   AWS offers Amazon Elastic Container Service (Amazon ECS) to simplify container management
-   Amazon ECS is a highly scalable and high-performance container management service that supports Docker containers
-   Amazon ECS allows for easy deployment of applications on a managed cluster of Amazon EC2 instances
-   Key features of Amazon ECS include the ability to launch tens of thousands of Docker containers in seconds, monitor container deployment, manage the state of the container cluster, and schedule containers using a built-in or third-party scheduler (e.g., Apache Mesos or Blox).

![](https://i.imgur.com/S5tjMzA.png)

### Amazon ECS orchestrates containers

-   To run your application on Amazon ECS, you need to create a task definition, which is a text file that describes one or more containers that make up your application.
-   Task definitions can specify various parameters, such as which containers to use, which ports to open, and which data volumes to use.
-   A task is the instantiation of a task definition within a cluster, and you can specify how many tasks will run on your cluster.
-   The Amazon ECS task scheduler is responsible for placing tasks within your cluster, and a task can run anywhere from one to ten containers.
-   An ECS cluster is made up of a group of EC2 instances that are running an Amazon ECS container agent.
-   Amazon ECS provides multiple scheduling strategies to place containers across your clusters based on your resource needs and availability requirements.

![](https://i.imgur.com/fUztwvC.png)

### Amazon ECS cluster options

-   There are three options for creating an Amazon ECS cluster: Networking Only cluster (powered by AWS Fargate), EC2 Linux + Networking cluster, and EC2 Windows + Networking cluster.
-   If you choose the EC2 launch type options, you need to specify details about the EC2 instances that make up your cluster, including On-Demand or Spot Instances.
-   The EC2 launch type provides granular control over the infrastructure that runs your container applications because you manage the EC2 instances that make up the cluster.
-   Amazon ECS keeps track of all the CPU, memory, and other resources in your cluster and finds the best server for your container based on your specified resource requirements.
-   If you choose the networking-only Fargate launch type, the cluster that runs your containers will be managed by AWS.
-   With the Fargate option, you only need to package your application in containers, specify the CPU and memory requirements, define networking and IAM policies, and launch the application.
-   Fargate removes the need to provision, configure, or scale the cluster and enables you to focus on designing and building your applications.

![](https://i.imgur.com/RF8Q3W0.png)

### What is Kubernetes?

-   Kubernetes is open source software for container orchestration that works with many containerization technologies, including Docker
-   Kubernetes has a large community of developers and companies that build extensions, integrations, and plugins to keep the software relevant and add new features
-   Kubernetes enables deployment and management of containerized applications at scale, using the same toolset in both on-premises data centers and the cloud
-   Kubernetes manages a cluster of compute instances called nodes and runs containers based on resource availability and requirements, in logical groupings called pods
-   Pods are given IP addresses and DNS names, which Kubernetes uses to connect services with each other and external traffic
-   Kubernetes allows for running containerized applications anywhere without needing to change operational tooling, for example, moving from local development machines to cloud production deployments

![](https://i.imgur.com/Ux33U7s.png)

### Amazon Elastic Kubernetes Service (Amazon EKS)

-   Amazon Elastic Kubernetes Service (Amazon EKS) is a managed Kubernetes service that simplifies the management of Kubernetes clusters.
-   It allows you to run Kubernetes on AWS without the need to install, operate, and maintain your own Kubernetes control plane.
-   Amazon EKS is certified Kubernetes conformant, making it compatible with existing applications that run on upstream Kubernetes.
-   Amazon EKS automatically manages the availability and scalability of the cluster nodes responsible for starting and stopping containers, scheduling containers on virtual machines, storing cluster data, and other tasks.
-   It also detects and replaces unhealthy control plane nodes for each cluster automatically.
-   Amazon EKS allows you to take advantage of the performance, scale, reliability, and availability of the AWS Cloud, including AWS networking and security services like Application Load Balancers for load distribution, IAM for role-based access control, and VPC for pod networking.
-   Amazon offers both Amazon ECS and Amazon EKS to provide customers with flexible options to choose the option that best matches their needs.

### Amazon Elastic Container Registry (Amazon ECR)

-   Amazon Elastic Container Registry (Amazon ECR) is a fully managed Docker container registry.
-   It makes it easy for developers to store, manage, and deploy Docker container images.
-   Amazon ECR is integrated with Amazon ECS, which allows for storing, running, and managing container images for applications that run on Amazon ECS.
-   Amazon ECR supports Docker Registry HTTP API version 2, which enables interacting with Amazon ECR using Docker CLI commands or preferred Docker tools.
-   Container images can be transferred to and from Amazon ECS via HTTPS and are automatically encrypted at rest using Amazon S3 server-side encryption.
-   Amazon ECR images can be used with Amazon EKS.

![](https://i.imgur.com/XaJArkm.png)


### Key Takeaways

Some key takeaways from this section include:
- Containers can hold everything that an application needs to run.
- Docker is a software platform that packages software into containers. 
- A single application can span multiple containers.
- Amazon Elastic Container Service (Amazon ECS) orchestrates the running of Docker containers.
- Kubernetes is open source software for container orchestration. 
- Amazon Elastic Kubernetes Service (Amazon EKS) enables you to run Kubernetes on AWS
- Amazon Elastic Container Registry (Amazon ECR) enables you to store, manage, and deploy your Docker containers

## Section 5: Introduction to AWS Lambda

### AWS Lambda: Run code without servers

-   AWS offers multiple compute options, including virtual machines and container-based services.
-   Serverless computing is a third approach to compute that does not require server provisioning or management.
-   AWS Lambda is an event-driven, serverless compute service.
-   Lambda functions contain the code that you upload and are triggered on a scheduled basis or in response to an event.
-   Code only runs when triggered, and you are only charged for the compute time you consume.

![](https://i.imgur.com/NAYy4Z8.png)

### Benefits of Lambda

-   AWS Lambda is a serverless compute service that runs your code without needing to provision or manage servers.
-   It supports multiple programming languages, including Java, Go, PowerShell, Node.js, C#, Python, and Ruby, and allows the use of native or third-party libraries.
-   Lambda automates the administration, maintenance, and security patches, and provides built-in logging and monitoring through Amazon CloudWatch.
-   Lambda is fault-tolerant, maintains compute capacity across multiple Availability Zones, and has no maintenance windows or scheduled downtimes.
-   AWS Step Functions can be used to orchestrate multiple Lambda functions for complex or long-running tasks.
-   With Lambda, you only pay for the requests served and the compute time required, with billing metered in increments of 100 milliseconds, making it cost-effective and scalable from a few requests per day to thousands of requests per second.

![](https://i.imgur.com/xLYdF8G.png)

### AWS Lambda event sources

-   An event source is a service or application that produces events that trigger an AWS Lambda function to run.
-   Some services publish events to Lambda by invoking the Lambda function directly, including Amazon S3, Amazon SNS, and Amazon CloudWatch Events.
-   Lambda can also poll resources in other services that do not publish events to Lambda, such as Amazon SQS and Amazon DynamoDB.
-   Some services like Elastic Load Balancing and Amazon API Gateway can invoke Lambda functions directly.
-   You can also invoke Lambda functions directly using various methods, such as the Lambda console, API, SDK, CLI, and toolkits.
-   Lambda automatically monitors functions using Amazon CloudWatch, and logs all requests that are handled by the function.

![](https://i.imgur.com/6RtH6z9.png)

### AWS Lambda function configuration

-   A Lambda function is custom code to process events, which Lambda runs on your behalf.
-   When creating a Lambda function using the AWS Management Console, you give it a name, specify the runtime environment, and an execution role.
-   After creating the function, you can configure it by adding a trigger, specifying the function code, and allocating memory (128 MB to 10,240 MB).
-   You can also add environment variables, a description, timeout, and other settings.
-   These settings end up in a Lambda deployment package, which is a ZIP archive that contains your function code and dependencies.
-   The Lambda console manages the package for you, but you need to create one if you use the Lambda API to manage functions.

![](https://i.imgur.com/MeC9UiN.png)

### Schedule-based Lambda function example: Start and stop EC2 instance

-   A schedule-based Lambda function can be used to reduce Amazon EC2 usage
-   AWS Lambda and Amazon CloudWatch Events can be configured to automate the process
-   CloudWatch event is scheduled to run a Lambda function to stop EC2 instances at a predefined time
-   The Lambda function runs with an IAM role that grants it permission to stop EC2 instances
-   EC2 instances enter the stopped state
-   Another CloudWatch event is scheduled to run a Lambda function to start EC2 instances at a predefined time in the morning
-   The Lambda function runs with an IAM role that grants it permission to start EC2 instances
-   EC2 instances enter the running state

![](https://i.imgur.com/af1qc5p.png)

### Event-based Lambda function example: Create thumbnail images

-   A user uploads an object to an S3 bucket (object-created event).
-   S3 detects the object-created event.
-   S3 invokes the Lambda function and passes event data.
-   The Lambda function runs with the IAM role that gives it permission to access the source and target S3 buckets.
-   Based on the event data, the Lambda function knows the source bucket name and object key name, reads the object, and creates a thumbnail using graphics libraries.
-   The Lambda function saves the thumbnail to the target bucket.

![](https://i.imgur.com/xyATXMR.png)

### AWS Lambda quotas

Soft limits per Region:

-   Concurrent executions: 1,000
-   Function and layer storage: 75 GB

Hard limits for individual functions:

-   Maximum function memory allocation: 10,240 MB
-   Function timeout: 15 minutes
-   Deployment package size: 250 MB unzipped, including layers
-   Container image code package size: 10 GB

### Key Takeaways

Some key takeaways from this section of the module include:
- Serverless computing enables you to build and run applications and services without provisioning or managing servers. 
- AWS Lambda is a serverless compute service that provides built-in fault tolerance and automatic scaling.
- An event source is an AWS service or developer-created application that triggers a Lambda function to run. 
- The maximum memory allocation for a single Lambda function is 10,240 MB. 
- The maximum run time for a Lambda function is 15 minutes

## Section 6: Introduction to AWS Elastic Beanstalk
---

### AWS Elastic Beanstalk

-   AWS Elastic Beanstalk is a PaaS for the deployment, scaling, and management of web applications and services.
-   You remain in control of your application and only need to upload your code.
-   You can choose your instance type, database, set up automatic scaling, update your application, access server log files, and enable HTTPS on the load balancer.
-   Elastic Beanstalk handles the deployment process, including capacity provisioning, load balancing, scaling, and monitoring application health.
-   You have full control over the underlying AWS resources that power your application and can access them at any time.
-   There is no additional charge for Elastic Beanstalk. You only pay for the AWS resources you use, with no minimum fees or upfront commitments.

### AWS Elastic Beanstalk deployments

-   AWS Elastic Beanstalk allows you to deploy your code using the AWS Management Console, AWS CLI, Visual Studio, and Eclipse.
-   Elastic Beanstalk provides all the application services you need for your application, and you only need to create your code.
-   Elastic Beanstalk supports a wide range of platforms, including Docker, Go, Java, .NET, Node.js, PHP, Python, and Ruby.
-   Elastic Beanstalk deploys your code on Apache Tomcat for Java, Apache HTTP Server for PHP and Python, NGINX or Apache HTTP Server for Node.js, Passenger or Puma for Ruby, and Microsoft Internet Information Services (IIS) for .NET applications, Java SE, Docker, and Go.

### Benefits of Elastic Beanstalk

-   Elastic Beanstalk is easy to use and handles deployment details automatically.
-   It saves developer time by allowing them to focus on writing code.
-   AWS updates the underlying platform to run your application with patches and updates.
-   Elastic Beanstalk can handle peaks in workload and scales your application based on its needs.
-   You can select optimal AWS resources, like Amazon EC2 instance type, for your application.
-   You retain full control over the AWS resources that power your application.
-   You can seamlessly take over some or all of the elements of your infrastructure by using Elastic Beanstalk's management capabilities.

### Key Takeaways

Some key takeaways from this section of the module include:
- AWS Elastic Beanstalk enhances developer productivity.
	- Simplifies the process of deploying your application.
	- Reduces management complexity.
- Elastic Beanstalk supports Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker.
- There is no charge for Elastic Beanstalk. Pay only for the AWS resources you use. 
