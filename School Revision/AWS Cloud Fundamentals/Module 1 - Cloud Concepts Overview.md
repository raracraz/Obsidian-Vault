# Module 1: Cloud Concepts Overview

## Module overview
---
- Introduction to cloud computing
- Advantages of cloud computing
- Introduction to Amazon Web Services (AWS)
- AWS Cloud Adoption Framework (AWS CAF)

## Module objectives
---
After completing this module, you should be able to:
- Define different types of cloud computing models
- Describe six advantages of cloud computing
- Recognize the main AWS service categories and core services
- Review the AWS Cloud Adoption Framework (AWS CAF)

## Section 1: Introduction to cloud computing
---
### Cloud computing defined

Cloud computing is the on-demand delivery of compute power, database, storage, applications, and other IT resources via the internetwith pay-as-you-gopricing.

### Infrastructure as software

Cloud computing enables you to stop thinking of your infrastructure as hardware, and instead think of (and use) it as software. 

### Cloud service models

![[Pasted image 20230213032429.png]]
There are three main cloud service models: Infrastructure as a Service (IaaS), Platform as a Service (PaaS), and Software as a Service (SaaS). 
- IaaS provides access to the basic components of cloud computing and offers the highest level of control over IT resources. 
- PaaS reduces the need to manage the underlying infrastructure and focuses on application deployment and management. 
- SaaS offers a completed product that the service provider runs and manages, allowing the user to focus only on how they plan to use the software, such as web-based email.

### Cloud computing deployment models

![[Pasted image 20230213032709.png]]
There are three main cloud computing deployment models: cloud, hybrid, and on-premises. 
- A cloud-based deployment is when an application is fully in the cloud. 
- A hybrid deployment connects cloud-based resources to existing non-cloud resources. 
- On-premises deployment, also known as private cloud, uses virtualization and resource management tools to provide dedicated resources, but does not offer the benefits of cloud computing.

### Similarities between AWS and traditional IT

![[Pasted image 20230213033133.png]]
AWS has many similarities with traditional on-premises IT systems: 
- AWS security groups, network access control lists, and IAM are like firewalls, ACLs, and administrators
- Elastic Load Balancing and Amazon VPC are similar to routers, network pipelines, and switches
- Amazon Machine Images and EC2 instances are like on-premises servers
- Amazon EBS, EFS, S3, and RDS are similar to DAS, SAN, NAS, and RDBMS
- AWS can do almost everything that can be done with a traditional data center.

### Key Takeaways from Section 1

Some key takeaways from this section of the module include:
- Cloud computing is the on-demand delivery of IT resources via the internet with pay-as-you-go pricing.
- Cloud computing enables you to think of (and use) your infrastructure as software.
- There are three cloud service models: IaaS, PaaS, and SaaS.
- There are three cloud deployment models: cloud, hybrid, and on-premises or private cloud.
- There are many AWS service analogs for the traditional, on-premises IT space

## Section 2: Advantages of cloud computing
--- 

### Trade capital expense for variable expense

Advantage #1 of cloud computing is the ability to trade capital expenses (money spent on acquiring and maintaining physical assets such as data centers and servers) for variable expenses (money spent only on the resources consumed and only when they are consumed). 

This allows a company to save money on technology and be more flexible in adapting to new applications. Additionally, maintenance is reduced, freeing up resources to focus on the core goals of the business.

### Massive economies of scale

Advantage #2 - Lower variable cost through economies of scale: Cloud computing enables you to benefit from lower variable costs as a result of higher economies of scale achieved by providers such as AWS by aggregating usage from hundreds of thousands of customers. This leads to lower pay-as-you-go prices.

### Stop guessing capacity

Advantage #3 is the ability to stop guessing about infrastructure capacity needs. With cloud computing, you can access the amount of resources you need and easily scale up or down as needed, without worrying about having idle resources or limited capacity.

### Increase speed and agility

Advantage #4: Speed and agility are increased by cloud computing, as new IT resources are easily accessible with just a few clicks. This reduces the time needed to make these resources available to developers from weeks to minutes, leading to a significant increase in organizational agility and a decrease in the cost and time required for experimentation and development.

### Stop spending money on running and maintaining data centers

Advantage #5 - Save money by not running and maintaining data centers: Cloud computing eliminates the need to focus on the maintenance of physical data centers and servers, freeing up resources to focus on differentiating projects and improving customer experience.

### Go global in minutes

Advantage #6: Quick Global Deployment - Cloud computing allows for quick deployment of applications in multiple regions around the world, resulting in lower latency and improved customer experience with minimal cost.

### Key Takeaways

The key takeaways from this section of the module include the six advantages of cloud computing:
- Trade capital expense for variable expense
- Massive economies of scale
- Stop guessing capacity
- Increase speed and agility
- Stop spending money on running and maintaining data centers
- Go global in minutes

## Section 3: Introduction to Amazon Web Services (AWS)
---

### What are web services?

A web service is any piece of software that makes itself available over the internet and uses a standardized format - such as Extensible Markup Language (XML) or JavaScript Object Notation (JSON) - for the request and the response of an application programming interface (API) interaction.

### What is AWS?

- AWS is a secure cloud platform that offers a broad set of global cloud-based products.
- AWS provides you with on-demand access to compute, storage, network, database, and other IT resources and management tools.
- AWS offers flexibility.
- You pay only for the individual services you need, for as long as you use them.
- AWS services work togethe rlike building blocks

### Choosing a service

The service you select depends on your business goals and technology requirements.

![[Pasted image 20230213043013.png]]

AWS offers various compute services for different business goals and technology requirements. Some of these services include Amazon EC2, AWS Lambda, AWS Elastic Beanstalk, Amazon Lightsail, AWS Batch, AWS Outposts, Amazon Elastic Container Service, Amazon Elastic Kubernetes Service, AWS Fargate, and VMware Cloud on AWS. The choice of service will depend on the specific needs of the business.

Here are the different AWS compute services and their main use cases:

1.  Amazon EC2: Complete control over AWS computing resources.
2.  AWS Lambda: Run code without managing or provisioning servers.
3.  AWS Elastic Beanstalk: Automated deployment, management, and scaling of web applications.
4.  Amazon Lightsail: Lightweight cloud platform for simple web applications.
5.  AWS Batch: Running batch workloads.
6.  AWS Outposts: Running AWS infrastructure in on-premises data center.
7.  Amazon Elastic Container Service (Amazon ECS): Implementation of containers or microservices architecture.
8.  Amazon Elastic Kubernetes Service (Amazon EKS): Implementation of Kubernetes architecture.
9.  AWS Fargate: Implementation of containers or microservices architecture.
10.  VMware Cloud on AWS: Migration of on-premises server virtualization platform to AWS.

These are just some of the many services offered by AWS, and the offerings keep growing.

### Three ways to interact with AWS

The three ways to access and manage resources on AWS Cloud are:

1.  AWS Management Console - provides a graphical interface to the majority of the features offered by AWS
2.  AWS Command Line Interface (AWS CLI) - a suite of utilities that can be launched from a command script in Linux, macOS, or Windows
3.  Software Development Kits (SDKs) - packages that enable accessing AWS in popular programming languages, making it easy to use AWS in existing applications and creating new applications through code. All three options are built on a common REST-like API.

### Key Takeaways

The key takeaways from this section of the module include:
- AWS is a secure cloud platform that offers a broad set of global cloud-based products called services that are designed to work together.
- There are many categories of AWS services, and each category has many services to choose from.
- Choose a service based on your business goals and technology requirements.
- There are three ways to interact with AWS services.

## Section 4: Moving to the AWS Cloud - The AWS Cloud Adoption Framework (AWS CAF)
---

### AWS Cloud Adoption Framework (AWS CAF)

The AWS Cloud Adoption Framework (AWS CAF) provides guidelines and best practices for organizations looking to migrate their IT portfolio to the cloud. For a successful migration, it is important to have alignment between people, process, and technology. The AWS CAF helps organizations identify skills and process gaps and provides a comprehensive approach to cloud computing throughout the IT lifecycle. The framework is organized into six perspectives, each covering people, processes, and technology, with a set of capabilities for each perspective. By identifying gaps, organizations can create prescriptive work streams to support a successful cloud journey.

### Six core perspectives

In general, the Business, People, and Governance perspectives focus on business capabilities, while the Platform, Security, and Operations perspectives focus on technical capabilities.

![[Pasted image 20230213043327.png]]

### 1. Business perspective

The AWS Cloud Adoption Framework can be used by stakeholders in the Business perspective, such as business managers, finance managers, budget owners, and strategy stakeholders, to create a strong case for cloud adoption and prioritize cloud initiatives. They should align the business and IT strategies and goals for a successful cloud adoption.

![[Pasted image 20230213043407.png]]

### 2. People perspective

The AWS CAF can be used by stakeholders from the People perspective, such as human resources, staffing, and people managers, to analyze the organizational structures and roles, identify new skill and process requirements, and evaluate any gaps. This can help prioritize training, staffing, and organizational changes to build an agile organization

![[Pasted image 20230213043557.png]]

### 3. Governance perspective

Stakeholders from the Governance perspective (such as the CIO, program managers, enterprise architects, etc.) can use the AWS Cloud Adoption Framework (AWS CAF) to align IT strategies with business strategies and goals, maximize the business value of IT investment and minimize business risks. This involves focusing on the necessary skills and processes.

![[Pasted image 20230213043640.png]]

### 4. Platform perspective

Stakeholders from the Platform perspective, such as CTOs, IT managers, and solutions architects, use the AWS CAF to understand and communicate the nature of IT systems and their relationships through architectural dimensions and models. The CAF provides guidance on implementing new solutions on the cloud and migrating on-premises workloads to the cloud, and helps these stakeholders describe the architecture of the target state environment in detail.

![[Pasted image 20230213043727.png]]

### 5. Security perspective

Stakeholders from the Security perspective, such as CISO, IT security managers, and IT security analysts, use the AWS CAF to implement security measures to meet the organization's objectives for visibility, auditability, control, and agility. The AWS CAF helps these stakeholders choose and implement security controls to meet the organization's security needs.

![[Pasted image 20230213043817.png]]

### 6. Operations perspective

Stakeholders from the Operations perspective use the AWS CAF to align their day-to-day operations with the business and support its operations. They define current operating procedures and use the framework to identify the process changes and training needed for successful cloud adoption.

![[Pasted image 20230213043842.png]]

### Key Takeaways

The key takeaways from this section of the module include:
- Cloud adoption is not instantaneous for most organizations and requires a thoughtful, deliberate strategy and alignment across the whole organization.
- The AWS CAF was created to help organizations develop efficient and effective plans for their cloud adoption journey.
- The AWS CAF organizes guidance into six areas of focus, called perspectives.
- Perspectives consist of sets of business or technology capabilities that are the responsibility of key stakeholders.