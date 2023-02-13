# Module 2: Cloud Economics and Billing

## Module overview
---
- Fundamentals of pricing
- Total Cost of Ownership
- AWS Organizations
- AWS Billing and Cost Management
- Technical Support

## Module objectives
---
After completing this module, you should be able to:
- Explain the AWS pricing philosophy
- Recognize fundamental pricing characteristics
- Indicate the elements of total cost of ownership
- Discuss the results of the AWS Pricing Calculator
- Identify how to set up an organizational structure that simplifies billing and account visibility to review cost data.
- Identify the functionality in the AWS Billing Dashboard
- Describe how to use AWS Bills, AWS Cost Explorer, AWS Budgets, and AWS Cost and Usage Reports
- Identify the various AWS technical support plans and features

## Section 1: Fundamentals of pricing
---

### AWS pricing model

The three main factors affecting cost on AWS are:

- compute - Charged per hour/second
- storage - Charged typically per GB
- outbound data transfer  - Charged typically per GB

which can vary based on the chosen product and pricing model. In general, there is no cost for inbound data transfer or transfer between AWS services within the same region. However, it's important to check for exceptions. Outbound data transfer costs are combined across services and billed at a specific rate, which is listed as "AWS Data Transfer Out" on the monthly statement.

### How do you pay for AWS?

AWS pricing is based on a philosophy of paying for what you use, with no long-term contracts required. You can start or stop using a service at any time and pay only for the resources you actually need. The pricing model is utility-style, with options such as:
- Pay for what you use
- Pay less when you reserve
- Pay less when you use more
- Pay even less as AWS grows

### 1. Pay for what you use

This AWS pricing model is based on a pay-as-you-go approach, allowing users to only pay for the services they use without any upfront expenses. This reduces variable costs and allows users to quickly adapt to changing business needs, freeing up resources to focus on innovation. The services are available on demand, with no long-term contracts or complex licensing dependencies.

![](https://i.imgur.com/OkI3IaT.png)


### 2. Pay less when you reserve

Reserved capacity for services like Amazon EC2 and Amazon RDS can save up to 75% compared to on-demand options. There are three types of reserved instances with different upfront payment options (All Upfront, Partial Upfront, and No Upfront) that offer different discounts. Choosing reserved capacity helps minimize risks, manage budgets, and meet long-term commitment policies.

Options:
- All Upfront reserved instance (AURI)
- Partial Upfront reserved instance (PURI)
- No Upfront reserved instance (NURI)

![](https://i.imgur.com/qyf67R4.png)


### 3. Pay less by using more

With AWS, you can save money through volume-based discounts as your usage grows. Services like Amazon S3 have tiered pricing, where you pay less per GB as you use more. Data transfer is always free and multiple storage services offer lower costs based on your needs. As your organization evolves, AWS offers services to address your business needs and help you optimize savings by choosing the right combination of storage solutions that balance cost, performance, security, and durability.

![](https://i.imgur.com/lSr32uH.png)


### 4. Pay even less as AWS grows

AWS is committed to reducing costs in data centers by optimizing hardware, operations, power consumption, and general expenses. These cost-saving measures and the large scale economies of AWS result in lower pricing for customers. AWS has lowered pricing 75 times since 2006 and as the company grows, customers can also enjoy upgrades to higher-performing resources at no additional cost.

![](https://i.imgur.com/XoajYX4.png)


### Custom pricing:

AWS realizes that every customer has different needs. If none of the AWS pricing models work for your project, custom pricing is available for high-volume projects with unique requirements.

### AWS Free Tier:

AWS offers a free usage tier, the AWS Free Tier, for new customers for up to one year. The free tier applies to certain services and options, including a free Amazon EC2 T2 micro instance and free usage of Amazon S3, Amazon EBS, Elastic Load Balancing, data transfer, and other AWS services. This is a helpful resource for new AWS customers to get started in the cloud.

![](https://i.imgur.com/mkCysa2.png)


### Services with no charge:

AWS also offers a variety of services for no additional charge.
- **Amazon Virtual Private Cloud** (Amazon VPC) enables you to provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.

- **AWS Identity and Access Management** (IAM) controls your users’ access to AWS services and resources.

- **Consolidated Billing** is a billing feature in AWS Organizations to consolidate payment for multiple AWS accounts or multiple Amazon Internet Services Private Limited (AISPL) accounts*. Consolidated billing provides:
	- One bill for multiple accounts.
	- The ability to easily track each account’s charges.
	- The opportunity to decrease charges as a result of volume pricing discounts from combined usage.
	- And you can consolidate all of your accounts using Consolidated Billing and get tiered benefits.

- **AWS Elastic Beanstalk** is an even easier way for you to quickly deploy and manage applications in the AWS Cloud.

- **AWS CloudFormation** gives developers and systems administrators an easy way to create a collection of related AWS resources and provision them in an orderly and predictable fashion.

- **Automatic Scaling** automatically adds or removes resources according to conditions you define. The resources you are using increase seamlessly during demand spikes to maintain performance and decrease automatically during demand lulls to minimize costs.

- **AWS OpsWorks** is an application management service that makes it easy to deploy and operate applications of all shapes and sizes.

![](https://i.imgur.com/sD3rieU.png)



### Key Takeaways:

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
-   Outbound data transfer costs are tiered and can be confirmed before using the service.

## Section 2: Total Cost of Ownership
---

### On-premises versus cloud

On-premises vs Cloud:

-   On-premises infrastructure is installed locally on a company's computers and servers
    -   Fixed costs (capital expenses) include facilities, hardware, licenses, and maintenance staff
    -   Scaling up is expensive and time-consuming
    -   Scaling down does not reduce fixed costs
-   Cloud infrastructure is purchased from a service provider
    -   Provider builds and maintains facilities, hardware, and maintenance staff
    -   Customer pays for what is used
    -   Scaling up or down is simple
    -   Costs are easy to estimate based on service use
-   Comparison of on-premises and AWS Cloud:
    -   On-premises IT involves capital expenditure, long planning cycles, and multiple components to manage and refresh resources over time
    -   AWS Cloud offers flexibility, agility, and consumption-based costs
-   Identifying the best option:
    -   Depends on company's needs for flexibility, agility, and cost management.

![](https://i.imgur.com/nuQxAN7.png)


### What is Total Cost of Ownership (TCO)?    

-   To identify the best option between on-premises and cloud solutions, you can compare Total Cost of Ownership (TCO)
-   TCO is a financial estimate that considers direct and indirect costs of a product or system
-   TCO includes the cost of the service plus all costs associated with owning the service
-   Compare costs of running entire infrastructure environment for a specific workload in an on-premises vs. cloud-based infrastructure
-   Comparison is done for budgeting purposes or to build a business case for deployment solution decisions

![](https://i.imgur.com/XY4WRM6.png)


### TCO considerations

-   Costs associated with data center management
    -   Server costs: hardware, software, facilities
    -   Storage costs: hardware, administration, facilities
    -   Network costs: hardware, administration, facilities
    -   IT labor costs for administration
-   Comparison of on-premises and cloud solutions
    -   Cloud solution:
        -   Upfront costs that are transparent and readily calculated
        -   Based on usage metrics: RAM, storage, bandwidth, etc.
        -   Pricing is fixed per unit of time
    -   On-premises technology:
        -   Direct costs: power, floor space, storage, IT operations
        -   Indirect costs: network and storage infrastructure

![](https://i.imgur.com/GEgye4E.png)


### On-premises versus all-in-cloud

-   Cost Comparison: On-premises solution vs. Cloud solution over 3 years
-   Two similar environments constructed to represent on-premises and AWS environments
-   On-premises solution components:
    -   1 virtual machine with 4 CPUs, 16 GB of RAM, Linux operating system
    -   Average utilization is 100%
    -   Optimized by RAM
-   AWS environment components:
    -   1 m4.xlarge instance with 4 CPUs, 16 GB of RAM
    -   Instance type is a 3-year Partial Upfront Reserved Instance
-   On-premises 3-year total cost: $167,422
-   AWS Cloud 3-year total cost: $7,509
-   Savings: 96% ($159,913)
-   On-premises solution incurs costs whether capacity is used
-   AWS solution commissioned when needed and decommissioned when resources no longer in use

Note: Chart comparing three-year total cost of ownership for on-premises and AWS available for accessibility. On-premises costs $167,422, while AWS costs $7,509.

![](https://i.imgur.com/IztaCYb.png)



### AWS Pricing Calculator

-   AWS provides the AWS Pricing Calculator to estimate monthly AWS bill
-   The tool can be used to model solutions and explore the cost of use cases on AWS
-   It allows to make informed decisions about using AWS by estimating costs and usage and pricing out new instances and services
-   Features of the AWS Pricing Calculator:
    -   Estimates monthly costs of AWS services
    -   Identifies opportunities for cost reduction
    -   Models solutions before building them
    -   Explores price points and calculations behind the estimate
    -   Finds available instance types and contract terms that meet your needs
-   Enables naming estimates and creating groups of services for organization
-   Allows for organization of groups and services based on cost-center, department, product architecture, etc.

![](https://i.imgur.com/kgAi0Jt.png)


### Additional benefit considerations

-   Hard benefits of adopting cloud technology:
    -   Reduced spending on compute, storage, networking, and security
    -   Reductions in hardware and software purchases
    -   Reduced operational costs, backup, and disaster recovery
    -   Reduction in operations personnel
-   Total Cost of Ownership (TCO) analysis compares the cost of running a solution in the cloud vs on-premises.
-   Return on Investment (ROI) analysis considers both hard and soft benefits, including direct and visible cost reductions and efficiency improvements.
-   Soft benefits of adopting cloud technology:
    -   Reusing services and applications
    -   Increased developer productivity
    -   Improved customer satisfaction
    -   Agile business processes
    -   Increased global reach

![](https://i.imgur.com/hAzvJty.png)



## Section 3: AWS Organizations
---

### Introduction to AWS Organizations

AWS Organizations:

-   A free account management service offered by AWS
-   Enables consolidation of multiple AWS accounts into one organization
-   Centrally managed by the user
-   Includes:
    -   Centrally managed access policies across multiple AWS accounts
    -   Controlled access to AWS services
    -   Automated AWS account creation and management
    -   Consolidated billing across multiple AWS accounts

### AWS Organizations terminology

![](https://i.imgur.com/iaRXHyc.png)


-   AWS Organizations is a service for account management and consolidation.
-   A basic organization consists of multiple accounts organized into OUs.
-   OUs are containers for accounts within a root and can also contain other OUs.
-   The structure creates a hierarchy resembling an upside-down tree with the root at the top and OUs and accounts branching and flowing downward.
-   Policies can be attached to OUs and accounts, with the policy affecting all branches and leaves if attached to a node in the hierarchy.
-   An OU can only have one parent, and each account can only be a member of one OU.
-   Accounts are standard AWS accounts that contain the AWS resources.
-   A policy can be attached to an account to apply controls to only that account.


### Key features and benefits

-   Ability to create service control policies (SCPs) to centrally control AWS services across multiple AWS accounts
-   Ability to create groups of accounts and attach policies to a group to ensure correct policies are applied
-   Simplification of account management using APIs to automate creation and management of new AWS accounts
-   Simplification of billing process with a single payment method for all AWS accounts in the organization
-   Consolidated billing provides central location to manage billing across all AWS accounts and the ability to benefit from volume discounts

![](https://i.imgur.com/FMxIuNp.png)



### Security with AWS Organizations

-   AWS Organizations does not replace the use of AWS Identity and Access Management (IAM) policies
-   IAM policies are used to allow or deny access to AWS services (such as Amazon S3), individual AWS resources (such as a specific S3 bucket), or individual API actions (such as s3:CreateBucket)
-   IAM policies can be applied only to IAM users, groups, or roles, and cannot restrict the AWS account root user
-   With Organizations, service control policies (SCPs) are used to allow or deny access to particular AWS services for individual AWS accounts or groups of accounts in an organizational unit
-   SCPs affect all IAM users, groups, and roles for an account, including the AWS account root user.

![](https://i.imgur.com/a7J9a48.png)


### Organizations setup

![](https://i.imgur.com/A7pqORK.png)


Summary of steps to set up AWS Organizations:
1.  Create your organization with your current AWS account as the primary account and invite one AWS account to join as a member account, and create another account as a member account.
2.  Create two organizational units in the organization and place the member accounts in the respective OUs.
3.  Create Service Control Policies (SCPs) to apply restrictions to the actions that can be delegated to users and roles in the member accounts.
4.  Test the policies by signing in as a user for each role or by using the IAM policy simulator.

### Limits of AWS Organizations

-   AWS Organizations has restrictions on names for accounts, OUs, roots, and policies:
    -   Names must be composed of Unicode characters
    -   Not exceed 250 characters in length
-   There are maximum and minimum values for AWS Organizations entities, including:
    -   Number of accounts (varies)
    -   Number of roots (1)
    -   Number of OUs (1,000)
    -   Number of policies (1,000)
    -   Maximum size of control policy document (5,120 bytes)
    -   Maximum nesting of BUs (5 levels of BUs under a root)
    -   Invitations sent per day (20)
    -   Member accounts created concurrently (5)
    -   Entities to which you can attach a policy (unlimited)

### Accessing AWS Organizations

-   AWS Organizations can be managed through the AWS Management Console, a browser-based interface.
-   AWS Command Line Interface (AWS CLI) tools enable the management of AWS Organizations and other AWS tasks.
-   AWS software development kits (SDKs) are available for various programming languages and platforms such as Java, Python, Ruby, .NET, iOS, and Android.
-   The AWS Organizations HTTPS Query API provides programmatic access to AWS Organizations and other AWS services.
-   When using the HTTPS API, you need to include code to digitally sign requests using your credentials.

## Section 4: AWS Billing and Cost Management
---

### Introducing AWS Billing and Cost Management

-   AWS Billing and Cost Management is the service used to pay the AWS bill, monitor usage, and budget costs.
-   It allows forecasting future costs and usage to plan ahead.
-   You can set a custom time period and choose to view data at monthly or daily granularity.
-   Filtering and grouping functionality is available for data analysis using various dimensions.
-   The AWS Cost and Usage Report Tool helps to identify optimization opportunities by understanding cost and usage data trends and usage of AWS implementation.

### AWS Billing Dashboard

-   AWS Billing and Cost Management is used to pay AWS bill and monitor usage and costs
-   Enables forecasting and better understanding of future costs and usage
-   Allows customization of time period and level of granularity (monthly or daily)
-   Filtering and grouping functionality available for further data analysis
-   AWS Cost and Usage Report Tool helps identify optimization opportunities
-   AWS Billing Dashboard displays month-to-date AWS expenditure status
-   Dashboard includes graphs: Spend Summary and Month-to-Date Spend by Service
-   Spend Summary shows last month's spending, estimated cost for the current month, and forecasted spending
-   Month-to-Date Spend by Service displays top services and cost attributed to each service.

![](https://i.imgur.com/U07xrLX.png)


### Tools in the billing dashboard

-   AWS Billing Dashboard: provides a high-level view of month-to-date AWS expenditure and allows you to identify the services that account for the majority of your costs.
-   Spend Summary: shows the amount spent last month, estimated costs of AWS usage for the month to date, and a forecast for the amount likely to be spent this month.
-   Month-to-Date Spend by Service: shows the top services used and the proportion of costs attributed to each service.
-   Cost Management Tools:
    -   AWS Bills
    -   AWS Cost Explorer
    -   AWS Budgets
    -   AWS Cost and Usage Reports.

### Monthly bills

- The **AWS Bills** page shows the costs you incurred for each AWS service over the past month, broken down by AWS Region and linked account. 
- This tool provides access to the latest information on costs and usage, including the monthly bill and a detailed breakdown of AWS services used.
![](https://i.imgur.com/dNAFWbv.png)


### Cost Explorer

-   AWS Billing and Cost Management is a service used to pay AWS bills, monitor usage, and budget costs.
-   The Billing Dashboard displays the current month-to-date AWS expenditure, top services, and cost trends.
-   Cost management tools: AWS Bills, AWS Cost Explorer, AWS Budgets, AWS Cost and Usage Reports.
-   AWS Bills lists the costs for each service, broken down by region and linked account.
-   Cost Explorer is a free tool for visualizing and managing AWS costs and usage over time, including a monthly running costs report, forecast for next 3 months, and data on the most used services.

![](https://i.imgur.com/LwMZSrq.png)


### Forecast and track costs

-   AWS Budgets is a tool that helps track and manage AWS costs using the cost visualization provided by Cost Explorer.
-   It allows you to create budgets at the monthly, quarterly, or yearly level and customize the start and end dates.
-   You can set up budget alerts to be sent via email or Amazon Simple Notification Service (Amazon SNS) when estimated costs exceed the budget.
-   The AWS Billing budgets panel shows budget names, current and future costs and usage, and headings for current and forecasted versus budgets.

![](https://i.imgur.com/dKQBnHi.png)


### Cost and usage reporting

-   The AWS Cost and Usage Report is a tool for accessing information about an AWS account's costs and usage.
-   The report provides information about the usage for each service category used by the account and its users in hourly or daily line items.
-   It also lists any tax activated for tax allocation purposes.
-   The reports can be published to an S3 bucket and updated once a day.

![](https://i.imgur.com/wDZvj27.png)



## Section 5: Technical support
---

### AWS support

-   AWS Support provides unique combination of tools and expertise based on current or planned use cases.
-   AWS Support aims to support all customers including those experimenting, looking for production uses, and using AWS as a critical resource.
-   Type of support provided varies depending on customer needs and goals.
-   AWS Support developed to provide complete support and resources to aid customer success.
-   AWS Support provides various tools and resources to support your success with AWS services and applications.
-   Support is available for customers at different stages of their AWS journey, from experimentation to business-critical use.
-   Technical Account Managers (TAMs) provide proactive guidance, architectural review, and continuous communication.
-   AWS Trusted Advisor is an online resource that checks for opportunities to reduce monthly costs and increase productivity.
-   Support Concierge is a billing and account expert who can quickly resolve non-technical billing and account-level inquiries.

![](https://i.imgur.com/vYImsam.png)

![](https://i.imgur.com/h8FQWFD.png)


### Support plans

AWS Support Plans:
-   Basic Support Plan:
    
    -   24/7 access to customer service, documentation, whitepapers and support forums
    -   Access to six core Trusted Advisor checks
    -   Access to Personal Health Dashboard
-   Developer Support Plan:
    
    -   For customers testing or doing early development on AWS or using AWS for non-production workloads
    -   Access to guidance and technical support
    -   Helps explore how to quickly put AWS to work
-   Business Support Plan:
    
    -   For customers running production workloads on AWS
    -   For customers with multiple services activated or who use key services extensively
    -   Depend on AWS for business solutions to be available, scalable, and secure
-   Enterprise Support Plan:
    
    -   For customers running business and mission-critical workloads on AWS
    -   Focus on proactive management to increase efficiency and availability
    -   Technical Account Manager (TAM) provides technical expertise and acts as primary point of contact
    -   Helps build and operate workloads following AWS best practices, supports launches and migrations.

![](https://i.imgur.com/xDxA2i5.png)


### Case severity and response times

Response Times Based on Case Severity:
-   Critical: Business at risk, critical functions unavailable.
-   Urgent: Business significantly impacted, important functions unavailable.
-   High: Important functions impaired or degraded.
-   Normal: Non-critical functions behaving abnormally or time-sensitive development question.
-   Low: General development question or feature request.