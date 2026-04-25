## AWS Amplify

AWS Amplify is a managed development platform for building and hosting full-stack web and mobile applications on AWS. It helps developers connect frontend apps to backend features such as authentication, APIs, storage, and hosting without manually managing each service. For the exam, recognize Amplify as a fast way to deploy modern web or mobile apps with managed backend integration.

## AWS API Gateway

AWS API Gateway is a fully managed service for creating, publishing, securing, and scaling APIs. It acts as the front door for applications that expose REST, HTTP, or WebSocket APIs to clients. For the exam, choose API Gateway when you need a managed API layer in front of services like Lambda, ECS, or backend applications.

## AWS App Runner

AWS App Runner is a fully managed compute service for running containerized web applications and APIs. It automatically handles deployment, scaling, load balancing, and HTTPS without requiring server or container orchestration management. For the exam, identify App Runner as a simple way to run web apps from source code or container images.

## AWS App2Container

AWS App2Container is a modernization tool that helps convert existing Java and .NET applications into containers. It analyzes applications, creates container images, and generates deployment artifacts for services like Amazon ECS or Amazon EKS. For the exam, associate App2Container with containerizing legacy applications for AWS.

## AWS AppFlow

AWS AppFlow is a fully managed integration service for securely transferring data between SaaS applications and AWS services. It can move data from applications like Salesforce or SAP into services such as Amazon S3 or Amazon Redshift. For the exam, choose AppFlow when you need no-code or low-code SaaS-to-AWS data integration.

## AWS Application Migration Service (MGN)

AWS Application Migration Service is used for lift-and-shift migration of servers to AWS. It continuously replicates source servers and launches them as EC2 instances with minimal downtime during cutover. For the exam, choose MGN when migrating physical, virtual, or cloud servers into AWS.

## AWS Batch

AWS Batch is a managed service for running batch processing jobs at scale. It automatically provisions and manages compute resources such as EC2, Spot Instances, or Fargate based on job requirements. For the exam, choose AWS Batch for queued jobs, scientific workloads, image processing, or large-scale background processing.

## AWS Backup

AWS Backup is a centralized managed service for automating backups across AWS services. It supports backup policies, retention rules, and compliance management for services like EBS, RDS, DynamoDB, EFS, and Storage Gateway. For the exam, choose AWS Backup when you need centralized backup management across multiple AWS resources.

## AWS Certificate Manager (ACM)

AWS Certificate Manager is a managed service for provisioning, managing, and renewing SSL/TLS certificates. It integrates with services like Elastic Load Balancing, CloudFront, and API Gateway to enable HTTPS. For the exam, choose ACM when you need managed certificates without manual renewal.

## AWS CloudFormation

AWS CloudFormation is an infrastructure as code service for provisioning AWS resources using templates. It lets you create, update, and delete related resources as stacks in a repeatable way. For the exam, choose CloudFormation when you need automated, version-controlled infrastructure deployment.

## AWS CloudHSM

AWS CloudHSM provides dedicated hardware security modules in AWS for cryptographic key storage and operations. It gives customers direct control over keys and HSM access for strict compliance requirements. For the exam, distinguish CloudHSM from KMS by remembering that CloudHSM uses dedicated customer-controlled hardware.

## AWS CloudTrail

AWS CloudTrail records AWS account activity and API calls. It helps with auditing, governance, compliance, and security investigations by showing who did what, when, and from where. For the exam, choose CloudTrail when you need API activity history or user action tracking.

## AWS Config

AWS Config records configuration changes for AWS resources and evaluates them against compliance rules. It helps answer questions about resource history, relationships, and whether resources meet required standards. For the exam, choose Config when you need configuration tracking and compliance evaluation.

## AWS Control Tower

AWS Control Tower is a managed service for setting up and governing a multi-account AWS environment. It creates a landing zone using AWS Organizations, guardrails, and account provisioning best practices. For the exam, choose Control Tower when you need a governed multi-account setup quickly.

## AWS Cost Anomaly Detection

AWS Cost Anomaly Detection uses machine learning to identify unusual AWS spending patterns. It alerts users when costs unexpectedly increase because of abnormal usage, misconfiguration, or unexpected activity. For the exam, choose it when the goal is automatic detection of unexpected cost spikes.

## AWS Cost Explorer

AWS Cost Explorer is a cost analysis tool for visualizing and forecasting AWS spending and usage. It helps break down costs by service, account, region, tag, or time period. For the exam, choose Cost Explorer when you need to analyze historical cost trends and usage patterns.

## AWS DataSync

AWS DataSync is a managed data transfer service for moving large amounts of data between on-premises storage and AWS or between AWS storage services. It supports services such as Amazon S3, Amazon EFS, and Amazon FSx. For the exam, choose DataSync for online, automated, high-speed file or object data transfers.

## AWS Database Migration Service (DMS)

AWS Database Migration Service is a managed service for migrating databases to AWS with minimal downtime. It supports both homogeneous migrations, such as Oracle to Oracle, and heterogeneous migrations, such as Oracle to Aurora. For the exam, choose DMS when you need database migration or continuous database replication.

## AWS Direct Connect

AWS Direct Connect provides a dedicated private network connection between an on-premises environment and AWS. It offers more consistent bandwidth and lower latency than using the public internet. For the exam, choose Direct Connect for hybrid architectures that require private, predictable connectivity to AWS.

## AWS Directory Service

AWS Directory Service provides managed directory options, including AWS Managed Microsoft Active Directory. It helps AWS workloads use directory-based authentication, domain joining, and integration with existing Active Directory environments. For the exam, choose Directory Service when applications need Microsoft AD or LDAP-style directory integration.

## AWS Elastic Beanstalk

AWS Elastic Beanstalk is a managed platform for deploying and running web applications. Developers upload code, and Elastic Beanstalk provisions resources such as EC2 instances, load balancers, Auto Scaling, and monitoring. For the exam, choose it when you want simple application deployment while still retaining access to the underlying infrastructure.

## AWS Elastic Disaster Recovery (DRS)

AWS Elastic Disaster Recovery is a managed disaster recovery service that continuously replicates servers into AWS. It helps quickly launch recovery instances in AWS during outages or disasters. For the exam, choose DRS when the goal is ongoing disaster recovery and failover readiness.

## AWS Fargate

AWS Fargate is a serverless compute engine for running containers with Amazon ECS or Amazon EKS. It removes the need to provision, patch, or manage EC2 worker nodes. For the exam, choose Fargate when you need containers without managing the underlying servers.

## AWS Firewall Manager

AWS Firewall Manager is a centralized security management service for firewall rules across multiple AWS accounts. It works with AWS Organizations and can manage AWS WAF, Shield Advanced, security groups, and Network Firewall policies. For the exam, choose Firewall Manager when you need consistent security policies across many accounts.

## AWS Global Accelerator

AWS Global Accelerator improves application availability and performance using static anycast IP addresses and the AWS global network. It routes users to healthy regional endpoints such as load balancers or EC2 instances. For the exam, choose Global Accelerator for low-latency global traffic routing and regional failover.

## AWS Glue

AWS Glue is a serverless data integration and ETL service. It discovers, catalogs, transforms, and prepares data for analytics using services such as S3, Athena, Redshift, and EMR. For the exam, recognize Glue as the managed ETL service and metadata catalog for analytics workloads.

## AWS Identity and Access Management (IAM)

AWS IAM is the core AWS security service for controlling access to AWS resources. It uses users, groups, roles, and policies to define who can perform specific actions on specific resources. For the exam, choose IAM for least-privilege permissions and access control inside AWS accounts.

## AWS IAM Identity Center

AWS IAM Identity Center provides centralized workforce access to multiple AWS accounts and cloud applications. It supports single sign-on and can integrate with external identity providers like Microsoft Entra ID or other SAML-based providers. For the exam, choose IAM Identity Center for managing human access across many AWS accounts.

## AWS KMS

AWS Key Management Service is a managed service for creating and controlling encryption keys. It integrates with many AWS services to encrypt data at rest and supports key policies, automatic rotation, and audit integration with CloudTrail. For the exam, choose KMS when you need managed encryption keys for AWS services.

## AWS Lake Formation

AWS Lake Formation is a managed service for building, securing, and managing data lakes on AWS. It simplifies permissions, data cataloging, and governance for data stored in services like Amazon S3. For the exam, choose Lake Formation when you need centralized security and governance for a data lake.

## AWS Keyspaces 

Amazon Keyspaces is a fully managed, serverless Apache Cassandra–compatible database service for running scalable NoSQL workloads. Applications use Cassandra Query Language (CQL) to read and write data, while AWS handles provisioning, scaling, and replication automatically. For the exam, choose Keyspaces when you need a Cassandra-compatible database without managing clusters, especially for high-throughput, distributed applications.

## AWS Network Firewall

AWS Network Firewall is a managed firewall service for protecting traffic inside Amazon VPCs. It supports stateful inspection, domain filtering, intrusion prevention, and centralized network traffic controls. For the exam, choose Network Firewall when you need managed network-layer firewall protection for VPC traffic.

## AWS Organizations

AWS Organizations is an account management service for centrally managing multiple AWS accounts. It supports organizational units, consolidated billing, and service control policies. For the exam, choose Organizations when you need multi-account management and centralized governance.

## AWS Outposts

AWS Outposts extends AWS infrastructure and services to on-premises locations. It is used when workloads need low latency to local systems or must meet data residency requirements while using AWS-managed hardware. For the exam, choose Outposts for hybrid architectures that require AWS services running on-premises.

## AWS Secrets Manager

AWS Secrets Manager is a managed service for storing, retrieving, and rotating sensitive secrets. It is commonly used for database credentials, API keys, and application secrets. For the exam, choose Secrets Manager when you need managed secret storage with automatic rotation support.

## AWS Shield

AWS Shield is a managed DDoS protection service for AWS applications. Shield Standard is automatically included, while Shield Advanced provides enhanced protections, visibility, and cost protection for larger attacks. For the exam, choose Shield when the focus is protection against distributed denial-of-service attacks.

## AWS Site-to-Site VPN

AWS Site-to-Site VPN creates an encrypted IPsec tunnel between an on-premises network and AWS. It is commonly used for hybrid connectivity over the public internet. For the exam, choose Site-to-Site VPN when you need secure connectivity to a VPC without a dedicated physical connection.

## AWS Snowball

AWS Snowball is a physical data transfer device used to move large amounts of data into or out of AWS. It is useful when network transfer would be too slow, expensive, or unreliable. For the exam, choose Snowball for offline bulk data migration at terabyte or petabyte scale.

## AWS Step Functions

AWS Step Functions is a serverless workflow orchestration service. It coordinates multiple AWS services, such as Lambda, ECS, SNS, and SQS, into visual workflows with retries, branching, and error handling. For the exam, choose Step Functions when you need to manage multi-step application workflows.

## AWS Storage Gateway

AWS Storage Gateway is a hybrid cloud storage service that connects on-premises environments to AWS storage. It provides file, volume, and tape gateway options backed by services such as Amazon S3 and Glacier. For the exam, choose Storage Gateway when on-premises applications need access to cloud-backed storage.

## AWS Systems Manager

AWS Systems Manager is an operations management service for managing AWS and hybrid resources. It supports patching, automation, inventory, remote command execution, and secure instance access through Session Manager. For the exam, choose Systems Manager for centralized operational control of servers and resources.

## AWS Systems Manager Parameter Store

Systems Manager Parameter Store is a managed service for storing configuration values and secrets as parameters. It supports plain text and encrypted values using AWS KMS. For the exam, choose Parameter Store for application configuration data or simple secret storage.

## AWS Transfer Family

AWS Transfer Family provides managed file transfer endpoints for protocols such as SFTP, FTPS, and FTP. It stores transferred files in Amazon S3 or Amazon EFS without requiring users to manage file transfer servers. For the exam, choose Transfer Family when external users or applications need standard file transfer access to AWS storage.

## AWS Transit Gateway

AWS Transit Gateway is a networking service that acts as a central hub for connecting VPCs and on-premises networks. It simplifies routing compared to many individual VPC peering or VPN connections. For the exam, choose Transit Gateway for scalable hub-and-spoke network connectivity.

## AWS Trusted Advisor

AWS Trusted Advisor provides recommendations to help optimize AWS environments. It checks areas such as cost optimization, performance, security, fault tolerance, and service limits. For the exam, choose Trusted Advisor when you need AWS best-practice recommendations for an account.

## AWS Virtual Private Cloud (VPC)

Amazon VPC is a networking service that lets you create isolated virtual networks in AWS. It includes subnets, route tables, internet gateways, NAT gateways, security groups, and network ACLs. For the exam, recognize VPC as the foundation for controlling network isolation and connectivity in AWS.

## AWS WAF

AWS WAF is a web application firewall that protects web applications from common web exploits. It can filter HTTP and HTTPS requests using rules for IP addresses, headers, SQL injection, cross-site scripting, and rate limits. For the exam, choose WAF when protecting CloudFront, Application Load Balancer, API Gateway, or AppSync from web-layer attacks.

## AWS Well-Architected Tool

AWS Well-Architected Tool helps review workloads against AWS best practices. It evaluates architecture using pillars such as operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability. For the exam, choose it when assessing whether a workload follows AWS architecture best practices.

## Amazon Athena

Amazon Athena is a serverless query service for analyzing data in Amazon S3 using SQL. It does not require managing servers or loading data into a database. For the exam, choose Athena when you need ad hoc SQL queries directly against data stored in S3.

## Amazon Aurora

Amazon Aurora is a managed relational database engine compatible with MySQL and PostgreSQL. It is designed for high performance, automatic storage scaling, replication, and high availability across multiple Availability Zones. For the exam, choose Aurora when you need a cloud-optimized relational database with better scalability than standard engines.

## Amazon CloudFront

Amazon CloudFront is a content delivery network that caches content at edge locations around the world. It improves performance and reduces latency for websites, APIs, videos, and static or dynamic content. For the exam, choose CloudFront when global users need faster access to content.

## Amazon CloudWatch

Amazon CloudWatch is a monitoring and observability service for AWS resources and applications. It collects metrics, logs, alarms, dashboards, and events to help detect and respond to operational issues. For the exam, choose CloudWatch when you need performance monitoring, alarms, or centralized logs.

## Amazon Cognito

Amazon Cognito provides managed authentication, authorization, and user management for web and mobile applications. It supports user sign-up, sign-in, social identity providers, and federated access. For the exam, choose Cognito when an application needs customer identity management.

## Amazon Comprehend

Amazon Comprehend is a managed natural language processing service for analyzing text. It can detect sentiment, key phrases, entities, language, and topics from unstructured text. For the exam, choose Comprehend when you need machine learning-based text analysis without building your own model.

## Amazon Comprehend Medical

Amazon Comprehend Medical is a managed natural language processing service for extracting medical information from healthcare text. It can identify items such as medical conditions, medications, procedures, and protected health information. For the exam, distinguish it from Comprehend by remembering it is specialized for clinical and healthcare language.

## Amazon DocumentDB

Amazon DocumentDB is a managed document database service compatible with MongoDB workloads. It stores JSON-like documents and is designed for scalable, highly available document-based applications. For the exam, choose DocumentDB when you need a managed MongoDB-compatible database.

## Amazon DynamoDB

Amazon DynamoDB is a fully managed serverless NoSQL key-value and document database. It provides single-digit millisecond performance at scale and supports automatic scaling, global tables, and built-in high availability. For the exam, choose DynamoDB when you need a highly scalable NoSQL database with low-latency access.

## Amazon DynamoDB Accelerator (DAX)

Amazon DAX is an in-memory cache designed specifically for DynamoDB. It reduces read latency from milliseconds to microseconds for read-heavy DynamoDB workloads. For the exam, choose DAX when DynamoDB needs faster repeated read performance without changing application logic significantly.

## Amazon EC2

Amazon EC2 provides resizable virtual servers in the AWS cloud. It gives users control over instance type, operating system, networking, storage, and scaling options. For the exam, choose EC2 when you need flexible compute with more server-level control than serverless services.

## Amazon EFS

Amazon EFS is a managed elastic file storage service for Linux workloads. It provides a shared file system that can be mounted by multiple EC2 instances across Availability Zones. For the exam, choose EFS when multiple compute resources need concurrent access to the same scalable file system.

## Amazon EKS

Amazon EKS is a managed Kubernetes service for running containerized applications. AWS manages the Kubernetes control plane while users manage worker nodes or use Fargate. For the exam, choose EKS when Kubernetes compatibility and ecosystem support are required.

## Amazon ElastiCache

Amazon ElastiCache is a managed in-memory caching service supporting Redis and Memcached. It improves application performance by caching frequently accessed data with very low latency. For the exam, choose ElastiCache for database query caching, session storage, or real-time low-latency data access.

## Amazon EMR

Amazon EMR is a managed big data processing service for frameworks such as Apache Spark, Hive, Presto, and Hadoop. It processes large datasets using clusters on EC2 or other supported compute options. For the exam, choose EMR for large-scale distributed data processing and analytics jobs.

## Amazon EventBridge

Amazon EventBridge is a serverless event bus service for building event-driven applications. It routes events from AWS services, SaaS applications, and custom applications to targets such as Lambda, Step Functions, and SQS. For the exam, choose EventBridge when services need to react to events with loose coupling.

## Amazon EBS

Amazon EBS provides block storage volumes for Amazon EC2 instances. It is used for operating systems, databases, and applications that need persistent low-latency block storage. For the exam, choose EBS when a single EC2 instance needs durable block-level storage.

## Amazon ECS

Amazon ECS is a managed container orchestration service for running Docker containers on AWS. It can run tasks on EC2 instances or on serverless Fargate compute. For the exam, choose ECS when you need AWS-native container orchestration without managing Kubernetes.

## Amazon FSx

Amazon FSx provides fully managed file systems for specialized workloads. It includes options such as FSx for Windows File Server, Lustre, NetApp ONTAP, and OpenZFS. For the exam, choose FSx when workloads need managed file storage with specific file system features or protocol compatibility.

## Amazon GuardDuty

Amazon GuardDuty is a managed threat detection service for AWS accounts and workloads. It analyzes data sources such as CloudTrail logs, VPC Flow Logs, and DNS logs to detect suspicious activity. For the exam, choose GuardDuty when you need intelligent threat detection without deploying agents.

## Amazon Inspector

Amazon Inspector is a vulnerability management service for scanning AWS workloads. It identifies software vulnerabilities and unintended network exposure in resources such as EC2 instances, container images, and Lambda functions. For the exam, choose Inspector when you need automated vulnerability scanning.

## Amazon Kendra

Amazon Kendra is a managed intelligent search service powered by machine learning. It helps users search across enterprise documents and data sources using natural language questions. For the exam, choose Kendra when an organization needs smart search across internal knowledge bases.

## Amazon Kinesis Data Firehose

Amazon Kinesis Data Firehose is a managed service for loading streaming data into destinations. It can deliver data to services such as S3, Redshift, OpenSearch Service, and third-party endpoints with minimal administration. For the exam, choose Firehose when you need simple, managed streaming data delivery without custom consumers.

## Amazon Kinesis Data Streams

Amazon Kinesis Data Streams is a service for collecting and processing real-time streaming data at scale. Applications can produce data into streams, and custom consumers can process records in near real time. For the exam, choose Data Streams when you need custom real-time stream processing and control over consumers.

## Amazon Lex

Amazon Lex is a managed service for building conversational chatbots and voice bots. It uses automatic speech recognition and natural language understanding, similar to the technology behind Alexa. For the exam, choose Lex when you need conversational interfaces for applications.

## Amazon Macie

Amazon Macie is a managed data security and privacy service for discovering sensitive data in Amazon S3. It uses machine learning and pattern matching to identify data such as personally identifiable information. For the exam, choose Macie when the focus is finding and protecting sensitive data stored in S3.

## Amazon Managed Service for Apache Flink

Amazon Managed Service for Apache Flink is a managed service for processing streaming data using Apache Flink. It is used for real-time analytics, transformations, and event processing on continuous data streams. For the exam, choose it when you need managed stream processing with Apache Flink capabilities.

## Amazon Managed Streaming for Apache Kafka (MSK)

Amazon MSK is a managed service for running Apache Kafka on AWS. It handles Kafka cluster provisioning, scaling, patching, and availability while allowing applications to use Kafka APIs. For the exam, choose MSK when workloads require managed Kafka for event streaming.

## Amazon MQ

Amazon MQ is a managed message broker service for Apache ActiveMQ and RabbitMQ. It is useful when migrating applications that already use standard messaging protocols such as JMS, AMQP, MQTT, or STOMP. For the exam, choose Amazon MQ when traditional message broker compatibility is required.

## Amazon Neptune

Amazon Neptune is a managed graph database service. It is designed for highly connected data such as social networks, fraud detection, recommendation engines, and knowledge graphs. For the exam, choose Neptune when relationships between data are the main focus.

## Amazon OpenSearch Service

Amazon OpenSearch Service is a managed service for search, log analytics, and observability workloads. It can index and search large volumes of text and machine-generated data. For the exam, choose OpenSearch Service when you need full-text search or log analytics at scale.

## Amazon Personalize

Amazon Personalize is a managed machine learning service for creating real-time recommendations. It uses user behavior and item data to generate personalized product, content, or ranking suggestions. For the exam, choose Personalize when an application needs recommendation functionality without building ML models from scratch.

## Amazon Pinpoint

Amazon Pinpoint is a customer engagement service for sending targeted messages across channels such as email, SMS, push notifications, and voice. It supports audience segmentation, campaigns, and analytics. For the exam, choose Pinpoint when you need user engagement campaigns rather than simple email sending.

## Amazon Polly

Amazon Polly is a managed text-to-speech service. It converts written text into natural-sounding speech in multiple languages and voices. For the exam, choose Polly when an application needs to generate spoken audio from text.

## Amazon QuickSight

Amazon QuickSight is a managed business intelligence service for dashboards, reports, and data visualization. It connects to AWS and external data sources to help users analyze and share insights. For the exam, choose QuickSight when users need scalable BI dashboards without managing analytics servers.

## Amazon RDS

Amazon RDS is a managed relational database service for engines such as MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server. It handles tasks like backups, patching, Multi-AZ high availability, and read replicas. For the exam, choose RDS when you need a managed relational database with standard SQL engine support.

## Amazon RDS Proxy

Amazon RDS Proxy is a managed database proxy for Amazon RDS and Aurora. It pools and shares database connections to improve application scalability and resilience. For the exam, choose RDS Proxy when serverless or highly concurrent applications need efficient relational database connection management.

## Amazon Redshift

Amazon Redshift is a managed data warehouse service for large-scale analytics. It is optimized for complex SQL queries across structured and semi-structured data. For the exam, choose Redshift when you need high-performance analytics and reporting over large datasets.

## Amazon Rekognition

Amazon Rekognition is a managed computer vision service for image and video analysis. It can detect objects, scenes, faces, text, unsafe content, and perform facial analysis or comparison. For the exam, choose Rekognition when an application needs image or video recognition without custom ML development.

## Amazon Route 53

Amazon Route 53 is a scalable DNS and domain registration service. It routes users to applications using routing policies such as simple, weighted, latency-based, failover, and geolocation routing. For the exam, choose Route 53 when managing DNS records, domain names, or DNS-based traffic routing.

## Amazon S3

Amazon S3 is a highly durable, scalable object storage service. It stores data as objects inside buckets and is commonly used for backups, static websites, data lakes, logs, and application assets. For the exam, choose S3 when you need durable object storage accessible over HTTP-based APIs.

## Amazon S3 Glacier

Amazon S3 Glacier is a low-cost storage class family for long-term archive data. It is designed for infrequently accessed data where retrieval can take minutes or hours depending on the option selected. For the exam, choose S3 Glacier when data must be retained cheaply for compliance or archival purposes.

## Amazon SageMaker

Amazon SageMaker is a managed machine learning service for building, training, and deploying ML models. It provides tools for data preparation, notebooks, training jobs, model hosting, and MLOps. For the exam, choose SageMaker when a team needs an end-to-end platform for custom machine learning.

## Amazon SES

Amazon Simple Email Service is a managed email sending and receiving service. It is commonly used for transactional emails, notifications, and marketing messages from applications. For the exam, choose SES when you need scalable email delivery rather than multi-channel campaigns.

## Amazon SNS

Amazon Simple Notification Service is a fully managed pub/sub messaging service. It sends messages from publishers to multiple subscribers such as Lambda, SQS, HTTP endpoints, email, or SMS. For the exam, choose SNS when one message must fan out to multiple recipients or systems.

## Amazon SQS

Amazon Simple Queue Service is a managed message queue for decoupling application components. It stores messages until consumers process them and supports standard queues for high throughput or FIFO queues for ordered processing. For the exam, choose SQS when you need reliable asynchronous communication between services.

## Amazon Timestream 

Amazon Timestream is a fully managed, serverless time-series database service for storing and analyzing timestamped data at scale. Applications can write metrics, events, IoT sensor data, and operational data, while Timestream automatically manages storage tiers and query performance. For the exam, choose Timestream when you need to store and analyze time-series data such as IoT telemetry, application metrics, logs, or monitoring data.

## Amazon Textract

Amazon Textract is a managed machine learning service that extracts text, handwriting, forms, and tables from documents. It goes beyond basic OCR by understanding document structure. For the exam, choose Textract when processing scanned forms, invoices, or documents automatically.

## Amazon Transcribe

Amazon Transcribe is a managed automatic speech recognition service. It converts spoken audio into written text and supports features such as timestamps and speaker identification. For the exam, choose Transcribe when an application needs speech-to-text conversion.

## Amazon Translate

Amazon Translate is a managed neural machine translation service. It translates text between supported languages for applications, websites, and content workflows. For the exam, choose Translate when an application needs language translation without building custom translation models.

## Elastic Load Balancing (ELB)

Elastic Load Balancing automatically distributes incoming traffic across multiple targets such as EC2 instances, containers, IP addresses, or Lambda functions. It improves availability and fault tolerance by routing traffic only to healthy targets. For the exam, recognize ELB as the general AWS load balancing service family.

## Application Load Balancer (ALB)

Application Load Balancer operates at Layer 7 for HTTP and HTTPS traffic. It supports host-based routing, path-based routing, redirects, fixed responses, and routing to containers or Lambda. For the exam, choose ALB when you need advanced web application routing.

## Network Load Balancer (NLB)

Network Load Balancer operates at Layer 4 for TCP, UDP, and TLS traffic. It is designed for ultra-high performance, very low latency, and static IP support. For the exam, choose NLB when handling high-throughput network traffic or when static IP addresses are required.

## Gateway Load Balancer (GWLB)

Gateway Load Balancer is used to deploy, scale, and manage third-party virtual network appliances. It transparently routes traffic through appliances such as firewalls, intrusion detection systems, or inspection tools. For the exam, choose GWLB when traffic must pass through security appliances before reaching applications.

## VMware Cloud on AWS

VMware Cloud on AWS lets organizations run VMware Software-Defined Data Center environments on AWS infrastructure. It supports migration and hybrid operations for workloads already running on VMware vSphere. For the exam, choose VMware Cloud on AWS when a company wants to extend or migrate VMware workloads to AWS without redesigning them immediately.