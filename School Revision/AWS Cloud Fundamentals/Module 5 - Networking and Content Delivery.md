# Module 5: Networking and Content Delivery

## Module overview
---
- Networking basics
- Amazon VPC
- VPC networking
- VPC security
- Amazon Route 53 
- Amazon CloudFront

## Module objectives
---
After completing this module, you should be able to:
- Recognize the basics of networking
- Describe virtual networking in the cloud with Amazon VPC
- Label a network diagram
- Design a basic VPC architecture
- Indicate the steps to build a VPC
- Identify security groups
- Create your own VPC and add additional components to it to produce a customized network
- Identify the fundamentals of Amazon Route 53
- Recognize the benefits of Amazon CloudFront

## Section 1: Networking basics
---

### Networks

-   A computer network consists of two or more client machines that are connected to each other to share resources.
-   A network can be divided into subnets for better management and security.
-   Networking requires a networking device, such as a router or switch, to connect all the clients together and enable communication between them.

## IP addresses

-   Each client machine in a network has a unique IP address.
-   An IP address is a numerical label in decimal format.
-   Machines convert the decimal number to binary format.
-   An IP address is made up of four dot-separated numbers in octal number format.
-   Each number can be anything from 0 to 255, representing 8 bits.
-   The combined total of the four numbers for an IP address is 32 bits in binary format.

### IPv4 and IPv6 addresses

-   IPv4 addresses are 32-bit
-   IPv6 addresses are 128 bits
-   IPv6 addresses are composed of eight groups of four letters and numbers separated by colons
-   Each group of an IPv6 address represents 16 bits in hexadecimal format
-   Combined total of the eight groups in an IPv6 address is 128 bits in binary format.

### Classless Inter-Domain Routing (CIDR)

-   Classless Inter-Domain Routing (CIDR) is a common method to describe networks
-   CIDR is expressed as an IP address, followed by a slash character (/), and a number indicating how many bits of the routing prefix must be fixed for the network identifier
-   The bits that are not fixed are allowed to change and CIDR expresses a group of consecutive IP addresses
-   The CIDR address 192.0.2.0/24 means that the first 24 bits must be fixed and the last 8 bits are flexible, which allows for 256 IP addresses ranging from 192.0.2.0 to 192.0.2.255
-   The CIDR address 192.0.2.0/16 means that the first 16 bits must be fixed and the last 16 bits are flexible, which allows for 65,536 IP addresses ranging from 192.0.0.0 to 192.0.255.255
-   Fixed IP addresses have every bit fixed, representing a single IP address (e.g., 192.0.2.0/32) and are helpful for setting up firewall rules
-   The internet is represented as 0.0.0.0/0, where every bit is flexible

![](https://i.imgur.com/HRRPbZD.png)


### Open Systems Interconnection (OSI) model

-   The Open Systems Interconnection (OSI) model is a conceptual model used to explain how data travels over a network.
-   It consists of seven layers, each with its own set of protocols and addresses used to send data.
-   The OSI model can be used to understand how communication takes place in a virtual private cloud (VPC).
-   Hubs and switches work at layer 2 (the data link layer).
-   Routers work at layer 3 (the network layer).

![](https://i.imgur.com/sJM1a3z.png)

## Section 2: Amazon VPC
---

### Amazon VPC

-   Amazon Virtual Private Cloud (Amazon VPC) is a service on AWS that allows you to create a logically isolated section of the cloud.
-   With Amazon VPC, you can launch AWS resources and control virtual networking resources.
-   You can customize the network configuration of your VPC, including the selection of your own IP address range and the creation of subnets.
-   Both IPv4 and IPv6 can be used for secure access to resources and applications in your VPC.
-   You can create a public subnet for web servers and a private subnet for backend systems, with no public internet access.
-   Security groups and network access control lists (networkACLs) can be used to control access to Amazon EC2 instances in each subnet.

![](https://i.imgur.com/l8eyqL1.png)

### VPCs and subnets

-   Amazon VPC allows you to provision virtual private clouds (VPCs) that are logically isolated from other virtual networks in the AWS Cloud.
-   A VPC is dedicated to your account and belongs to a single AWS Region but can span multiple Availability Zones.
-   A VPC can be divided into one or more subnets, which are a range of IP addresses in a VPC.
-   Subnets belong to a single Availability Zone, and you can create subnets in different Availability Zones for high availability.
-   Subnets can be classified as public or private, with public subnets having direct access to the internet and private subnets not having such access.

![](https://i.imgur.com/kaQ3sOr.png)

### IP addressing

-   IP addresses enable communication between resources in a VPC and over the internet
-   When creating a VPC, you assign an IPv4 CIDR block to it, which cannot be changed later
-   The IPv4 CIDR block can be as large as /16 or as small as /28
-   You can also associate an IPv6 CIDR block with your VPC and subnets
-   The CIDR block of a subnet can be the same as the VPC or a subset of the VPC
-   Creating multiple subnets in a VPC is possible but their CIDR blocks cannot overlap
-   Duplicate IP addresses cannot exist in the same VPC.

![](https://i.imgur.com/4AuaqIW.png)

### Reserved IP addresses

-   Each subnet requires its own CIDR block
-   AWS reserves five IP addresses within each CIDR block
-   These reserved addresses are used for network, router, DNS, future, and broadcast purposes
-   For example, a subnet with an IPv4 CIDR block of 10.0.0.0/24 has 256 total IP addresses, but only 251 are available due to the five reserved addresses.

![](https://i.imgur.com/shuor8c.png)

### Public IP address types

-   Instances in a VPC get a private IP address automatically, but you can also request a public IP address when you create the instance by modifying the subnet's auto-assign public IP address properties.
-   Elastic IP addresses are static and public IPv4 addresses that can be associated with any instance or network interface for any VPC in your account.
-   With an Elastic IP address, you can mask the failure of an instance by rapidly remapping the address to another instance in your VPC.
-   Associating the Elastic IP address with the network interface has an advantage over associating it directly with the instance because you can move all of the attributes of the network interface from one instance to another in a single step.
-   Additional costs might apply when you use Elastic IP addresses, so it is important to release them when you no longer need them.

![](https://i.imgur.com/SsDsUAp.png)

### Elastic network interface

-   An elastic network interface is a virtual network interface that can be attached or detached from an instance in a VPC.
-   The attributes of a network interface follow it when it is reattached to another instance, and network traffic is redirected to the new instance.
-   Each instance in a VPC has a default network interface that is assigned a private IPv4 address from the VPC's IPv4 address range.
-   The primary network interface, which is the default network interface, cannot be detached from an instance.
-   Additional network interfaces can be created and attached to any instance in the VPC.
-   The number of network interfaces that can be attached varies by instance type.

![](https://i.imgur.com/cF0xV5N.png)

### Route tables and routes

-   A route table directs network traffic from a subnet.
-   Each route specifies a destination and a target.
-   The destination is the CIDR block where traffic is sent.
-   The target is the target that the traffic is sent through.
-   Every route table has a default local route for internal communications.
-   Route tables can be customized by adding routes.
-   Each subnet must be associated with a route table.
-   The main route table is automatically assigned to the VPC.
-   A subnet can only be associated with one route table at a time.
-   Multiple subnets can be associated with the same route table.

![](https://i.imgur.com/WfzLkUQ.png)

### Key takeaways

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
---

### Internet gateway

-   An internet gateway is a VPC component that enables communication between instances in a VPC and the internet.
-   It serves two purposes: providing a target in VPC route tables for internet-routable traffic, and performing network address translation for instances with public IPv4 addresses.
-   To make a subnet public, you attach an internet gateway to your VPC and add a route to the route table to send non-local traffic through the internet gateway to the internet (0.0.0.0/0).

![](https://i.imgur.com/1BeGRB9.png)

### Network address translation (NAT) gateway

-   A NAT gateway allows instances in a private subnet to connect to the internet or other AWS services, while blocking incoming connections.
-   To create a NAT gateway, you need to specify the public subnet and an Elastic IP address to associate with it.
-   After creating a NAT gateway, you need to update the route table associated with the private subnets to point internet-bound traffic to the NAT gateway.
-   You can use a NAT instance instead of a NAT gateway, but a NAT gateway is a managed NAT service that provides better availability, higher bandwidth, and requires less administrative effort.
-   AWS recommends using a NAT gateway instead of a NAT instance for common use cases.

![](https://i.imgur.com/hlXzxxV.png)

### VPC sharing

-   VPC sharing enables multiple AWS accounts to create and manage their resources into shared VPCs.
-   It allows the owner of the VPC to share one or more subnets with other accounts that belong to the same organization in AWS Organizations.
-   Participants can view, create, modify, and delete their application resources in the shared subnets but cannot access other participant's resources or the VPC owner's resources.
-   VPC sharing offers benefits such as separation of duties, ownership of resources, referencing each other's security groups, higher density in subnets, avoidance of hard limits, optimized costs through reuse of NAT gateways, VPC interface endpoints, and intra-Availability Zone traffic.
-   VPC sharing enables decoupling of accounts and networks, resulting in fewer, larger, and centrally managed VPCs, which can lead to optimized costs and efficient use of resources.

![](https://i.imgur.com/Vnv8Tro.png)

### VPC peering

-   A VPC peering connection allows routing of traffic between two VPCs privately.
-   Instances in either VPC can communicate with each other as if they are within the same network.
-   VPC peering connection can be set up between your own VPCs, with a VPC in another AWS account, or with a VPC in a different AWS Region.
-   Route table rules are created to allow the VPCs to communicate with each other through the peering resource.
-   VPC peering has restrictions: IP address ranges cannot overlap, transitive peering is not supported, and only one peering resource is allowed between the same two VPCs.

![](https://i.imgur.com/Mj2HxBw.png)

### AWS Site-to-Site VPN

-   AWS Virtual Private Cloud (VPC) is a service that allows you to create a logically isolated section of the AWS Cloud where you can launch AWS resources.
-   VPC allows you to define a virtual network topology, including subnets and routing tables.
-   An internet gateway is a VPC component that enables communication between instances in your VPC and the internet.
-   A NAT gateway enables instances in a private subnet to connect to the internet or other AWS services, but prevents the internet from initiating a connection with those instances.
-   VPC sharing allows you to share subnets with other AWS accounts in the same organization in AWS Organizations, enabling multiple AWS accounts to create their application resources into shared, centrally managed VPCs.
-   A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them privately, allowing instances in either VPC to communicate with each other as if they are within the same network.
-   To connect your VPC to your remote network, you must create a new VPN gateway, define the configuration of the VPN device or customer gateway, create a custom route table, establish an AWS Site-to-Site VPN connection, and configure routing to pass traffic through the connection.

![](https://i.imgur.com/uAVpPmL.png)

### AWS Direct Connect

-   AWS Direct Connect (DX) is a service that enables a dedicated, private network connection between a user's network and an AWS Direct Connect location.
-   This private connection can help reduce network costs, increase bandwidth throughput, and provide a more consistent network experience than internet-based connections.
-   DX uses the open standard 802.1q virtual local area networks (VLANs).

![](https://i.imgur.com/ZgWxBnx.png)

### VPC endpoints

-   VPC endpoint is a virtual device for private connection between VPC and supported AWS services or VPC endpoint services using AWS PrivateLink
-   VPC endpoint connection doesn't require internet gateway, NAT device, VPN or AWS Direct Connect
-   There are two types of VPC endpoints: interface and gateway endpoints
-   Interface VPC endpoint enables connection to AWS services, endpoint services hosted by other AWS customers or AWS Partner Network Partners in their own VPCs, and supported AWS Marketplace APN Partner services. It incurs hourly usage rates and data processing rates
-   Gateway endpoint is free to use, but standard charges for data transfer and resource usage still apply.

![](https://i.imgur.com/1eBfxKB.png)

### AWS Transit Gateway

-   AWS offers various connectivity options and gateways to connect VPCs to each other and to on-premises networks.
-   As the number of VPCs and workloads grows, managing point-to-point connectivity can become operationally costly and difficult.
-   AWS Transit Gateway simplifies the networking model by acting as a hub that connects all the VPCs and on-premises networks, and controls how traffic is routed among them.
-   With AWS Transit Gateway, you only need to create and manage a single connection from the central gateway into each VPC, on-premises data center, or remote office.
-   The hub-and-spoke model of AWS Transit Gateway significantly simplifies management and reduces operational costs.
-   Any new VPC is automatically connected to the transit gateway and becomes available to every other network that is connected to the transit gateway.
-   AWS Transit Gateway makes it easier to scale your network as you grow.

![](https://i.imgur.com/nZRkTjb.png)

### Key Takeaways

Some key takeaways from this section of the module include:
- There are several VPC networking options, which include:
	- Internet gateway: Connects your VPC to the internet
	- NAT gateway: Enables instances in a private subnet to connect to the internet
	- VPC endpoint: Connects your VPC to supported AWS services
	- VPC peering: Connects your VPC to other VPCs
	- VPC sharing: Allows multiple AWS accounts to create their application resources into shared, centrally-managed Amazon VPCs•AWS Site-to-Site VPN: Connects your VPC to remote networks
	- AWS Direct Connect: Connects your VPC to a remote network by using a dedicated network connection
	- AWS Transit Gateway: A hub-and-spoke connection alternative to VPC peering
- You can use the VPC Wizard to implement your design.

## Section 4: VPC security
---
### Security groups

-   Security groups act as a virtual firewall for instances and control inbound and outbound traffic
-   Security groups are applied at the instance level, not the subnet level, so different instances in the same subnet can have different security groups
-   Security groups have rules for inbound and outbound traffic, but no inbound rules are created by default
-   By default, security groups allow all outbound traffic, but you can add specific outbound rules
-   If a security group has no outbound rules, no outbound traffic from an instance is allowed
-   Security groups are stateful, so allowed inbound traffic is automatically allowed to flow out, regardless of outbound rules

![](https://i.imgur.com/8UOytMJ.png)
![](https://i.imgur.com/5fyG8GX.png)

### Custom security group examples

-   Custom security groups can be created in AWS to filter inbound and outbound traffic for instances.
-   Allow rules can be specified in custom security groups, but deny rules cannot.
-   All rules in a security group are evaluated before a decision is made to allow traffic.
-   Security groups are stateful and retain state information even after a request is processed.

### Network access control lists

-   A network ACL is an optional layer of security for your Amazon VPC.
-   It acts as a firewall for controlling traffic in and out of one or more subnets.
-   Network ACLs have separate inbound and outbound rules, and each rule can either allow or deny traffic.
-   Each subnet in your VPC must be associated with a network ACL.
-   Your VPC comes with a default network ACL that allows all inbound and outbound IPv4 traffic.
-   Network ACLs are stateless, which means that no information about a request is maintained after a request is processed. 

![](https://i.imgur.com/KN4QGQ8.png)
![](https://i.imgur.com/58bZY9I.png)

### Custom network ACLs examples

-   You can create a custom network ACL and associate it with a subnet for an additional layer of security for your VPC.
-   By default, a custom network ACL denies all inbound and outbound traffic until you add rules to it.
-   A network ACL has separate inbound and outbound rules, and each rule can either allow or deny traffic.
-   Rules are evaluated in order, starting with the lowest numbered rule, to determine whether traffic is allowed in or out of any subnet associated with the network ACL.
-   The highest number you can use for a rule is 32,766, and AWS recommends creating rules in increments for easier future editing.

![](https://i.imgur.com/1gumLyg.png)

### Security groups versus network ACLs

Here is a summary of the differences between security groups and network ACLs:
- Security groupsact at the instance level, but network ACLs act at the subnet level.
- Security groups support allow rules only, but network ACLs support both allow and deny rules.
- Security groups are stateful, but network ACLs are stateless.
- For security groups, all rules are evaluated before the decision is made to allow traffic. For network ACLs, rules are evaluated in number order before the decision is made to allow traffic.

### Key Takeaway

The keytakeaways from this section of the module are:
- Build security into your VPC architecture.
- Security groups and network ACLs are firewall options that you can use to secure your VPC

## Section 5: Amazon Route 53
---

### Amazon Route 53

-   Amazon Route 53 is a cloud Domain Name System (DNS) web service designed to translate domain names into numeric IP addresses.
-   It is highly available, scalable, reliable, and cost-effective.
-   Route 53 can connect user requests to infrastructure running in AWS or outside of AWS.
-   It can be used to route traffic to healthy endpoints and monitor the health of an application and its endpoints.
-   Route 53 traffic flow can help manage traffic globally through several routing types and can be combined with DNS failover to enable low-latency, fault-tolerant architectures.
-   Domain Name Registration is also offered by Amazon Route 53.

![](https://i.imgur.com/kPup1rt.png)

### Amazon Route 53 supported routing

-   Amazon Route 53 offers several routing policies for responding to queries.
-   Simple routing is used for a single resource that performs a specific function.
-   Weighted round robin routing is used to route traffic to multiple resources in specific proportions.
-   Latency routing is used to route traffic to the AWS Region that provides the best latency.
-   Geolocation routing is used to route traffic based on the location of users.
-   Geoproximity routing is used to route traffic based on the location of resources and shift traffic from one location to another.
-   Failover routing is used for active-passive failover and redirects users to alternate locations in case of an outage.
-   Multivalue answer routing is used to respond to DNS queries with up to eight healthy records selected at random.

![](https://i.imgur.com/OyZeqDI.png)

### Amazon Route 53 DNS failover

Amazon Route 53 enables you to improve the availability of your applications that run on AWS by:

-   Configuring backup and failover scenarios for your own applications.
-   Enabling highly available multi-Region architectures on AWS.
-   Creating health checks to monitor the health and performance of your web applications, web servers, and other resources.
-   Each health check that you create can monitor the health of a specified resource, the status of other health checks, and the status of an Amazon CloudWatch alarm.

![](https://i.imgur.com/k9m5CP9.png)

### DNS failover for a multi-tiered web application

-   DNS failover is a feature in Amazon Route 53 that enables you to configure backup and failover scenarios for your applications.
-   In a multi-tiered web application, traffic is passed to a load balancer which then distributes traffic to a fleet of EC2 instances.
-   To ensure high availability with DNS failover, you can create two DNS records for the Canonical Name Record (CNAME) with a routing policy of Failover Routing.
-   The first record is the primary route policy, which points to the load balancer for your web application. The second record is the secondary route policy, which points to your static Amazon S3 website.
-   Route 53 health checks can be used to monitor the health of the primary route policy, and if it goes down, failover to the secondary route policy is triggered.
-   Failover can be triggered if the web server goes down or stops responding, or if the database instance goes down.

![](https://i.imgur.com/CvESBFQ.png)

### Key Takeaways

Some keytakeaways from this section of the module include:
- Amazon Route 53 is a highly available and scalable cloud DNS web service that translates domain names into numeric IP addresses.
- Amazon Route 53 supports several types of routing policies.
- Multi-Region deployment improves your application’s performance for a global audience.
- You can use Amazon Route 53 failover to improve the availability of your applications

## Section 6: Amazon CloudFront
---

### Content delivery and network latency

-   Network performance is a challenge for network communication.
-   Requests go through many different networks to reach an origin server, which stores the original versions of the objects.
-   The number of network hops and the distance traveled affect the performance and responsiveness of the website.
-   Network latency differs across geographic locations.
-   A content delivery network (CDN) can solve these issues.

![](https://i.imgur.com/0loLRRj.png)

### Content delivery network (CDN)

-   A content delivery network (CDN) is a system of caching servers distributed globally.
-   CDNs cache commonly requested files from the application origin server.
-   CDNs deliver a local copy of the requested content from a cache edge or Point of Presence that provides the fastest delivery to the requester.
-   CDNs can deliver dynamic content that is unique to the requester and is not cacheable, improving application performance and scaling.
-   CDNs establish and maintain secure connections closer to the requester, accelerating routing back to the origin to retrieve dynamic content if the CDN is on the same network as the origin.
-   CDNs can ingest and send content such as form data, images, and text back to the origin, taking advantage of the low-latency connections and proxy behavior of the PoP.

### Amazon CloudFront

-   Amazon CloudFront is a fast and developer-friendly CDN service.
-   It securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.
-   It uses a global network of edge locations and Regional edge caches to deliver files to users.
-   It does not require negotiated contracts, high prices, or minimum fees, and uses pay-as-you-go pricing.
-   It provides a self-service offering that is easy to use and configure.

### Amazon CloudFront infrastructure

-   Amazon CloudFront is a CDN service that securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.
-   CloudFront delivers content through a worldwide network of data centers called edge locations, which are designed to serve popular content quickly to viewers.
-   When a user requests content, they are routed to the edge location with the lowest latency to deliver the content with the best possible performance.
-   CloudFront also has Regional edge caches that are closer to viewers and have larger caches than individual edge locations. Regional edge caches reduce the need for CloudFront to go back to the origin server and improve overall performance for viewers.

### Amazon CloudFront benefits

-   Amazon CloudFront is a fast CDN service that securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.
-   Amazon CloudFront uses a global network of edge locations and regional caches to deliver content to end users with low latency.
-   Amazon CloudFront provides both network-level and application-level protection to ensure security at the edge.
-   Amazon CloudFront is highly programmable and can be customized for specific application requirements, including the ability to run custom code with Lambda@Edge, integrate with other DevOps tools, and support CI/CD environments.
-   Amazon CloudFront is deeply integrated with AWS, with APIs and the AWS Management Console allowing for programmatically configuration of all features in the CDN.
-   Amazon CloudFront is also cost effective because there it has no minimum commitments and charges you for what you use.

### Amazon CloudFront pricing

-   Data transfer out, charged based on the volume of data transferred out from Amazon CloudFront edge locations to the internet or to your origin.
-   HTTP(S) requests, charged based on the number of requests made to Amazon CloudFront for your content.
-   Invalidation requests, charged per path in your invalidation request beyond the first 1,000 paths requested.
-   Dedicated IP custom Secure Sockets Layer (SSL), charged at $600 per month for each custom SSL certificate associated with one or more CloudFront distributions that use the Dedicated IP version of custom SSL certificate support, prorated by the hour.

### Key Takeaways

Some keytakeaways from this section of the module include:
- A CDN is a globally distributed system of caching servers that accelerates delivery of content.
- Amazon CloudFront is a fast CDN service that securely delivers data, videos, applications, and APIs over a global infrastructure with low latency and high transfer speeds.
- Amazon CloudFront offers many benefits, including:
- Fast and global•Security at the edge
- Highly programmable
- Deeply integrated with AWS•Cost-effective































