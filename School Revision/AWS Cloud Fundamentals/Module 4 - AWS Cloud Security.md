# Module 4: AWS Cloud Security

## Module overview
---
- AWS shared responsibility model
- AWS Identity and Access Management (IAM)
- Securing a new AWS account
- Securing accounts
- Securing data on AWS
- Working to ensure compliance

## Module objectives
---
After completing this module, you should be able to:
- Recognize the shared responsibility model
- Identify the responsibility of the customer and AWS
- Recognize IAM users, groups, and roles
- Describe different types of security credentials in IAM
- Identify the steps to securing a new AWS account
- Explore IAM users and groups
- Recognize how to secure AWS data
- Recognize AWS compliance programs

## Section 1: AWS shared responsibility model
---
### AWS shared responsibility model

-   Security and compliance is a shared responsibility between AWS and the customer
-   The shared responsibility model is designed to relieve the customer's operational burden
-   The customer remains responsible for some aspects of overall security (security "in" the cloud)
-   AWS operates, manages, and controls components from the software virtualization layer down to physical security of facilities where AWS services operate (security "of" the cloud)
-   AWS is responsible for protecting the infrastructure that runs AWS services
-   Customer is responsible for:
    -   Encryption of data at rest and data in transit
    -   Ensuring network security configuration
    -   Safe management of security credentials and logins
    -   Configuration of security groups
    -   Configuration of operating system on compute instances, including updates and security patches

![](https://i.imgur.com/qh3XCZj.png)

### AWS responsibility: Security of the cloud

-   AWS is responsible for the global infrastructure that runs all the services offered in the AWS Cloud, including AWS Regions, Availability Zones, and edge locations.
-   AWS is responsible for the physical security of data centers with controlled, need-based access and 24/7 security guards, two-factor authentication, access logging, video surveillance, and disk degaussing and destruction.
-   AWS is responsible for the hardware infrastructure, including servers, storage devices, and other appliances.
-   AWS is responsible for the software infrastructure that hosts operating systems, service applications, and virtualization software.
-   AWS is responsible for the network infrastructure, including routers, switches, load balancers, firewalls, and cabling.
-   AWS continuously monitors the network at external boundaries and secures access points to ensure the protection of this infrastructure.
-   AWS provides third-party audit reports that verify its compliance with various computer security standards and regulations.

![](https://i.imgur.com/Xvb9E6W.png)

### Customer responsibility: Security in the cloud

-   The customer is responsible for the security of everything they put in the AWS cloud.
-   The security steps required depend on the services used and the complexity of the system.
-   Customer responsibilities include securing instance operating systems, applications, security group configurations, firewall configurations, network configurations, and account management.
-   Customers retain control over their content, including what content is stored, which services are used, location, format, and access rights.
-   Customers are responsible for managing critical content security requirements, such as encryption and masking.
-   Customers retain control over the security they choose to implement for their data, environment, applications, IAM configurations, and operating systems.

![](https://i.imgur.com/zG9fq9D.png)


### Service characteristics and security responsibility

-   Infrastructure as a Service (IaaS) provides basic building blocks for cloud IT and gives customers the highest level of flexibility and control over IT resources.
    -   AWS services like Amazon EC2 are categorized as IaaS and require customers to manage the guest operating system, applications, and security group configurations.
-   Platform as a Service (PaaS) removes the need for customers to manage the underlying infrastructure and focuses on application deployment and management.
    -   AWS services like AWS Lambda and Amazon RDS are categorized as PaaS and AWS operates the infrastructure, operating system, and platforms. Customers are responsible for managing their data and security.
-   Software as a Service (SaaS) provides centrally hosted software accessible through a web browser, mobile app, or API.
    -   AWS services like AWS Trusted Advisor, AWS Shield, and Amazon Chime could be categorized as SaaS offerings and customers do not need to manage the infrastructure.

![](https://i.imgur.com/gTMw4m9.png)

![](https://i.imgur.com/5DiY0Bl.png)

### Key Takeaways

Some key takeaways from this section of the module include:
- AWS and the customer share security responsibilities–
	- AWS is responsible for security ofthe cloud
	- Customer is responsible for security inthe cloud
- AWS is responsible for protecting the infrastructure—including hardware, software, networking, and facilities—that run AWS Cloud services
- For services that are categorized as infrastructure as a service (IaaS), the customer is responsible for performing necessary security configuration and management tasks
	- For example, guest OS updates and security patches, firewall, security group configurations

### Section 2: AWS Identity and Access Management (IAM)
---
### AWS Identity and Access Management (IAM)

-   AWS Identity and Access Management (IAM) allows for control of access to AWS Cloud services such as compute, storage, database, and application services.
-   IAM is used for authentication and authorization policies, specifying which users can access which services.
-   IAM provides central management of access to resources in the AWS account, with granular control over access to resources including API call authorization.
-   IAM enables control over which resources can be accessed by whom, and how they can be accessed, with different permissions granted to different users for different resources.
-   IAM is a feature of the AWS account, available at no additional charge.

### IAM: Essential components



![](https://i.imgur.com/dKL6kis.png)












































