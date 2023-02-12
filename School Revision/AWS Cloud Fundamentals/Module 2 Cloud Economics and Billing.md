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

![[Pasted image 20230213050417.png]]

### 2. Pay less when you reserve

Reserved capacity for services like Amazon EC2 and Amazon RDS can save up to 75% compared to on-demand options. There are three types of reserved instances with different upfront payment options (All Upfront, Partial Upfront, and No Upfront) that offer different discounts. Choosing reserved capacity helps minimize risks, manage budgets, and meet long-term commitment policies.

Options:
- All Upfront reserved instance (AURI)
- Partial Upfront reserved instance (PURI)
- No Upfront reserved instance (NURI)

![[Pasted image 20230213051126.png]]

### 3. Pay less by using more

With AWS, you can save money through volume-based discounts as your usage grows. Services like Amazon S3 have tiered pricing, where you pay less per GB as you use more. Data transfer is always free and multiple storage services offer lower costs based on your needs. As your organization evolves, AWS offers services to address your business needs and help you optimize savings by choosing the right combination of storage solutions that balance cost, performance, security, and durability.

![[Pasted image 20230213051419.png]]

### 4. Pay even less as AWS grows

AWS is committed to reducing costs in data centers by optimizing hardware, operations, power consumption, and general expenses. These cost-saving measures and the large scale economies of AWS result in lower pricing for customers. AWS has lowered pricing 75 times since 2006 and as the company grows, customers can also enjoy upgrades to higher-performing resources at no additional cost.

![[Pasted image 20230213051515.png]]

### Custom pricing:

AWS realizes that every customer has different needs. If none of the AWS pricing models work for your project, custom pricing is available for high-volume projects with unique requirements.

### AWS Free Tier:

AWS offers a free usage tier, the AWS Free Tier, for new customers for up to one year. The free tier applies to certain services and options, including a free Amazon EC2 T2 micro instance and free usage of Amazon S3, Amazon EBS, Elastic Load Balancing, data transfer, and other AWS services. This is a helpful resource for new AWS customers to get started in the cloud.

![[Pasted image 20230213051647.png]]

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

![[Pasted image 20230213051740.png]]


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

![[Pasted image 20230213052304.png]]

### What is Total Cost of Ownership (TCO)?    

-   To identify the best option between on-premises and cloud solutions, you can compare Total Cost of Ownership (TCO)
-   TCO is a financial estimate that considers direct and indirect costs of a product or system
-   TCO includes the cost of the service plus all costs associated with owning the service
-   Compare costs of running entire infrastructure environment for a specific workload in an on-premises vs. cloud-based infrastructure
-   Comparison is done for budgeting purposes or to build a business case for deployment solution decisions

![[Pasted image 20230213052449.png]]

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

![[Pasted image 20230213052549.png]]


