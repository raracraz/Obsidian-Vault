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

## Section 2: AWS Identity and Access Management (IAM)
---
### AWS Identity and Access Management (IAM)

-   AWS Identity and Access Management (IAM) allows for control of access to AWS Cloud services such as compute, storage, database, and application services.
-   IAM is used for authentication and authorization policies, specifying which users can access which services.
-   IAM provides central management of access to resources in the AWS account, with granular control over access to resources including API call authorization.
-   IAM enables control over which resources can be accessed by whom, and how they can be accessed, with different permissions granted to different users for different resources.
-   IAM is a feature of the AWS account, available at no additional charge.

### IAM: Essential components

-   An IAM user is a person or application defined in an AWS account with a unique name and security credentials
-   An IAM group is a collection of IAM users for simplified permissions management
-   An IAM policy is a document defining permissions for users in an AWS account, including access to specific resources and actions the user can perform on them
-   An IAM role is a tool for granting temporary access to specific AWS resources in an AWS account.

![](https://i.imgur.com/dKL6kis.png)

### Authenticate as an IAM user to gain access

-   Authentication is the process of proving one's identity.
-   An IAM user is defined in an AWS account to access AWS resources and must have a unique name and security credentials.
-   IAM users can have programmatic access or AWS Management Console access or both.
-   Programmatic access requires an access key ID and secret access key for API calls using the AWS CLI, SDK, or other development tools.
-   Console access requires the 12-digit account ID or account alias, IAM username, password, and an authentication code if MFA is enabled.

![](https://i.imgur.com/6icLo4r.png)

### IAM MFA

-   AWS services and resources can be accessed using AWS Management Console, AWS CLI, SDKs, and APIs.
-   For increased security, Multi-Factor Authentication (MFA) can be enabled.
-   MFA requires users and systems to provide an MFA token along with regular sign-in credentials.
-   Options for generating MFA authentication tokens include virtual MFA applications, U2F security keys, and hardware MFA devices.

![](https://i.imgur.com/il6MTck.png)

### Authorization: What actions are permitted

-   Authorization determines what permissions a user, service, or application should be granted.
-   After authentication, users must be authorized to access AWS services.
-   IAM users do not have permissions to access resources or data by default.
-   Permissions are explicitly granted to users, groups, or roles by creating policies.
-   Policies are documents in JSON format that list permissions to allow or deny access to resources in the AWS account.

![](https://i.imgur.com/0YORRvK.png)

### IAM: Authorization

-   To assign permissions to a user, group, or role, you must create an IAM policy or find an existing policy in the account.
-   There are no default permissions in AWS; all actions are denied by default unless explicitly allowed.
-   The principle of least privilege is an important concept in computer security that promotes granting minimal user privileges needed to the user based on their needs.
-   It is a best practice to follow the principle of least privilege when creating IAM policies. Determine what users need to be able to do and grant them only those permissions.
-   Start with a minimum set of permissions and grant additional permissions as necessary, instead of starting with broad permissions and trying to lock them down later.
-   The scope of IAM service configurations is global, and the settings apply across all AWS regions.

![](https://i.imgur.com/ravy18U.png)


### IAM policies

-   An IAM policy is a formal statement of permissions granted to an entity, which can be attached to any IAM entity such as users, groups, roles, or resources.
-   Policies specify which actions are allowed, on which resources, and what the effect will be when the user requests access to the resources.
-   The order of policy evaluation has no effect on the outcome of the evaluation, and the most restrictive policy applies when there is a conflict.
-   There are two types of IAM policies: Identity-based policies and Resource-based policies.
-   Identity-based policies are permissions policies that control what actions an identity (such as a user, role, or group) can perform, on which resources, and under what conditions. They can be managed policies or inline policies.
-   Resource-based policies are JSON policy documents that are attached to a resource (such as an S3 bucket) and control what actions a specified principal can perform on that resource and under what conditions.

![](https://i.imgur.com/IWuY1h9.png)

### Resource-based policies

-   Identity-based policies are attached to users, groups, or roles, while resource-based policies are attached to resources such as S3 buckets
-   Resource-based policies specify who can access a resource and what actions they can perform on it, and are defined inline only
-   An example of a resource-based policy is an S3 bucket policy, which can be defined by navigating to the bucket, clicking the Permission tab, and defining the JSON-formatted policy document
-   Amazon S3 access control lists (ACLs) are another example of a resource-based policy
-   Resource-based policies can be used to grant access to specific IAM users, even if they are restricted in an identity-based policy
-   An explicit deny statement in a resource-based policy will always take precedence over any allow statement

![](https://i.imgur.com/4MYgyN7.png)

### IAM permissions

-   IAM policies let you specify permissions for IAM users, groups, and roles.
-   IAM first checks for any explicit denial policies before checking for explicit allow policies.
-   If neither an explicit deny nor an explicit allow policy exists, IAM denies access by default.
-   This process is referred to as an implicit deny.
-   IAM grants permission only if the requested action is explicitly allowed and not explicitly denied.

![](https://i.imgur.com/yMmIHxf.png)

### IAM groups

-   IAM groups are collections of IAM users that offer a convenient way to manage permissions for a group of users.
-   You can create an IAM group and attach IAM policies to it, granting AWS resource access permissions that developers typically need.
-   Users added to the group will automatically have the permissions assigned to the group, and removing the user from the group will revoke the permissions.
-   Important characteristics of IAM groups include:
    -   A group can contain many users and a user can belong to multiple groups.
    -   Groups cannot be nested and can only contain users.
    -   There is no default group that includes all users in the AWS account; you need to create the group and add each user to it.

![](https://i.imgur.com/gJmBG8X.png)

### IAM roles

-   An IAM role is an AWS identity with specific permissions that can be assumed by anyone who needs it.
-   A role is similar to a user in that permissions policies can be attached to it, but it does not have long-term credentials like a password or access keys.
-   When a role is assumed, temporary security credentials are provided for the session.
-   Roles can be used to delegate access to users, applications, or services that do not normally have access to AWS resources.
-   Examples of use cases for roles include granting users access to resources they don't usually have, granting access across AWS accounts, allowing mobile apps to use AWS resources without embedding AWS keys, granting access to users with identities defined outside of AWS, and granting access to third parties for auditing resources.

![](https://i.imgur.com/0eU3hen.png)

### Example use of an IAM role

-   An IAM role is created with a permissions policy and a trust policy.
-   The permissions policy grants read-only access to an S3 bucket named photos.
-   The role is attached to an EC2 instance.
-   The trust policy allows the EC2 instance to assume the role and retrieve temporary credentials.
-   The application running on the instance uses the role's temporary credentials to access the photos bucket.
-   The application developer does not need to manage or share any credentials, and the administrator does not need to grant the developer permission to access the photos bucket.

![](https://i.imgur.com/PgU8LZN.png)

### Key Takeaways

Some keytakeaways from this section of the module include:
- IAM policies are constructed with JavaScript Object Notation (JSON) and define permissions.
- IAM policies can be attached to any IAM entity.
- Entities are IAM users, IAM groups, and IAM roles.
- An IAM user provides a way for a person, application, or service to authenticate to AWS.
- An IAM group is a simple way to attach the same policies to multiple users.
- An IAM role can have permissions policies attached to it,and can be used to delegate temporary access to users or applications.

## Section 3: Securing a new AWS account
---

### AWS account root user access versus IAM access

-   AWS account root user is created when you first create an AWS account and has complete access to all AWS services and resources in the account
-   AWS recommends not to use the root user credentials for day-to-day interactions with the account
-   IAM should be used to create additional users and assign permissions to them, following the principle of least privilege
-   Administrator-level permissions can be granted to an IAM user, which can be used to interact with the account
-   IAM allows unique credentials for each user, and you can define which user will have access to which resources
-   You should avoid sharing the same credentials with multiple users

![](https://i.imgur.com/0SsqsE7.png)

### Securing a new AWS account: Account root user

-   To stop using the account root user, create an IAM user for yourself with AWS Management Console access enabled (but no permissions yet)
-   Create an IAM group with a name and attach IAM policies to the group that grant full access to at least a few of the services you will use.
-   Add the IAM user to the group.
-   Disable and remove your account root user access keys if they exist.
-   Enable a password policy for all users.
-   Copy the IAM user's sign-in link from the IAM Dashboard page.
-   Sign out as the account root user.
-   Browse to the IAM user's sign-in link and sign in using your new IAM user credentials.
-   Store your account root user credentials in a secure place.

![](https://i.imgur.com/9knmgzL.png)

### Securing a new AWS account: MFA

-   It's recommended to require multi-factor authentication (MFA) for both the account root user login and all other IAM user logins in a new AWS account.
-   MFA can also be used to control programmatic access.
-   There are various options for retrieving the MFA token, such as virtual MFA-compliant applications like Google Authenticator and Authy Authenticator, U2F security key devices, and hardware MFA options that provide a key fob or display card.

![](https://i.imgur.com/ZDDkkKP.png)

### Securing a new AWS account: AWS CloudTrail

-   AWS CloudTrail logs all API requests to resources in an account, enabling operational auditing.
-   It is enabled by default on all AWS accounts and keeps a record of the last 90 days of account management event activity.
-   You can view and download the last 90 days of account activity without needing to create another trail.
-   CloudTrail supports a variety of AWS services, and you can view the list of supported services in the documentation.
-   To retain logs beyond the last 90 days and enable alerting for specified events, you can create a new trail.

![](https://i.imgur.com/XTiTFz6.png)

### Securing a new AWS account: Billing reports

-   Enabling billing reports is a recommended step for securing a new AWS account.
-   AWS provides billing reports like the AWS Cost and Usage Report that show information about your use of AWS resources and estimated costs.
-   Reports are delivered to an Amazon S3 bucket specified by you and are updated at least once per day.
-   The AWS Cost and Usage Report tracks usage in the account and provides estimated charges, either by the hour or by the day.

![](https://i.imgur.com/a65pAG1.png)

### Key Takeaways

The key takeaways from this section of the module are all related to best practices for securing an AWS account. Those best practice recommendations include:
- Secure logins with multi-factor authentication (MFA).
- Delete account root user access keys.
- Create individual IAM users and grant permissions according to the principle of least privilege.
- Use groups to assign permissions to IAM users.
- Configure a strong password policy.
- Delegate using roles instead of sharing credentials.
- Monitor account activity using AWS CloudTrail

## Section 4: Securing accounts
---

### AWS Organizations

-   AWS Organizations is an account management service that allows you to consolidate multiple AWS accounts into an organization that you create and centrally manage.
-   AWS Organizations allows you to group accounts into organizational units (OUs) and attach different access policies to each OU.
-   You can define policies that block OU access to services that do not meet certain requirements, and then attach the policy to the OU.
-   AWS Organizations integrates with and supports IAM, giving you control over what users and roles in an account or a group of accounts can do.
-   AWS Organizations provides service control policies (SCPs) that enable you to specify the maximum permissions that member accounts in the organization can have, even overriding the administrators of member accounts.

![](https://i.imgur.com/e43mw2A.png)

### AWS Organizations: Service control policies

-   SCPs (Service Control Policies) in AWS Organizations offer centralized control over maximum available permissions for all accounts in an organization
-   SCPs are available only in organizations with all features enabled, including consolidated billing
-   SCPs are similar to IAM permissions policies and use almost the same syntax
-   An SCP specifies the maximum permissions for an organization or OU, but does not grant permissions
-   Attaching an SCP to the organization root or an OU defines a safeguard for the actions that accounts in the organization root or OU can do
-   SCPs are not a substitute for well-managed IAM configurations within each account
-   You must still attach IAM policies to users and roles in your organization's accounts to actually grant permissions to them.

![](https://i.imgur.com/BfhDT00.png)

### AWS Key Management Service (AWS KMS)

-   AWS KMS is a service for creating and managing encryption keys.
-   AWS KMS uses hardware security modules (HSMs) validated under FIPS 140-2 to protect your keys.
-   AWS KMS integrates with AWS CloudTrail to provide logs of all key usage.
-   Customer master keys (CMKs) control access to data encryption keys used to encrypt and decrypt your data.
-   You can create, manage, and import keys from your own key management infrastructure into AWS KMS.
-   AWS KMS integrates with most AWS services to control data encryption.

![](https://i.imgur.com/nGjvXv7.png)

### Amazon Cognito

-   Amazon Cognito provides access control solutions for AWS resources in applications
-   Users can be assigned different roles to control access to authorized resources
-   Amazon Cognito uses identity management standards like SAML 2.0 for authentication
-   SAML enables single sign-on to multiple SAML-enabled applications with a single set of credentials
-   Amazon Cognito helps meet security and compliance requirements for highly regulated organizations like healthcare companies and merchants.

![](https://i.imgur.com/D5IxPyh.png)

### AWS Shield

-   AWS Shield is a managed DDoS protection service for applications running on AWS.
-   It provides always-on detection and automatic inline mitigations for all types of DDoS attacks, including infrastructure layer attacks, state exhaustion attacks, and application-layer attacks.
-   AWS Shield Standard is free and automatically enabled for all AWS customers.
-   AWS Shield Advanced is a paid service that provides additional protections against larger and more sophisticated attacks for applications running on EC2, Elastic Load Balancing, CloudFront, Global Accelerator, and Route 53.
-   AWS Shield Advanced customers can contact the DDoS Response Team for support, but they need to have either Enterprise Support or Business Support from AWS Support.

![](https://i.imgur.com/cehsNPL.png)

## Section 5: Securing data on AWS
---

### Encryption of data at rest

-   Data encryption is essential to protect digital data.
-   Data encryption encodes data and makes it unreadable to anyone who does not have access to the secret key.
-   Data at rest is data that is physically stored on disk or on tape.
-   Encrypted file systems can be created on AWS using AES-256 encryption algorithm to encrypt all data and metadata at rest.
-   AWS KMS handles encryption and decryption automatically and transparently without modifying your applications.
-   AWS recommends enabling encryption on all services that store your data to comply with corporate or regulatory policies.
-   Data stored in any service supported by AWS KMS can be encrypted.

![](https://i.imgur.com/lRrGIGH.png)

### Encryption of data in transit

-   Data in transit is data that is moving across the network.
-   Encryption of data in transit is accomplished by using Transport Layer Security (TLS) 1.2 with an open standard AES-256 cipher.
-   AWS Certificate Manager is a service that enables you to provision, manage, and deploy SSL or TLS certificates for use with AWS services and your internal connected resources.
-   With AWS Certificate Manager, you can request a certificate and then deploy it on AWS resources, such as load balancers or CloudFront distributions.
-   HTTPS traffic is protected against eavesdropping and man-in-the-middle attacks because of the bidirectional encryption of the communication.
-   AWS services support encryption for data in transit, with TLS or SSL used to encrypt traffic between services.

![](https://i.imgur.com/0ABkvAf.png)

### Securing Amazon S3 buckets and objects

-   All Amazon S3 buckets are private by default and require explicit access grant.
-   It's important to manage and control access to Amazon S3 data.
-   Tools and options are available to control access, including:
    -   Using Amazon S3 Block Public Access to avoid unintended exposure of data
    -   Writing IAM policies to specify users or roles that can access specific buckets and objects
    -   Writing bucket policies to define access to specific buckets or objects for users or systems that can't authenticate with IAM
    -   Setting access control lists (ACLs) on buckets and objects (but use with caution)
    -   AWS Trusted Advisor provides a bucket permission check feature to discover global access permissions in your account.
-   Bucket policies can be used to grant access across AWS accounts or to grant public or anonymous access to Amazon S3 data, but should be written carefully and tested fully.
-   Deny statements can be used in bucket policies to restrict access even if users have permissions granted in an identity-based policy.

![](https://i.imgur.com/hL50RJH.png)

## Section 6: Working to ensure compliance
---

### AWS compliance programs

-   AWS engages with external certifying bodies and independent auditors to provide customers with information about AWS policies, processes, and controls.
-   One example of a certification for which you can use AWS services to meet your compliance goals is the ISO/IEC 27001:2013 certification, which specifies the requirements for establishing, implementing, maintaining, and continually improving an Information Security Management System.
-   AWS provides security features and legal agreements that are designed to help support customers with common regulations and laws, such as the Health Insurance Portability and Accountability Act (HIPAA) regulation and the European Union (EU) General Data Protection Regulation (GDPR).
-   HIPAA regulates the protection of sensitive patient data in the US, while GDPR protects EU data subjects' fundamental right to privacy and the protection of personal data.
-   AWS perpetually manages security in a holistic, comprehensive manner through the development and implementation of an Information Security Management System.

![](https://i.imgur.com/f2eibqV.png)

### AWS Config

-   AWS Config is a service that assesses, audits, and evaluates the configurations of AWS resources.
-   AWS Config continuously monitors and records AWS resource configurations and enables the automation of evaluating recorded configurations against desired configurations.
-   AWS Config enables reviewing changes in configurations and relationships between AWS resources, reviewing detailed resource configuration histories, and determining overall compliance against configurations specified in internal guidelines.
-   AWS Config simplifies compliance auditing, security analysis, change management, and operational troubleshooting.
-   AWS Config keeps an inventory listing of all resources in the account and checks for configuration rule compliance and resource compliance.
-   Noncompliant resources are flagged, alerting users to configuration issues.
-   AWS Config is a Regional service, so it needs to be enabled in every Region used.
-   AWS Config offers an aggregator feature that shows an aggregated view of resources across multiple Regions and accounts.

![](https://i.imgur.com/6iKh5ee.png)

### AWS Artifact

-   AWS Artifact provides on-demand downloads of AWS security and compliance documents
-   These documents can be used to demonstrate the security and compliance of AWS infrastructure and services used
-   Documents available include AWS ISO certifications, PCI, and SOC reports
-   Customers are responsible for obtaining documents to demonstrate the security and compliance of their own companies
-   AWS Artifact can also be used to review, accept, and track the status of AWS agreements such as the Business Associate Agreement (BAA)
-   BAA is required for companies subject to HIPAA to ensure protected health information (PHI) is appropriately safeguarded
-   AWS Artifact can be used to accept agreements on behalf of multiple accounts
-   AWS Organizations can be used to create an organization to accept agreements for multiple accounts.

![](https://i.imgur.com/r0yYtAr.png)

### Key Takeaway

Some keytakeaways from this section of the module include:
- AWS security compliance programs provide information about the policies, processes, and controls that are established and operated by AWS.
- AWS Config is used to assess, audit, and evaluate the configurations of AWS resources.
- AWS Artifact provides access to security and compliance reports.




