# AWS SAA Definitions

## IAM users, groups, policies

IAM users are individual identities, groups collect users, and policies define permissions in AWS Identity and Access Management. Their main purpose is to control who can access AWS resources and what actions they can perform. On the exam, remember that IAM users are for long-term identities, groups simplify permission management, and policies are JSON documents that allow or deny actions.

## IAM roles for AWS services

IAM roles are identities with permissions that can be assumed by AWS services, applications, or users without using long-term access keys. Their main purpose is to grant temporary, secure access to AWS resources. For example, an EC2 instance can use an IAM role to access S3 instead of storing credentials on the instance.

## IAM policy evaluation logic

IAM policy evaluation is the process AWS uses to decide whether a request is allowed or denied. AWS starts with an implicit deny, allows access only if a matching allow exists, and always lets an explicit deny override any allow. This logic helps solve permission conflicts across identity policies, resource policies, boundaries, and organization policies.

## IAM conditions

IAM conditions are policy elements that restrict when a permission applies based on context, such as source IP, MFA status, tags, time, or encryption settings. Their purpose is to make IAM permissions more precise than simply allowing an action on a resource. Conditions help solve exam scenarios requiring access only under specific security or network requirements.

## IAM permission boundaries

An IAM permission boundary sets the maximum permissions an IAM user or role can receive, even if identity policies grant more. It does not grant permissions by itself; it only limits what identity-based policies can allow. Permission boundaries are useful for delegating IAM administration safely without giving administrators unlimited privilege.

## IAM resource-based policies vs IAM roles

Resource-based policies are attached directly to resources, such as S3 buckets or Lambda functions, and specify who can access that resource. IAM roles are identities that trusted principals can assume to receive temporary permissions. Use resource-based policies when the resource should directly trust another principal, and use roles when an identity needs temporary permissions to act.

## IAM Identity Center

IAM Identity Center is AWS’s managed service for centralized workforce access to multiple AWS accounts and applications. Its main purpose is to provide single sign-on, permission sets, and integration with identity providers. It helps organizations avoid managing separate IAM users in each AWS account.

## AWS Organizations

AWS Organizations is a managed account management service for centrally organizing and governing multiple AWS accounts. Its main purpose is consolidated billing, account grouping, and policy-based control across an organization. It helps solve multi-account governance problems for security, cost, and operational separation.

## Organizational Units

Organizational Units, or OUs, are containers inside AWS Organizations used to group AWS accounts. Their main purpose is to apply policies, such as Service Control Policies, to multiple accounts at once. OUs help structure accounts by environment, team, workload, or compliance boundary.

## Service Control Policies / organization policies

Service Control Policies, or SCPs, define the maximum available permissions for accounts in AWS Organizations. They do not grant permissions directly; they only limit what IAM principals in affected accounts can do. SCPs help enforce organization-wide guardrails, such as preventing use of specific Regions or blocking high-risk services.

## AWS Control Tower

AWS Control Tower is a managed service that helps set up and govern a secure multi-account AWS environment. Its main purpose is to create a landing zone using AWS Organizations, IAM Identity Center, logging, and guardrails. It helps organizations quickly establish account governance without building everything manually.

## AWS Control Tower guardrails

AWS Control Tower guardrails are governance rules that help enforce or detect compliance across accounts in a landing zone. Preventive guardrails usually use SCPs to block actions, while detective guardrails use AWS Config rules to monitor compliance. They help keep multi-account environments aligned with security and operational standards.

## AWS KMS

AWS Key Management Service is a managed security service for creating and controlling encryption keys. Its main purpose is to encrypt and decrypt data used by services such as S3, EBS, RDS, Lambda, and Secrets Manager. KMS helps solve centralized key management, auditability, and access control for encryption in AWS.

## KMS key types

KMS key types include AWS owned keys, AWS managed keys, customer managed keys, and imported key material. AWS managed keys are created and managed for AWS services, while customer managed keys give you more control over policies, rotation, aliases, and auditing. This distinction matters on the exam when deciding how much control and management responsibility is required.

## KMS multi-Region keys

KMS multi-Region keys are customer managed KMS keys that can be replicated into multiple AWS Regions while sharing the same key ID and key material. Their main purpose is to support client-side encryption or disaster recovery designs that need decrypt operations across Regions. They are useful when encrypted data must be moved or replicated across Regions without re-encryption complexity.

## S3 encryption: SSE-S3, SSE-KMS, SSE-C

S3 server-side encryption protects objects at rest using encryption handled by Amazon S3. SSE-S3 uses S3-managed keys, SSE-KMS uses AWS KMS keys with audit and access control features, and SSE-C uses customer-provided keys that AWS does not store. These options solve different levels of control, compliance, and key management requirements for S3 data.

## S3 client-side encryption

S3 client-side encryption means the application encrypts data before uploading it to Amazon S3. Its main purpose is to keep encryption and decryption under client control instead of relying only on S3 server-side encryption. This helps when data must remain encrypted before it reaches AWS or when the client must manage the encryption process.

## S3 in-transit encryption

S3 in-transit encryption protects data while it travels between clients and Amazon S3 using HTTPS/TLS. Its main purpose is to prevent network interception or tampering during upload and download. On the exam, bucket policies can enforce secure transport by denying requests that do not use HTTPS.

## SSM Parameter Store

AWS Systems Manager Parameter Store is a managed service for storing configuration data and simple secrets as parameters. Its main purpose is to centralize values such as AMI IDs, database strings, feature flags, and passwords used by applications. SecureString parameters can use KMS encryption, but Secrets Manager is usually preferred for advanced secret rotation.

## AWS Secrets Manager

AWS Secrets Manager is a managed security service for storing, retrieving, and rotating secrets such as database credentials and API keys. Its main purpose is to avoid hardcoding sensitive values in applications. It is especially useful when automatic rotation, fine-grained access, and integration with services like RDS are required.

## AWS Certificate Manager

AWS Certificate Manager, or ACM, is a managed service for provisioning, managing, and renewing public and private SSL/TLS certificates. Its main purpose is to secure HTTPS connections for AWS services such as ALB, CloudFront, and API Gateway. ACM reduces operational work by handling certificate renewal for supported public certificates.

## ACM with ALB

ACM integrates with Application Load Balancer to provide HTTPS termination at the load balancer. Its main purpose is to secure web applications without installing certificates directly on EC2 instances. On the exam, use ACM certificates with ALB listeners for managed TLS on HTTP and HTTPS workloads.

## ACM with API Gateway

ACM integrates with Amazon API Gateway to secure custom domain names using TLS certificates. Its main purpose is to provide HTTPS endpoints for APIs with managed certificate handling. For Regional API Gateway custom domains, certificates must be in the same Region, while edge-optimized APIs use certificates in us-east-1.

## AWS WAF

AWS WAF is a web application firewall that protects HTTP and HTTPS applications from common web attacks. Its main purpose is to filter requests using rules for IP addresses, headers, SQL injection, cross-site scripting, rate limits, and managed rule groups. It is commonly used with CloudFront, ALB, API Gateway, and AppSync.

## AWS Shield

AWS Shield is a managed DDoS protection service for AWS resources. Shield Standard is automatically included and protects against common network and transport layer attacks, while Shield Advanced adds stronger protection, cost safeguards, and support. It helps protect availability for internet-facing workloads.

## AWS Firewall Manager

AWS Firewall Manager is a security management service for centrally configuring firewall rules across accounts in AWS Organizations. Its main purpose is to manage services like AWS WAF, Shield Advanced, security groups, and AWS Network Firewall at scale. It solves multi-account firewall governance instead of protecting a single resource directly.

## WAF vs Shield vs Firewall Manager

AWS WAF filters application-layer web requests, AWS Shield protects against DDoS attacks, and AWS Firewall Manager centrally manages firewall protections across accounts. WAF is best for HTTP rule filtering, Shield is best for DDoS resilience, and Firewall Manager is best for organization-wide enforcement. This comparison is common in exam questions about web security and multi-account governance.

## Amazon GuardDuty

Amazon GuardDuty is a managed threat detection service that analyzes logs and signals for suspicious activity. Its main purpose is to detect threats such as compromised credentials, unusual API calls, cryptocurrency mining, and malicious IP communication. It uses sources such as CloudTrail events, VPC Flow Logs, DNS logs, and optional workload protection features.

## Amazon Inspector

Amazon Inspector is a managed vulnerability management service for scanning workloads such as EC2 instances, container images in ECR, and Lambda functions. Its main purpose is to find software vulnerabilities and unintended network exposure. It helps solve security assessment needs without manually running separate vulnerability scanners.

## Amazon Macie

Amazon Macie is a managed data security and privacy service focused on discovering sensitive data in Amazon S3. Its main purpose is to identify data such as personally identifiable information and help evaluate S3 bucket security. It is the exam choice when the question asks to discover or classify sensitive data stored in S3.

## S3 bucket policies

S3 bucket policies are resource-based JSON policies attached to S3 buckets. Their main purpose is to control access to buckets and objects based on principals, actions, resources, and conditions. They are commonly used for cross-account access, enforcing HTTPS, requiring encryption, or granting public access when allowed.

## S3 IAM access

S3 IAM access uses identity-based IAM policies attached to users, groups, or roles to allow S3 actions. Its main purpose is to control what an AWS identity can do across S3 buckets and objects. Unlike bucket policies, IAM policies follow the identity and are often used for application roles or user permissions.

## S3 Block Public Access

S3 Block Public Access is a security feature that prevents public access to S3 buckets and objects. Its main purpose is to protect data from accidental exposure through ACLs or bucket policies. It can be enabled at the account or bucket level and is usually the safest default for private data.

## S3 pre-signed URLs

S3 pre-signed URLs grant temporary access to a specific S3 object using the permissions of the creator. Their main purpose is to let users upload or download private objects without requiring AWS credentials. They help solve short-lived access scenarios such as secure file sharing or temporary uploads.

## S3 access points

S3 access points are named network endpoints with dedicated access policies for accessing shared S3 buckets. Their main purpose is to simplify access management for large datasets used by different applications or teams. Each access point can enforce its own permissions and network controls, including VPC-only access.

## S3 Object Lock

S3 Object Lock protects objects from deletion or overwrite using write-once-read-many controls. Its main purpose is to support retention, compliance, and protection against accidental or malicious deletion. It works with versioned buckets and can use governance or compliance mode.

## Glacier Vault Lock

Glacier Vault Lock enforces compliance controls on Amazon S3 Glacier vaults using a lockable policy. Its main purpose is to apply write-once-read-many retention rules for archive data. Once locked, the policy cannot be changed, which supports strict regulatory archive requirements.

## VPC

A Virtual Private Cloud, or VPC, is a logically isolated network in AWS where you launch resources such as EC2, RDS, and load balancers. Its main purpose is to control IP addressing, subnets, routing, and network security. A VPC is Region-scoped and forms the foundation of AWS networking.

## Subnets

Subnets are subdivisions of a VPC IP address range that exist in a single Availability Zone. Their main purpose is to place resources into public or private network segments. Public subnets route to an internet gateway, while private subnets usually use NAT or private connectivity for outbound access.

## Internet Gateway

An Internet Gateway is a horizontally scaled VPC component that allows communication between a VPC and the internet. Its main purpose is to provide internet access for resources in public subnets with public IP addresses and proper routes. It supports both inbound and outbound internet connectivity.

## NAT Gateway

A NAT Gateway is a managed AWS networking service that allows private subnet resources to initiate outbound internet or public AWS service connections. Its main purpose is to keep instances private while allowing updates, downloads, or external API calls. NAT Gateway is highly available within an Availability Zone and is preferred over NAT instances for managed scalability.

## NAT Instance

A NAT Instance is an EC2 instance configured to provide outbound internet access for private subnet resources. Its main purpose is similar to NAT Gateway, but it requires manual management, scaling, patching, and high availability design. It may be used when custom networking controls are required, but it is less managed than NAT Gateway.

## Security Groups

Security Groups are stateful virtual firewalls attached to elastic network interfaces, EC2 instances, load balancers, and other resources. Their main purpose is to control inbound and outbound traffic using allow rules. Because they are stateful, return traffic is automatically allowed without a separate rule.

## Network ACLs

Network ACLs, or NACLs, are stateless firewalls applied at the subnet level in a VPC. Their main purpose is to provide an additional network control layer using numbered allow and deny rules. Because they are stateless, both inbound and outbound rules must explicitly allow the traffic.

## Stateless vs stateful firewalls

Stateful firewalls remember connection state and automatically allow return traffic for an allowed request. Stateless firewalls evaluate each packet independently and require rules for both request and response traffic. In AWS, Security Groups are stateful, while Network ACLs are stateless.

## VPC Peering

VPC Peering is a private networking connection between two VPCs that allows resources to communicate using private IP addresses. Its main purpose is to connect VPCs without using the public internet. VPC peering is non-transitive, so traffic cannot pass through one peered VPC to reach another.

## VPC Endpoints

VPC Endpoints let resources in a VPC privately connect to supported AWS services without using the public internet, NAT Gateway, or internet gateway. Gateway endpoints are used for S3 and DynamoDB, while interface endpoints use PrivateLink for many other services. They improve security and can reduce data transfer through public paths.

## PrivateLink concept

AWS PrivateLink provides private connectivity to AWS services, third-party services, or your own services using interface endpoints. Its main purpose is to expose services privately without opening public internet access or requiring VPC peering. It is commonly used for secure service-to-service access across VPCs or accounts.

## VPC Flow Logs

VPC Flow Logs capture metadata about IP traffic going to and from network interfaces, subnets, or VPCs. Their main purpose is network monitoring, troubleshooting, and security analysis. They do not capture packet payloads, only flow information such as source, destination, ports, protocol, and accept or reject status.

## Site-to-Site VPN

AWS Site-to-Site VPN creates an encrypted IPsec connection between an on-premises network and AWS. Its main purpose is secure hybrid connectivity over the public internet. It is faster to set up than Direct Connect but can have less predictable performance because it uses internet paths.

## Virtual Private Gateway

A Virtual Private Gateway is the AWS-side VPN endpoint attached to a VPC for Site-to-Site VPN connections. Its main purpose is to connect a single VPC to an on-premises network. It is commonly seen in exam questions about traditional hybrid connectivity for one VPC.

## Direct Connect

AWS Direct Connect provides a dedicated private network connection from on-premises locations to AWS. Its main purpose is to deliver more consistent bandwidth, lower latency, and private connectivity than internet-based VPN. It does not encrypt traffic by default, so encryption may require VPN over Direct Connect or other controls.

## Direct Connect Gateway

A Direct Connect Gateway connects Direct Connect connections to multiple VPCs across different AWS Regions or accounts. Its main purpose is to simplify global hybrid connectivity without needing separate Direct Connect links for every VPC. It works with virtual private gateways or transit gateways depending on the design.

## Transit Gateway

AWS Transit Gateway is a managed regional hub for connecting VPCs, VPNs, and Direct Connect attachments. Its main purpose is to simplify large-scale network routing using a hub-and-spoke model. It solves the complexity of many VPC peering connections and supports transitive routing.

## Egress-only Internet Gateway

An Egress-only Internet Gateway allows outbound IPv6 internet access from a VPC while blocking unsolicited inbound IPv6 connections. Its main purpose is to give private IPv6 resources internet egress similar to NAT behavior for IPv4. It is used only for IPv6 traffic.

## AWS Network Firewall

AWS Network Firewall is a managed network security service for deploying stateful firewall protection inside a VPC. Its main purpose is to inspect and filter traffic using rules for domains, IPs, protocols, and intrusion prevention patterns. It helps solve centralized network inspection requirements beyond basic security groups and NACLs.

## VPC traffic mirroring

VPC Traffic Mirroring copies network traffic from elastic network interfaces to security and monitoring appliances. Its main purpose is deep packet inspection, threat detection, and troubleshooting. Unlike VPC Flow Logs, traffic mirroring can provide packet-level visibility.

## Networking costs

Networking costs in AWS often come from data transfer between Availability Zones, Regions, internet egress, NAT Gateway processing, load balancers, and endpoints. The main purpose of understanding these costs is to design architectures that are secure and efficient without unexpected charges. Exam questions often test whether private routing, caching, or regional placement can reduce network cost.

## Route 53 hosted zones

Route 53 hosted zones are containers for DNS records for a domain. Public hosted zones answer DNS queries from the internet, while private hosted zones answer queries inside associated VPCs. Their main purpose is to manage how domain names resolve to AWS or external resources.

## Route 53 record types

Route 53 record types define what kind of DNS answer is returned, such as A, AAAA, CNAME, MX, TXT, NS, or alias records. Their main purpose is to map domain names to IP addresses, services, mail servers, verification values, or other names. On the exam, A and AAAA map to IP addresses, while CNAME maps one name to another name.

## Route 53 TTL

Route 53 TTL, or time to live, controls how long DNS resolvers cache a DNS record. Its main purpose is to balance faster DNS changes against lower query volume and caching efficiency. Lower TTL helps during migrations or failovers, while higher TTL reduces repeated lookups.

## Route 53 alias records

Route 53 alias records are AWS-specific DNS records that map a domain to supported AWS resources such as CloudFront, ALB, API Gateway, or S3 website endpoints. Their main purpose is to provide DNS mapping like a CNAME while supporting root domains and no extra Route 53 query charge for many AWS targets. Alias records are commonly preferred for AWS endpoints.

## Simple routing policy

Simple routing is a Route 53 routing policy that returns one or more record values without special traffic logic. Its main purpose is basic DNS resolution for a single resource or a simple set of records. It does not support advanced decisions such as latency, weight, geolocation, or failover.

## Weighted routing policy

Weighted routing is a Route 53 policy that distributes DNS responses based on assigned weights. Its main purpose is controlled traffic splitting, such as blue-green deployments, canary releases, or gradual migrations. A higher weight receives a larger share of DNS responses.

## Latency routing policy

Latency routing is a Route 53 policy that sends users to the AWS Region with the lowest measured network latency. Its main purpose is improving user performance for applications deployed in multiple Regions. It chooses based on latency measurements, not geographic distance alone.

## Failover routing policy

Failover routing is a Route 53 policy that routes traffic to a primary resource when healthy and a secondary resource when the primary fails. Its main purpose is DNS-level disaster recovery or high availability. It requires health checks to determine whether the primary endpoint is available.

## Geolocation routing policy

Geolocation routing is a Route 53 policy that routes users based on their geographic location, such as country, continent, or US state. Its main purpose is location-specific content, compliance, or localization. It is based on where the user is located, not necessarily which endpoint is fastest.

## Geoproximity routing policy

Geoproximity routing is a Route 53 policy that routes traffic based on the physical distance between users and resources, with optional bias adjustments. Its main purpose is shifting traffic toward or away from specific locations. It is commonly associated with advanced traffic management using Route 53 traffic flow.

## IP-based routing policy

IP-based routing is a Route 53 policy that routes DNS queries based on the client resolver’s IP range. Its main purpose is to control routing for known networks, such as ISPs, corporate offices, or partner IP ranges. It is useful when routing decisions need to follow specific CIDR blocks.

## Multi-value answer routing

Multi-value answer routing is a Route 53 policy that returns multiple healthy records in response to DNS queries. Its main purpose is simple DNS-based load distribution with health checking. It is not a replacement for an Elastic Load Balancer but can improve availability for multiple endpoints.

## Route 53 health checks

Route 53 health checks monitor endpoints or CloudWatch alarms to determine whether DNS records should be considered healthy. Their main purpose is to support routing policies like failover and multi-value answer routing. They help Route 53 avoid returning unhealthy endpoints when properly configured.

## EC2 basics

Amazon EC2 is AWS’s core compute service for running virtual servers called instances. Its main purpose is to provide resizable compute capacity where you choose the instance type, operating system, networking, storage, and security settings. EC2 is useful when you need control over servers rather than fully serverless compute.

## EC2 sizing and configuration

EC2 sizing and configuration means choosing CPU, memory, storage, networking, AMI, and instance settings that match workload requirements. Its main purpose is to balance performance, availability, and cost. On the exam, right-sizing helps avoid overprovisioning while still meeting application needs.

## EC2 instance types

EC2 instance types are families of virtual machines optimized for different workloads, such as general purpose, compute optimized, memory optimized, storage optimized, and accelerated computing. Their main purpose is to match hardware characteristics to application needs. For example, compute optimized instances suit CPU-heavy workloads, while memory optimized instances suit large in-memory databases.

## EC2 IAM roles

EC2 IAM roles provide temporary AWS credentials to applications running on EC2 instances. Their main purpose is to let instances securely access AWS services such as S3, DynamoDB, or CloudWatch without storing access keys. This is the recommended exam answer for granting AWS permissions to EC2 workloads.

## EC2 SSH connection

An EC2 SSH connection is a secure shell connection used to administer Linux EC2 instances. Its main purpose is remote command-line access using a private key and network access through security groups. SSH typically uses port 22, but production architectures often limit access or use Systems Manager Session Manager instead.

## EC2 purchase options

EC2 purchase options define how you pay for instance capacity, such as On-Demand, Reserved Instances, Savings Plans, Spot Instances, Dedicated Hosts, and Dedicated Instances. Their main purpose is to match cost model to workload predictability, flexibility, and compliance needs. Choosing the right option is a major SAA exam cost optimization theme.

## On-Demand Instances

On-Demand Instances let you pay for EC2 compute by the second or hour without long-term commitment. Their main purpose is flexibility for unpredictable, short-term, or development workloads. They cost more than commitment-based options but are simple and require no upfront planning.

## Reserved Instances

Reserved Instances provide a billing discount for committing to specific EC2 usage over a one-year or three-year term. Their main purpose is cost savings for steady, predictable workloads. Standard RIs offer the highest discount with less flexibility, while Convertible RIs allow more changes with a lower discount.

## Savings Plans

Savings Plans provide discounted compute pricing in exchange for a commitment to a consistent amount of usage per hour. Their main purpose is flexible cost savings across EC2, Fargate, and Lambda depending on the plan type. They are often more flexible than Reserved Instances for changing instance families or compute services.

## Spot Instances

Spot Instances use spare EC2 capacity at large discounts but can be interrupted when AWS needs the capacity back. Their main purpose is low-cost compute for fault-tolerant, flexible, or batch workloads. They are not ideal for workloads that cannot handle interruption.

## Dedicated Hosts

Dedicated Hosts provide a physical server fully dedicated to your use. Their main purpose is compliance, licensing, or visibility into physical cores and sockets. They are useful when software licenses are tied to physical server characteristics.

## Dedicated Instances

Dedicated Instances run on hardware dedicated to a single customer account but do not provide the same physical server visibility as Dedicated Hosts. Their main purpose is workload isolation at the hardware level. They are simpler than Dedicated Hosts but offer less control for license management.

## Elastic IP

An Elastic IP is a static public IPv4 address that you can allocate to your AWS account and remap to resources. Its main purpose is to keep a consistent public address even if an instance changes. On the exam, remember that unnecessary or unattached Elastic IPs can create cost.

## Elastic Network Interface

An Elastic Network Interface, or ENI, is a virtual network card in a VPC. Its main purpose is to provide private IP addresses, security groups, MAC address, and network attachment to resources such as EC2 instances. ENIs can be moved between instances in some designs for failover.

## Cluster placement group

A cluster placement group places EC2 instances close together within one Availability Zone. Its main purpose is low-latency, high-throughput networking between instances. It is best for tightly coupled HPC or high-performance workloads but has less placement flexibility.

## Spread placement group

A spread placement group places instances across distinct underlying hardware. Its main purpose is reducing the risk of simultaneous failure for a small number of critical instances. It is best when each instance must be isolated from hardware failure impact.

## Partition placement group

A partition placement group spreads instances across logical partitions, where each partition has separate underlying hardware. Its main purpose is to reduce correlated failure for large distributed systems such as Hadoop, Cassandra, or Kafka. It provides more scale than spread placement groups while still limiting failure impact.

## EC2 Hibernate

EC2 Hibernate saves an instance’s in-memory RAM state to the root EBS volume before stopping it. Its main purpose is faster startup for applications that take a long time to initialize. When restarted, the instance resumes with the previous memory state instead of booting from scratch.

## Golden AMI

A Golden AMI is a preconfigured Amazon Machine Image that contains approved operating system settings, patches, agents, and application dependencies. Its main purpose is to standardize EC2 deployments and reduce launch-time configuration. It helps enforce consistency across environments and Auto Scaling groups.

## Elastic Beanstalk

AWS Elastic Beanstalk is a managed platform service for deploying and scaling web applications without manually managing all infrastructure. Its main purpose is to handle provisioning of resources such as EC2, load balancers, Auto Scaling, and monitoring from application code. It is useful when developers want control over the platform but less operational setup.

## Elastic Load Balancers

Elastic Load Balancing distributes incoming traffic across multiple targets such as EC2 instances, containers, IP addresses, or Lambda functions. Its main purpose is to improve availability, scalability, and fault tolerance. AWS provides Application Load Balancer, Network Load Balancer, Gateway Load Balancer, and Classic Load Balancer.

## Application Load Balancer

Application Load Balancer is a Layer 7 load balancer for HTTP and HTTPS traffic. Its main purpose is advanced request routing based on host, path, headers, methods, query strings, and target groups. It is commonly used for web applications, microservices, containers, and TLS termination.

## Network Load Balancer

Network Load Balancer is a Layer 4 load balancer for TCP, UDP, and TLS traffic with very high performance and low latency. Its main purpose is handling millions of requests per second while preserving static IP support. It is best for non-HTTP traffic or extreme performance requirements.

## Gateway Load Balancer

Gateway Load Balancer helps deploy, scale, and manage third-party virtual appliances such as firewalls and intrusion detection systems. Its main purpose is transparent network traffic inspection using a single entry and exit point. It operates at Layer 3 and is used for security appliance architectures.

## Target groups

Target groups define the destinations that a load balancer routes traffic to, such as EC2 instances, IP addresses, Lambda functions, or containers. Their main purpose is to group backend targets and perform health checks. They are central to ALB and NLB routing decisions.

## Sticky sessions

Sticky sessions make a load balancer send requests from the same client to the same target for a period of time. Their main purpose is to support applications that store session state locally on a server. On the exam, a better scalable design often stores session state outside the instance, such as in ElastiCache or DynamoDB.

## Cross-zone load balancing

Cross-zone load balancing distributes traffic evenly across targets in all enabled Availability Zones. Its main purpose is to prevent uneven load when each Availability Zone has a different number of targets. It improves balancing behavior but can have service-specific cost or configuration considerations.

## Connection draining

Connection draining, also called deregistration delay, allows existing requests to finish before a load balancer stops sending traffic to a target being removed. Its main purpose is graceful instance replacement during deployments, scaling, or maintenance. It helps avoid interrupting active user connections.

## Auto Scaling Groups

Auto Scaling Groups manage a fleet of EC2 instances by launching, terminating, and replacing instances based on desired capacity and health. Their main purpose is automatic scaling and self-healing for EC2 workloads. They work with launch templates, load balancers, health checks, and scaling policies.

## Scaling policies

Scaling policies define how Auto Scaling Groups adjust capacity based on metrics or schedules. Their main purpose is to add or remove instances automatically to match demand. Common types include target tracking, step scaling, simple scaling, and scheduled scaling.

## Scaling cooldown

Scaling cooldown is a waiting period after a scaling action before another simple scaling action can occur. Its main purpose is to give new capacity time to start and affect metrics before making more changes. It helps prevent rapid over-scaling or under-scaling from temporary metric changes.

## Amazon S3

Amazon S3 is a managed object storage service designed for high durability, scalability, and availability. Its main purpose is storing and retrieving objects such as files, backups, logs, media, and data lake content. S3 stores data in buckets and is not a traditional block or file system.

## S3 lifecycle policies

S3 lifecycle policies automatically transition or expire objects based on rules. Their main purpose is to reduce storage cost and manage data retention over time. They can move objects to cheaper storage classes or delete old object versions when no longer needed.

## S3 Standard

S3 Standard is the default S3 storage class for frequently accessed data. Its main purpose is high durability, high availability, and low-latency access across multiple Availability Zones. It is best for active data such as websites, content distribution, and frequently used application objects.

## S3 Intelligent-Tiering

S3 Intelligent-Tiering automatically moves objects between access tiers based on changing access patterns. Its main purpose is to optimize storage cost when access patterns are unknown or unpredictable. It keeps frequent access performance while reducing cost for rarely accessed objects.

## S3 Standard-IA

S3 Standard-Infrequent Access is an S3 storage class for data accessed less often but still requiring rapid retrieval. Its main purpose is lower storage cost than S3 Standard for infrequently accessed data stored across multiple Availability Zones. It has retrieval costs and is suitable for backups or long-lived data.

## S3 One Zone-IA

S3 One Zone-Infrequent Access stores infrequently accessed data in a single Availability Zone. Its main purpose is lower cost for data that can be recreated or does not require multi-AZ resilience. It is less resilient than Standard-IA because data is not stored across multiple Availability Zones.

## S3 Glacier classes

S3 Glacier storage classes are low-cost S3 options for archive data with different retrieval times. Their main purpose is long-term retention for data that is rarely accessed. Glacier Instant Retrieval, Flexible Retrieval, and Deep Archive trade off retrieval speed and storage cost.

## S3 versioning

S3 versioning keeps multiple versions of an object in the same bucket. Its main purpose is protection against accidental overwrite or deletion. Versioning is also required for features such as S3 replication and Object Lock.

## S3 replication

S3 replication automatically copies objects from one bucket to another bucket in the same or different Region. Its main purpose is data redundancy, compliance, latency optimization, or account separation. Versioning must be enabled on both source and destination buckets.

## Cross-Region Replication

Cross-Region Replication copies S3 objects from a source bucket to a destination bucket in another AWS Region. Its main purpose is disaster recovery, geographic compliance, or lower-latency access for users in another Region. It requires versioning and appropriate IAM permissions.

## Same-Region Replication

Same-Region Replication copies S3 objects between buckets in the same AWS Region. Its main purpose is log aggregation, compliance copies, account separation, or maintaining replicas without crossing Regions. It uses S3 replication features while keeping data regional.

## Live replication

Live replication copies new S3 objects automatically after replication is configured. Its main purpose is to keep destination buckets updated for newly written data. It does not automatically copy existing objects that were already in the bucket before replication was enabled.

## On-demand replication

On-demand replication copies existing S3 objects that were not replicated by live replication. Its main purpose is backfilling replicas after enabling replication or retrying replication for selected objects. It is commonly performed using S3 Batch Replication.

## S3 Batch Operations

S3 Batch Operations performs large-scale actions on many S3 objects using a manifest. Its main purpose is to automate bulk changes such as copying objects, invoking Lambda, restoring Glacier objects, or applying tags. It helps manage millions or billions of objects without custom scripts.

## S3 static website hosting

S3 static website hosting lets an S3 bucket serve static web content such as HTML, CSS, JavaScript, and images. Its main purpose is low-cost hosting for static sites without servers. It does not support dynamic server-side processing and often pairs with CloudFront for HTTPS and caching.

## S3 CORS

S3 CORS controls whether web applications from one domain can access resources in an S3 bucket from another domain. Its main purpose is enabling browser-based cross-origin requests safely. It is required when a frontend site needs to directly load or upload S3 objects from a different origin.

## S3 MFA Delete

S3 MFA Delete requires multi-factor authentication to permanently delete object versions or change versioning state. Its main purpose is extra protection against accidental or unauthorized destructive S3 actions. It can only be configured by the root user through specific API or CLI operations.

## S3 access logs

S3 server access logging records detailed requests made to an S3 bucket and stores the logs in another bucket. Its main purpose is audit, troubleshooting, and usage analysis for S3 access. It is different from CloudTrail data events, which record API activity.

## Requester Pays

Requester Pays is an S3 bucket setting where the requester pays for request and data transfer costs instead of the bucket owner. Its main purpose is sharing large datasets while shifting access costs to consumers. The requester must include a request-payer flag when accessing the data.

## S3 Event Notifications

S3 Event Notifications publish events when object actions occur, such as object creation or deletion. Their main purpose is triggering workflows using destinations like Lambda, SQS, or SNS. They help build event-driven processing pipelines for uploaded or changed objects.

## S3 Storage Lens

S3 Storage Lens provides organization-wide visibility into S3 storage usage, activity, and trends. Its main purpose is cost optimization, data protection analysis, and identifying storage patterns. It helps monitor many buckets and accounts through dashboards and metrics.

## EBS

Amazon Elastic Block Store, or EBS, provides persistent block storage volumes for EC2 instances. Its main purpose is low-latency storage for operating systems, databases, and applications that need block devices. EBS volumes are Availability Zone-scoped and persist independently of an instance unless configured to delete on termination.

## EBS snapshots

EBS snapshots are point-in-time backups of EBS volumes stored in Amazon S3-managed infrastructure. Their main purpose is data protection, volume recovery, and creating new volumes from backups. Snapshots are incremental, meaning only changed blocks are saved after the first snapshot.

## EBS snapshot features

EBS snapshot features include incremental backups, cross-Region copy, sharing, encryption support, and fast snapshot restore. Their main purpose is to improve backup efficiency, recovery, and disaster recovery planning. These features help create new EBS volumes quickly and securely from saved volume states.

## EBS volume types

EBS volume types are storage options optimized for different performance and cost needs, such as gp3, gp2, io2, st1, and sc1. Their main purpose is to match block storage performance to workload requirements. General purpose volumes fit most workloads, provisioned IOPS volumes fit high-performance databases, and throughput or cold HDD volumes fit large sequential workloads.

## EBS Multi-Attach

EBS Multi-Attach allows certain provisioned IOPS EBS volumes to attach to multiple EC2 instances in the same Availability Zone. Its main purpose is supporting clustered applications that manage concurrent block access. The application must handle write coordination because EBS itself is block storage, not a shared file system.

## Amazon Machine Image

An Amazon Machine Image, or AMI, is a template used to launch EC2 instances. Its main purpose is to package an operating system, application software, configuration, and launch permissions. AMIs help standardize and repeatably deploy EC2 instances.

## Instance Store

Instance Store provides temporary block storage physically attached to the host running an EC2 instance. Its main purpose is very fast ephemeral storage for caches, buffers, or temporary data. Data is lost when the instance stops, hibernates, or terminates, so it is not for durable storage.

## EFS

Amazon Elastic File System is a managed, scalable NFS file system for Linux workloads. Its main purpose is shared file storage that multiple EC2 instances, containers, or serverless workloads can access at the same time. EFS is regional, elastic, and designed to scale automatically.

## EFS use cases

EFS is used for shared content repositories, web serving, home directories, container storage, serverless file access, and lift-and-shift Linux applications. Its main purpose is to provide a shared POSIX-style file system without managing file servers. It is the exam choice when multiple Linux instances need concurrent access to the same files.

## EFS performance modes

EFS performance modes control file system latency and throughput scaling behavior. General Purpose is the default for latency-sensitive workloads, while Max I/O supports higher aggregate throughput for highly parallel workloads with slightly higher latency. This helps match EFS behavior to application concurrency needs.

## EFS throughput modes

EFS throughput modes control how much throughput an EFS file system can deliver. Bursting throughput scales with file system size, provisioned throughput sets a chosen throughput independent of size, and elastic throughput automatically scales with workload activity. These modes help balance performance needs and cost.

## EFS storage classes

EFS storage classes optimize file storage cost based on access patterns and resilience needs. Standard stores data across multiple Availability Zones, One Zone stores data in one Availability Zone, and Infrequent Access or Archive tiers reduce cost for rarely accessed files. Lifecycle policies can move files between EFS classes automatically.

## EBS vs EFS vs Instance Store

EBS is persistent block storage for a single EC2 instance in one Availability Zone, while EFS is managed shared file storage for multiple Linux clients. Instance Store is temporary high-performance storage tied to the EC2 host. Choose EBS for disks, EFS for shared files, and Instance Store for ephemeral data.

## Amazon FSx

Amazon FSx provides fully managed file systems for specific file system technologies such as Windows File Server, Lustre, NetApp ONTAP, and OpenZFS. Its main purpose is to run workloads that need specialized file system features or compatibility. It helps avoid managing file servers while supporting enterprise and high-performance file workloads.

## AWS Storage Gateway

AWS Storage Gateway is a hybrid cloud storage service that connects on-premises environments to AWS storage. Its main purpose is to provide local access to cloud-backed storage for files, volumes, or tapes. It helps migrate, back up, and extend on-premises storage to AWS.

## File Gateway

File Gateway is a Storage Gateway type that presents file shares using NFS or SMB while storing data as objects in Amazon S3. Its main purpose is to let on-premises applications use file protocols while benefiting from S3 durability and scalability. It is useful for hybrid file storage and backup to S3.

## Volume Gateway

Volume Gateway is a Storage Gateway type that presents iSCSI block storage volumes to on-premises applications. Its main purpose is hybrid block storage with snapshots stored in AWS. It supports cached volumes for cloud-backed primary data or stored volumes for local primary data with cloud backups.

## Tape Gateway

Tape Gateway is a Storage Gateway type that presents a virtual tape library to backup applications. Its main purpose is replacing physical tape infrastructure with cloud-backed virtual tapes stored in Amazon S3 and archived to Glacier classes. It helps modernize backup workflows without changing tape-based backup software.

## AWS DataSync

AWS DataSync is a managed data transfer service for moving files between on-premises storage, edge locations, and AWS storage services. Its main purpose is fast, automated, and secure migration or synchronization to services like S3, EFS, and FSx. It handles scheduling, encryption, validation, and transfer optimization.

## AWS Transfer Family

AWS Transfer Family is a managed service for file transfers using protocols such as SFTP, FTPS, FTP, and AS2. Its main purpose is to move files into and out of Amazon S3 or EFS without managing transfer servers. It is useful for business-to-business file exchange and legacy transfer workflows.

## AWS Snowball

AWS Snowball is a physical edge device used to transfer large amounts of data into or out of AWS when networks are too slow or costly. Its main purpose is offline data migration and edge processing in disconnected or low-bandwidth environments. Data is copied to the device and shipped securely to AWS for import.

## Snowball into Glacier

Snowball into Glacier means using Snowball to move large archive datasets to AWS, typically landing data in S3 first and then transitioning it to Glacier storage classes. Its main purpose is bulk migration of cold data when direct internet upload is impractical. Lifecycle policies can move imported objects into Glacier classes for long-term low-cost retention.

## Amazon RDS

Amazon Relational Database Service is a managed service for running relational databases such as MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Db2. Its main purpose is to reduce database administration by handling provisioning, backups, patching, monitoring, and high availability options. RDS is best for structured data and SQL-based applications.

## RDS Multi-AZ

RDS Multi-AZ creates a standby database in another Availability Zone for high availability and automatic failover. Its main purpose is resilience, not read scaling. In most standard RDS Multi-AZ deployments, the standby is not used for application reads.

## RDS read replicas

RDS read replicas are copies of a database used to scale read-heavy workloads and support some migration or reporting needs. Their main purpose is read scalability, not automatic high availability failover. They can often be promoted to standalone databases if needed.

## RDS backups

RDS backups include automated backups, transaction logs, and manual snapshots. Their main purpose is point-in-time recovery and long-term database protection. Automated backups are retention-based, while manual snapshots remain until deleted.

## RDS monitoring

RDS monitoring provides visibility into database health, performance, and resource usage using CloudWatch metrics, Enhanced Monitoring, Performance Insights, and logs. Its main purpose is troubleshooting and performance optimization for managed relational databases. It helps identify CPU, memory, storage, connection, and query bottlenecks.

## RDS security

RDS security includes IAM controls, security groups, encryption at rest with KMS, encryption in transit with TLS, subnet groups, and database authentication. Its main purpose is to protect database access and stored data. RDS instances are usually placed in private subnets and accessed only by trusted application layers.

## RDS Proxy

RDS Proxy is a managed database proxy for Amazon RDS and Aurora. Its main purpose is to pool and manage database connections, improving application scalability and resilience. It is especially useful for Lambda or highly concurrent applications that could otherwise overwhelm database connection limits.

## Amazon Aurora

Amazon Aurora is an AWS-managed relational database engine compatible with MySQL and PostgreSQL. Its main purpose is to provide higher performance, availability, and scalability than standard open-source database deployments. Aurora uses a distributed, fault-tolerant storage system that replicates data across multiple Availability Zones.

## Aurora backups

Aurora backups are continuous and automatic to Amazon S3-backed storage, supporting point-in-time recovery within the backup retention period. Their main purpose is protecting Aurora clusters without manual backup scheduling. Aurora also supports manual snapshots for longer-term retention or cloning use cases.

## Aurora security

Aurora security includes VPC isolation, security groups, IAM integration, KMS encryption at rest, TLS encryption in transit, and database-level permissions. Its main purpose is to protect access to relational data while using managed database infrastructure. Aurora can also integrate with Secrets Manager for credential management.

## Aurora global database concept

Aurora Global Database replicates an Aurora database across multiple AWS Regions with low-latency global reads and disaster recovery capabilities. Its main purpose is worldwide read performance and fast cross-Region recovery. It uses one primary Region for writes and secondary Regions for read scaling and failover planning.

## RDS MySQL to Aurora MySQL migration

RDS MySQL to Aurora MySQL migration moves a MySQL-compatible workload from standard RDS to Aurora MySQL. Its main purpose is to gain Aurora performance, storage scaling, and availability features while keeping MySQL compatibility. Common approaches include snapshot restore, read replica promotion, or database migration tools depending on downtime needs.

## Amazon DynamoDB

Amazon DynamoDB is a fully managed serverless NoSQL key-value and document database. Its main purpose is single-digit millisecond performance at almost any scale without managing servers. It is best for applications with known access patterns and high scalability requirements.

## DynamoDB Accelerator / DAX

DynamoDB Accelerator, or DAX, is an in-memory cache designed specifically for DynamoDB. Its main purpose is microsecond read performance for read-heavy DynamoDB workloads. DAX is managed and API-compatible with DynamoDB, but it does not replace DynamoDB as the persistent database.

## DAX vs ElastiCache

DAX is a managed cache built specifically for DynamoDB and accessed through DynamoDB-compatible APIs. ElastiCache is a general-purpose in-memory caching service using Redis or Memcached for many types of applications. Use DAX for DynamoDB read acceleration and ElastiCache for broader caching, session storage, leaderboards, or pub/sub patterns.

## DynamoDB Streams

DynamoDB Streams capture time-ordered changes to items in a DynamoDB table. Their main purpose is enabling event-driven processing when records are inserted, updated, or deleted. Streams are commonly consumed by Lambda to update other systems, maintain aggregates, or trigger workflows.

## DynamoDB Streams vs Kinesis Data Streams

DynamoDB Streams capture item-level changes from a DynamoDB table, while Kinesis Data Streams ingests custom streaming data from many producers. DynamoDB Streams are tied directly to table changes, while Kinesis is a general-purpose real-time streaming service. Use DynamoDB Streams for database change events and Kinesis for application, IoT, clickstream, or log streams.

## Amazon ElastiCache

Amazon ElastiCache is a managed in-memory caching service supporting Redis-compatible and Memcached engines. Its main purpose is to reduce database load and improve application latency. It is used for caching, session storage, real-time leaderboards, rate limiting, and pub/sub-style workloads.

## ElastiCache security

ElastiCache security includes VPC placement, security groups, subnet groups, encryption in transit, encryption at rest, authentication, and IAM-supported management controls. Its main purpose is to protect cache access and sensitive data stored in memory. ElastiCache clusters are usually deployed in private subnets and accessed only by application resources.

## Amazon DocumentDB

Amazon DocumentDB is a managed document database service compatible with MongoDB workloads. Its main purpose is storing, querying, and scaling JSON-like document data without managing database servers. It is best when applications need document database behavior rather than relational tables or key-value access.

## Amazon Neptune

Amazon Neptune is a managed graph database service. Its main purpose is storing and querying highly connected data such as relationships, fraud networks, recommendation graphs, and knowledge graphs. It supports graph query models like property graph and RDF for relationship-heavy workloads.

## Amazon Redshift

Amazon Redshift is a managed cloud data warehouse for large-scale analytics using SQL. Its main purpose is fast querying and reporting over structured and semi-structured data, often from data lakes, operational databases, or BI tools. It is optimized for analytical workloads, not transactional application databases.

## Amazon S3 as a data store

Amazon S3 can act as a durable, scalable object data store for data lakes, backups, logs, media, and analytics datasets. Its main purpose is low-cost storage of large amounts of structured, semi-structured, or unstructured data. Unlike databases, S3 stores objects and relies on services like Athena, Glue, EMR, or Redshift Spectrum for analysis.

## AWS Lambda

AWS Lambda is a serverless compute service that runs code in response to events without managing servers. Its main purpose is to execute short-lived functions that automatically scale with demand. Lambda is commonly used for event processing, APIs, automation, and backend tasks.

## Lambda concurrency errors

Lambda concurrency errors happen when function invocations exceed available concurrency limits. Their main purpose in exam scenarios is to indicate throttling, where Lambda rejects or delays new invocations depending on the event source. Solutions may include increasing account limits, setting reserved concurrency, or controlling event source throughput.

## Reserved concurrency

Reserved concurrency guarantees a specific amount of Lambda concurrency for a function and also sets its maximum concurrency. Its main purpose is to protect critical functions while preventing one function from consuming all account concurrency. Setting reserved concurrency to zero can intentionally throttle a function.

## Provisioned concurrency

Provisioned concurrency keeps a configured number of Lambda execution environments initialized and ready to respond. Its main purpose is reducing cold start latency for latency-sensitive workloads. It is different from reserved concurrency because it focuses on pre-warming capacity, not just limiting or reserving concurrency.

## Lambda cold starts

Lambda cold starts occur when AWS initializes a new execution environment before running function code. Their main purpose as an exam topic is understanding latency during first invocation or scaling events. Cold starts can be reduced by smaller packages, efficient initialization, provisioned concurrency, or features like SnapStart for supported runtimes.

## Lambda SnapStart

Lambda SnapStart improves startup performance for supported Java Lambda functions by caching a snapshot of the initialized execution environment. Its main purpose is reducing cold start latency without manually keeping functions warm. It is useful for latency-sensitive Java serverless applications.

## Lambda@Edge

Lambda@Edge runs Lambda functions at CloudFront edge locations in response to CloudFront events. Its main purpose is customizing content delivery closer to users, such as modifying headers, redirects, or authentication logic. It is associated with CloudFront and supports globally distributed request processing.

## CloudFront Functions

CloudFront Functions are lightweight JavaScript functions that run at CloudFront edge locations for very low-latency request or response manipulation. Their main purpose is simple viewer request and viewer response logic such as header changes, redirects, or URL rewrites. They are lighter and faster than Lambda@Edge but support fewer capabilities.

## Amazon API Gateway

Amazon API Gateway is a managed service for creating, publishing, securing, and monitoring APIs. Its main purpose is to front services such as Lambda, HTTP backends, or AWS services with scalable API endpoints. It supports features like throttling, authentication, caching, stages, and usage plans.

## API Gateway endpoint types

API Gateway endpoint types define how clients reach an API: edge-optimized, Regional, or private. Edge-optimized endpoints use CloudFront for global clients, Regional endpoints are hosted in a specific Region, and private endpoints are accessible only from a VPC through interface endpoints. The choice affects latency, access scope, and architecture.

## API Gateway security

API Gateway security includes IAM authorization, Lambda authorizers, Amazon Cognito user pools, resource policies, throttling, WAF integration, and TLS. Its main purpose is to control who can call APIs and protect them from abuse. Exam questions often choose Cognito for user authentication and IAM for AWS principal authorization.

## AWS Step Functions

AWS Step Functions is a serverless workflow orchestration service for coordinating AWS services and application components. Its main purpose is to model business processes as state machines with steps, retries, branching, and error handling. It helps replace custom workflow code with managed orchestration.

## Amazon Cognito

Amazon Cognito is a managed identity service for adding user sign-up, sign-in, and access control to applications. Its main purpose is application user authentication and federation with social or enterprise identity providers. User pools handle authentication, while identity pools provide temporary AWS credentials.

## Amazon SQS

Amazon Simple Queue Service is a managed message queue for decoupling application components. Its main purpose is reliable asynchronous communication between producers and consumers. SQS helps absorb traffic spikes and lets consumers process messages at their own pace.

## SQS visibility timeout

SQS visibility timeout is the period after a consumer receives a message during which the message is hidden from other consumers. Its main purpose is to give the consumer time to process and delete the message. If the message is not deleted before the timeout ends, it becomes visible again for retry.

## SQS long polling

SQS long polling waits for messages to arrive before returning a response to the consumer. Its main purpose is to reduce empty responses, lower cost, and improve efficiency compared with short polling. It is configured by setting a wait time up to 20 seconds.

## SQS FIFO

SQS FIFO queues provide first-in-first-out message ordering and exactly-once processing behavior within message groups. Their main purpose is preserving strict order and preventing duplicates for workflows that require sequencing. They have different throughput characteristics than standard SQS queues.

## SQS security

SQS security includes IAM policies, queue policies, server-side encryption, VPC endpoints, and TLS in transit. Its main purpose is to control who can send, receive, delete, or manage queue messages. Queue policies are especially useful for cross-account access or allowing SNS to publish to SQS.

## SQS consumer autoscaling

SQS consumer autoscaling adjusts the number of workers based on queue depth or message backlog. Its main purpose is to process messages faster during spikes and reduce compute during low traffic. Common designs scale EC2, ECS, or Lambda consumers using CloudWatch metrics such as ApproximateNumberOfMessagesVisible.

## Amazon SNS

Amazon Simple Notification Service is a managed pub/sub messaging service. Its main purpose is to fan out messages from publishers to multiple subscribers such as SQS queues, Lambda functions, HTTP endpoints, email, or SMS. SNS is push-based and useful for event notifications.

## SNS security

SNS security includes IAM permissions, topic policies, encryption with KMS, TLS in transit, and VPC endpoint access for private connectivity. Its main purpose is to control who can publish or subscribe and protect notification data. Topic policies are commonly used for cross-account publishing or allowing AWS services to publish events.

## SNS + SQS fanout

SNS plus SQS fanout uses an SNS topic to publish the same message to multiple SQS queues. Its main purpose is to let multiple independent consumers process the same event reliably at their own pace. This pattern combines SNS push fanout with SQS buffering and retry behavior.

## Amazon Kinesis Data Streams

Amazon Kinesis Data Streams is a managed service for real-time streaming data ingestion and processing. Its main purpose is to collect ordered records from producers and allow multiple consumers to process them in near real time. It is used for clickstreams, logs, IoT telemetry, and real-time analytics.

## Amazon Data Firehose

Amazon Data Firehose is a managed service for delivering streaming data to destinations such as S3, Redshift, OpenSearch, and third-party services. Its main purpose is simple streaming ingestion with automatic buffering, transformation, and delivery. It is easier to operate than Kinesis Data Streams when custom stream processing is not required.

## Firehose vs Kinesis Data Streams

Kinesis Data Streams provides real-time streaming with shard-level control and custom consumers, while Data Firehose focuses on managed delivery to destinations. Data Streams is best when applications need to process records directly and control retention or consumers. Firehose is best when data should be loaded into storage or analytics services with minimal management.

## SQS vs SNS vs Kinesis

SQS is a queue for decoupling producers and consumers, SNS is pub/sub for pushing messages to multiple subscribers, and Kinesis is for real-time streaming data. SQS stores messages until consumers pull them, SNS pushes notifications, and Kinesis keeps ordered streams for processing. This distinction is common in event-driven architecture questions.

## Amazon MQ

Amazon MQ is a managed message broker service for Apache ActiveMQ and RabbitMQ. Its main purpose is migrating existing broker-based applications to AWS without rewriting them for SQS or SNS. It supports traditional messaging protocols such as JMS, AMQP, MQTT, OpenWire, and STOMP.

## Amazon EventBridge

Amazon EventBridge is a serverless event bus service for routing events from AWS services, SaaS applications, and custom applications. Its main purpose is building event-driven architectures using rules that match events and send them to targets. It helps decouple producers and consumers without managing event infrastructure.

## EventBridge rules

EventBridge rules match incoming events based on event patterns or schedules and route them to targets. Their main purpose is to trigger actions when specific events occur or on a cron-like schedule. Targets can include Lambda, Step Functions, SQS, SNS, ECS tasks, and many AWS services.

## EventBridge schema registry

EventBridge schema registry discovers, stores, and manages event schemas. Its main purpose is helping developers understand event structure and generate code bindings for event-driven applications. It is useful when many applications publish and consume structured events.

## EventBridge resource-based policies

EventBridge resource-based policies control which accounts or principals can put events onto an event bus. Their main purpose is secure cross-account event publishing. They are important in multi-account event-driven architectures using centralized or shared event buses.

## Amazon CloudFront

Amazon CloudFront is AWS’s content delivery network for caching and delivering content from edge locations worldwide. Its main purpose is reducing latency, improving performance, and protecting origins such as S3, ALB, EC2, or API Gateway. It supports HTTPS, caching controls, geo restrictions, signed URLs, and integration with WAF.

## CloudFront geo restriction

CloudFront geo restriction controls access to content based on the viewer’s country. Its main purpose is allowing or blocking content delivery for licensing, compliance, or regional access rules. It is a CloudFront distribution feature and works at the edge.

## CloudFront cache invalidation

CloudFront cache invalidation removes objects from edge caches before their normal TTL expires. Its main purpose is forcing CloudFront to fetch updated content from the origin. It helps when content changes immediately, but versioned file names are often a better long-term caching strategy.

## CloudFront with S3

CloudFront with S3 uses S3 as the origin for cached content distributed globally through CloudFront edge locations. Its main purpose is faster and more secure delivery of static assets or downloadable files. Origin Access Control can restrict direct S3 access so users must access content through CloudFront.

## CloudFront with ALB

CloudFront with ALB uses an Application Load Balancer as the origin for dynamic web applications. Its main purpose is improving global performance, TLS handling, caching, and security for HTTP and HTTPS workloads. CloudFront can also integrate with WAF to protect traffic before it reaches the ALB.

## AWS Global Accelerator

AWS Global Accelerator is a networking service that improves availability and performance using static anycast IP addresses and the AWS global network. Its main purpose is routing user traffic to healthy application endpoints in optimal AWS Regions. It works well for TCP or UDP applications that need stable IPs and fast failover.

## Global Accelerator vs CloudFront

Global Accelerator improves network routing for TCP and UDP applications using static anycast IPs, while CloudFront caches HTTP and HTTPS content at edge locations. CloudFront is best for content delivery and web caching, while Global Accelerator is best for non-cacheable traffic and multi-Region application acceleration. Both use AWS edge locations but solve different problems.

## Route 53 vs Global Accelerator vs CloudFront

Route 53 provides DNS resolution and routing policies, Global Accelerator provides static anycast IPs with optimized network routing, and CloudFront provides edge caching and content delivery. Route 53 answers where to send traffic, Global Accelerator improves how traffic reaches application endpoints, and CloudFront caches and serves content near users. Exam questions often distinguish DNS control, network acceleration, and CDN caching.

## AWS Container Management

AWS container management refers to services for running, storing, orchestrating, and scaling containerized applications. Its main purpose is to package applications consistently and run them on managed infrastructure. Key services include ECS, EKS, Fargate, ECR, App Runner, and load balancer integrations.

## Amazon ECS

Amazon Elastic Container Service is AWS’s managed container orchestration service. Its main purpose is running Docker containers on EC2 instances or serverless Fargate capacity without managing a separate Kubernetes control plane. ECS manages task scheduling, services, scaling, and integration with IAM and load balancers.

## ECS EC2 launch type

ECS EC2 launch type runs containers on EC2 instances that you manage as the cluster capacity. Its main purpose is giving more control over instance types, AMIs, networking, and host-level configuration. You are responsible for scaling, patching, and managing the EC2 container instances.

## ECS Fargate launch type

ECS Fargate launch type runs containers without managing EC2 instances. Its main purpose is serverless container compute where AWS manages the underlying capacity. It is best when you want to focus on containers and tasks instead of servers.

## ECS IAM roles

ECS uses IAM roles to grant permissions to containers and ECS infrastructure. Task roles give application containers permissions to call AWS services, while task execution roles let ECS pull images and write logs. This separation helps follow least privilege for containerized applications.

## ECS load balancer integration

ECS integrates with Elastic Load Balancing to route traffic to running container tasks. Its main purpose is highly available service access while tasks scale or move across instances and Availability Zones. ALB is commonly used for HTTP services, while NLB is used for high-performance TCP or static IP needs.

## ECS data volumes with EFS

ECS can mount Amazon EFS file systems into containers for shared persistent storage. Its main purpose is allowing multiple ECS tasks to access the same files across instances or Availability Zones. This is useful when containerized applications need durable shared file storage.

## ECS Auto Scaling

ECS Auto Scaling adjusts the number of running tasks or underlying capacity based on demand. Its main purpose is maintaining application performance while controlling cost. ECS services commonly scale using CloudWatch metrics such as CPU, memory, request count, or custom metrics.

## Amazon ECR

Amazon Elastic Container Registry is a managed container image registry. Its main purpose is storing, scanning, and managing Docker and OCI images for ECS, EKS, Lambda, and other container platforms. ECR integrates with IAM for access control and supports private repositories.

## Amazon EKS

Amazon Elastic Kubernetes Service is AWS’s managed Kubernetes service. Its main purpose is running Kubernetes workloads while AWS manages the control plane. EKS is useful when teams need Kubernetes APIs, ecosystem compatibility, and portability.

## EKS node types

EKS node types define where Kubernetes pods run, such as managed node groups, self-managed EC2 nodes, and Fargate profiles. Their main purpose is choosing the right balance of control, management effort, and serverless operation. Managed node groups reduce EC2 management, while Fargate removes node management for supported pod workloads.

## EKS data volumes

EKS data volumes provide persistent storage for Kubernetes workloads using integrations such as EBS CSI, EFS CSI, and FSx CSI drivers. Their main purpose is giving pods durable block or file storage. EBS is typically for single-node block storage, while EFS supports shared file access across pods.

## AWS App Runner

AWS App Runner is a managed service for running containerized web applications and APIs directly from source code or container images. Its main purpose is simplified deployment, scaling, load balancing, and HTTPS without managing servers or orchestrators. It is easier than ECS or EKS for straightforward web services.

## AWS App2Container

AWS App2Container is a migration tool that helps containerize existing applications running on servers. Its main purpose is analyzing applications and generating container artifacts for deployment to ECS or EKS. It helps modernize legacy applications without manually creating all container configuration from scratch.

## Amazon CloudWatch metrics

CloudWatch metrics are time-series data points that measure AWS resource and application performance. Their main purpose is monitoring values such as CPU utilization, latency, request count, disk activity, and custom application metrics. Metrics support dashboards, alarms, and automated scaling decisions.

## CloudWatch alarms

CloudWatch alarms watch metrics and trigger actions when thresholds are breached. Their main purpose is alerting or automation based on resource and application health. Alarms can notify SNS topics, trigger Auto Scaling actions, or support operational responses.

## CloudWatch logs

CloudWatch Logs is a managed service for collecting, storing, searching, and monitoring log data. Its main purpose is centralized logging for AWS services, applications, and custom systems. Logs are organized into log groups and log streams.

## CloudWatch Logs Insights

CloudWatch Logs Insights is an interactive query tool for analyzing CloudWatch Logs. Its main purpose is searching, filtering, aggregating, and visualizing log data without exporting it first. It is useful for troubleshooting application errors and operational events.

## CloudWatch Logs S3 export

CloudWatch Logs S3 export moves log data from CloudWatch Logs to Amazon S3. Its main purpose is long-term retention, analytics, compliance archiving, or cost optimization. Exports are useful when logs need to be analyzed with Athena, Glue, or other S3-based tools.

## CloudWatch Logs subscriptions

CloudWatch Logs subscriptions stream log events from CloudWatch Logs to destinations such as Lambda, Kinesis Data Streams, or Firehose. Their main purpose is near real-time log processing, filtering, and forwarding. They help build centralized logging or security analytics pipelines.

## CloudWatch Logs aggregation across accounts and Regions

CloudWatch Logs aggregation across accounts and Regions centralizes log collection from multiple AWS environments. Its main purpose is unified monitoring, security analysis, and operational visibility. This is commonly done with subscription filters, cross-account destinations, or organization-level logging patterns.

## CloudWatch logs for EC2

CloudWatch logs for EC2 require the CloudWatch Agent to collect operating system and application logs from instances. Their main purpose is centralized visibility into logs that EC2 does not send automatically. The agent can also collect additional system-level metrics such as memory and disk usage.

## CloudWatch Container Insights

CloudWatch Container Insights collects metrics and logs from containerized applications on ECS, EKS, and Kubernetes. Its main purpose is monitoring cluster, node, pod, task, and container performance. It helps troubleshoot container resource usage and application health.

## CloudWatch Lambda Insights

CloudWatch Lambda Insights provides enhanced monitoring for Lambda functions. Its main purpose is collecting performance metrics, logs, and diagnostic information such as memory usage, CPU time, and cold starts. It helps troubleshoot serverless application behavior beyond basic invocation metrics.

## CloudWatch Contributor Insights

CloudWatch Contributor Insights analyzes time-series log data to identify top contributors to operational issues. Its main purpose is finding patterns such as which IPs, users, or resources contribute most to errors or traffic. It is useful for detecting heavy hitters and unusual behavior.

## CloudWatch Application Insights

CloudWatch Application Insights helps monitor applications by detecting problems and setting up observability for supported resources. Its main purpose is automated application-level health monitoring and troubleshooting. It can group related telemetry and surface likely causes of issues.

## CloudWatch Network Synthetic Monitor

CloudWatch Network Synthetic Monitor monitors network performance between AWS and on-premises or internet endpoints. Its main purpose is identifying latency and packet loss issues in hybrid or distributed networks. It helps troubleshoot network paths beyond basic resource metrics.

## AWS CloudTrail

AWS CloudTrail records AWS account activity and API calls. Its main purpose is governance, auditing, security analysis, and operational troubleshooting. It answers who did what, when, from where, and against which AWS resource.

## CloudTrail events

CloudTrail events are records of API activity in an AWS account. Management events track control plane actions such as creating buckets or launching instances, while data events track resource-level activity such as S3 object access or Lambda invocation. They help audit both administrative and data access actions.

## CloudTrail Insights

CloudTrail Insights detects unusual API activity patterns in an AWS account. Its main purpose is identifying anomalies such as spikes in resource provisioning or unusual management API calls. It helps detect operational or security issues that differ from normal behavior.

## CloudTrail event retention

CloudTrail event retention refers to how long CloudTrail keeps event history and where logs are stored for long-term access. Event history provides a limited recent view, while trails can deliver logs to S3 for longer retention. Its main purpose is audit readiness and compliance over time.

## AWS Config

AWS Config records and evaluates resource configurations over time. Its main purpose is compliance tracking, configuration history, and change auditing. It helps answer how a resource was configured and whether it follows required rules.

## AWS Config rules

AWS Config rules evaluate resource configurations against desired settings. Their main purpose is compliance detection, such as identifying unencrypted volumes or publicly accessible buckets. Rules can be AWS managed or custom.

## AWS Config resources

AWS Config resources are the AWS resource types whose configuration details are recorded and tracked. Their main purpose is maintaining inventory, history, and relationship information for supported resources. This helps investigate changes and compliance across an account or organization.

## AWS Config remediations

AWS Config remediations automatically correct noncompliant resources using predefined or custom actions. Their main purpose is reducing manual work after Config rules detect violations. Remediation commonly uses Systems Manager Automation documents.

## AWS Config notifications

AWS Config notifications alert users or systems when configuration changes or compliance changes occur. Their main purpose is timely visibility into drift or violations. Notifications commonly integrate with Amazon SNS and EventBridge.

## CloudWatch vs CloudTrail vs Config

CloudWatch monitors performance metrics, logs, and alarms; CloudTrail records API activity; and AWS Config tracks resource configuration and compliance. CloudWatch answers how resources are behaving, CloudTrail answers who made API calls, and Config answers what changed in resource configuration. This distinction is heavily tested on the SAA exam.

## AWS Trusted Advisor

AWS Trusted Advisor analyzes AWS accounts and provides recommendations across cost optimization, performance, security, fault tolerance, service limits, and operational excellence. Its main purpose is account-level best practice guidance. The available checks depend on the AWS support plan.

## AWS Well-Architected Tool

AWS Well-Architected Tool helps review workloads against AWS best practices across pillars such as operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability. Its main purpose is structured architecture assessment and improvement planning. It is not a monitoring service but a review and guidance tool.

## RPO and RTO

Recovery Point Objective, or RPO, is the maximum acceptable amount of data loss measured in time. Recovery Time Objective, or RTO, is the maximum acceptable time to restore service after an outage. These metrics guide disaster recovery strategy selection and cost.

## Backup and restore

Backup and restore is a disaster recovery strategy where data is backed up and infrastructure is recreated after a failure. Its main purpose is low-cost recovery for workloads that can tolerate longer RTO. It usually has slower recovery than pilot light, warm standby, or multi-site designs.

## Pilot light

Pilot light is a disaster recovery strategy where only the most critical core components run in the recovery environment. Its main purpose is lower cost than warm standby while allowing faster recovery than backup and restore. During disaster, additional resources are scaled up and applications are fully restored.

## Warm standby

Warm standby is a disaster recovery strategy where a scaled-down but functional version of the application runs in another environment. Its main purpose is faster recovery than pilot light because the full stack is already running. During disaster, capacity is scaled up to handle production traffic.

## Multi-site / hot site

Multi-site, or hot site, is a disaster recovery strategy where full production workloads run in multiple locations at the same time. Its main purpose is very low RTO and often low RPO. It is the most expensive common DR option because resources are always active.

## AWS Elastic Disaster Recovery

AWS Elastic Disaster Recovery is a managed service for replicating servers to AWS for fast recovery after outages. Its main purpose is minimizing downtime and data loss for physical, virtual, or cloud-based servers. It uses continuous block-level replication and can launch recovery instances in AWS.

## AWS Backup

AWS Backup is a managed service for centralized backup policies across AWS services. Its main purpose is automating backup scheduling, retention, lifecycle, and cross-account or cross-Region backup management. It supports services such as EBS, RDS, DynamoDB, EFS, FSx, and Storage Gateway.

## AWS Application Migration Service

AWS Application Migration Service helps migrate applications to AWS by replicating source servers and launching them as EC2 instances. Its main purpose is lift-and-shift migration with minimal downtime. It is commonly used to move physical, virtual, or cloud servers into AWS.

## AWS DMS

AWS Database Migration Service helps migrate databases to AWS with minimal downtime. Its main purpose is moving data between homogeneous or heterogeneous database engines while keeping source databases running during migration. It supports full load and ongoing replication using change data capture.

## On-premises strategy with AWS

On-premises strategy with AWS means designing hybrid architectures that connect existing data centers to AWS services. Its main purpose is supporting gradual migration, low-latency local systems, compliance needs, or legacy applications. Common services include VPN, Direct Connect, Storage Gateway, Outposts, DataSync, and DMS.

## VMware Cloud on AWS

VMware Cloud on AWS runs VMware software-defined data center environments on AWS infrastructure. Its main purpose is migrating or extending VMware workloads to AWS without immediately refactoring applications. It is useful for organizations already standardized on VMware tools and operations.

## EC2 cost optimization

EC2 cost optimization means reducing compute cost by matching capacity and pricing models to workload needs. Its main purpose is avoiding overprovisioning and using options such as right-sizing, Auto Scaling, Savings Plans, Reserved Instances, and Spot Instances. Exam questions often focus on predictable versus interruptible workloads.

## S3 cost optimization

S3 cost optimization means reducing object storage cost by choosing appropriate storage classes and lifecycle policies. Its main purpose is moving infrequently accessed or archive data to lower-cost classes while meeting retrieval needs. S3 Intelligent-Tiering is useful when access patterns are unknown.

## EBS cost optimization

EBS cost optimization means choosing the right volume type, size, IOPS, throughput, and snapshot retention. Its main purpose is avoiding overprovisioned block storage and unused volumes. Common actions include using gp3, deleting unattached volumes, and managing old snapshots.

## EFS cost optimization

EFS cost optimization means using lifecycle management, Infrequent Access or Archive classes, and the right throughput mode. Its main purpose is reducing cost for shared file data that is not frequently accessed. One Zone storage may reduce cost when multi-AZ resilience is not required.

## CloudFront caching for cost optimization

CloudFront caching reduces cost by serving repeated requests from edge locations instead of repeatedly fetching from the origin. Its main purpose is lowering origin load, data transfer, and latency for web content. Proper TTLs, cache keys, and object versioning improve both performance and cost.

## NAT Gateway cost awareness

NAT Gateway cost awareness means understanding that NAT Gateways charge for hourly usage and data processing. Its main purpose is avoiding unnecessary routing of large traffic volumes through NAT. VPC endpoints, per-AZ NAT design, or private service access can reduce cost and improve architecture.

## VPC endpoint cost awareness

VPC endpoint cost awareness means understanding cost tradeoffs between gateway endpoints, interface endpoints, NAT Gateway traffic, and data transfer. Its main purpose is choosing secure private connectivity without unexpected charges. Gateway endpoints for S3 and DynamoDB have different pricing behavior than interface endpoints powered by PrivateLink.

## AWS Cost Explorer

AWS Cost Explorer is a cost analysis tool for viewing and forecasting AWS spending and usage. Its main purpose is identifying cost trends by service, account, tag, Region, or usage type. It helps with financial visibility but does not enforce spending limits by itself.

## AWS Cost Anomaly Detection

AWS Cost Anomaly Detection uses machine learning to identify unusual AWS spending patterns. Its main purpose is alerting when costs deviate from normal behavior. It helps detect unexpected usage, misconfigurations, or sudden spikes before they become large bills.

## AWS Budgets concept

AWS Budgets lets you set custom cost, usage, reservation, or Savings Plans thresholds and receive alerts. Its main purpose is proactive financial monitoring against defined limits. Budgets notify you when thresholds are exceeded or forecasted to be exceeded, but they do not automatically stop most AWS usage by default.

## AWS Compute Optimizer concept

AWS Compute Optimizer analyzes resource utilization and recommends better configurations for compute resources. Its main purpose is right-sizing and performance improvement for resources such as EC2, Auto Scaling groups, EBS volumes, Lambda, and ECS services. It helps reduce cost and improve efficiency using usage metrics.

## AWS Athena

Amazon Athena is a serverless interactive query service for analyzing data in Amazon S3 using SQL. Its main purpose is querying data lakes without managing servers or loading data into a database. It works with schemas from AWS Glue Data Catalog and charges based on data scanned.

## Amazon OpenSearch

Amazon OpenSearch Service is a managed service for search, log analytics, and observability workloads. Its main purpose is indexing and querying large volumes of text, logs, metrics, or application data. It is commonly used for full-text search and operational analytics dashboards.

## Amazon EMR

Amazon EMR is a managed big data platform for running frameworks such as Apache Spark, Hadoop, Hive, and Presto. Its main purpose is processing large datasets for analytics, ETL, and machine learning pipelines. EMR can run on EC2, EKS, or serverless options depending on workload needs.

## AWS QuickSight

Amazon QuickSight is a managed business intelligence service for dashboards, reports, and data visualization. Its main purpose is helping users analyze data from AWS and external sources without managing BI servers. It integrates with services such as Athena, Redshift, S3, and RDS.

## AWS Glue

AWS Glue is a serverless data integration and ETL service. Its main purpose is discovering, cataloging, transforming, and preparing data for analytics. Glue includes crawlers, jobs, and the Glue Data Catalog used by services like Athena and EMR.

## Lake Formation

AWS Lake Formation helps build, secure, and manage data lakes on AWS. Its main purpose is centralizing permissions, cataloging, and governance for data stored mainly in Amazon S3. It simplifies data lake setup and fine-grained access control.

## Amazon Managed Service for Apache Flink

Amazon Managed Service for Apache Flink is a managed service for processing streaming data using Apache Flink. Its main purpose is real-time analytics and stateful stream processing without managing Flink infrastructure. It is used with sources such as Kinesis Data Streams, MSK, and other streaming systems.

## Amazon Managed Streaming for Apache Kafka

Amazon Managed Streaming for Apache Kafka, or MSK, is a managed service for running Apache Kafka clusters. Its main purpose is streaming event ingestion and messaging using Kafka-compatible tools and APIs. It reduces operational work for teams that need Kafka rather than Kinesis or SQS.

## Big data ingestion pipeline

A big data ingestion pipeline collects, moves, processes, and stores large volumes of data for analytics. Its main purpose is turning raw data from applications, logs, IoT, or streams into usable data in services like S3, Redshift, or OpenSearch. Common AWS building blocks include Kinesis, Firehose, Glue, Lambda, S3, and Athena.

## Amazon Rekognition

Amazon Rekognition is a managed machine learning service for image and video analysis. Its main purpose is detecting objects, faces, labels, text, unsafe content, and activities in visual media. It helps add computer vision features without building custom ML models.

## Amazon Transcribe

Amazon Transcribe is a managed speech-to-text service. Its main purpose is converting audio into written text for captions, call analytics, search, or transcription workflows. It supports features such as speaker identification and custom vocabulary.

## Amazon Polly

Amazon Polly is a managed text-to-speech service. Its main purpose is turning written text into natural-sounding speech. It is useful for voice applications, accessibility, automated announcements, and content narration.

## Amazon Translate

Amazon Translate is a managed neural machine translation service. Its main purpose is translating text between languages for applications and content workflows. It helps add multilingual support without managing translation models.

## Amazon Lex

Amazon Lex is a managed service for building conversational interfaces using voice and text. Its main purpose is creating chatbots and virtual agents with automatic speech recognition and natural language understanding. It uses similar conversational technology concepts to Amazon Alexa.

## Amazon Comprehend

Amazon Comprehend is a managed natural language processing service for analyzing text. Its main purpose is detecting sentiment, key phrases, entities, language, topics, and syntax. It helps applications understand unstructured text without custom NLP models.

## Amazon Comprehend Medical

Amazon Comprehend Medical is a managed NLP service specialized for healthcare and medical text. Its main purpose is extracting medical information such as conditions, medications, anatomy, tests, and protected health information from clinical documents. It is distinct from Amazon Comprehend because it is trained for medical terminology.

## Amazon SageMaker

Amazon SageMaker is a managed machine learning platform for building, training, deploying, and managing ML models. Its main purpose is supporting the full ML lifecycle without manually assembling all infrastructure. It is broader than AI services like Rekognition or Translate, which provide prebuilt capabilities.

## Amazon Kendra

Amazon Kendra is a managed intelligent enterprise search service. Its main purpose is using machine learning to search across documents, knowledge bases, and business data sources. It helps users find answers from unstructured organizational content.

## Amazon Textract

Amazon Textract is a managed machine learning service that extracts text, handwriting, forms, and tables from scanned documents. Its main purpose is document processing beyond basic OCR. It helps automate workflows involving invoices, forms, receipts, and PDFs.

## AWS CloudFormation

AWS CloudFormation is an infrastructure as code service for defining and provisioning AWS resources using templates. Its main purpose is repeatable, version-controlled deployment of infrastructure stacks. It helps avoid manual console configuration and supports consistent environments.

## Amazon SES

Amazon Simple Email Service is a managed email sending and receiving service. Its main purpose is sending transactional, notification, or marketing email from applications. It is commonly used for high-scale email delivery but requires proper domain verification and reputation management.

## Amazon Pinpoint

Amazon Pinpoint is a managed customer engagement service for targeted messaging campaigns. Its main purpose is sending personalized communications across channels such as email, SMS, push notifications, and voice. It is more campaign- and audience-focused than SES.

## AWS Systems Manager

AWS Systems Manager is a management service for operating AWS and hybrid resources at scale. Its main purpose is centralized operational tasks such as patching, command execution, inventory, parameter storage, automation, and session access. It helps manage EC2 instances and on-premises servers without relying only on SSH or RDP.

## AWS Outposts

AWS Outposts extends AWS infrastructure and services to on-premises locations. Its main purpose is running AWS-managed compute and storage locally when workloads need low latency, local data processing, or data residency. It provides a consistent AWS experience outside AWS Regions.

## AWS Batch

AWS Batch is a managed service for running batch computing jobs at scale. Its main purpose is scheduling jobs, provisioning compute, and managing queues for workloads such as simulations, data processing, and rendering. It can use EC2, Spot Instances, and Fargate depending on job requirements.

## AWS AppFlow

AWS AppFlow is a managed integration service for transferring data between SaaS applications and AWS services. Its main purpose is no-code or low-code data flows between services such as Salesforce, SAP, Google Analytics, S3, and Redshift. It helps automate secure data movement without custom integration code.

## AWS Amplify

AWS Amplify is a set of tools and managed services for building full-stack web and mobile applications. Its main purpose is simplifying frontend hosting, authentication, APIs, storage, and CI/CD for application developers. It is commonly used with services such as Cognito, AppSync, Lambda, and S3.

## AWS Instance Scheduler

AWS Instance Scheduler is an AWS solution that automatically starts and stops EC2 and RDS instances based on schedules. Its main purpose is reducing cost for non-production workloads that do not need to run continuously. It uses automation to align instance uptime with business hours or planned usage.