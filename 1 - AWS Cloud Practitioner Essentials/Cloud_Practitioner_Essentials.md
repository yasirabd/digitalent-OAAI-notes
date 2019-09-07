# Cloud Practitioner Essentials (Second Edition)

# Module 1: Introduction to the AWS Cloud
* Cloud Computing refers to the on-demand delivery of IT resources and applications via the internet.
* AWS Cloud benefits:
  * Reducing risk: risk management in Cloud
  * Scalability: able to resize resources as necessary
  * Agility: increasing speed, ease of experimentation, and cultivating a culture of innovation
  * Elasticity: scale computing resources up or down easily
  * Reliability: able to acquire computing resources to meet demand and mitigate disruptions
  * Availability: place resources in multiple locations
  * Fault tolerance: system can remain operational even if some of the components of that system fail
  * Security: full control and ownership over your data

## Introduction to AWS Interfaces
* Three ways to use AWS:
  * AWS management console
    * Navigation
    * Usability
    * Convenient mobile app
  * Command Line Interface
    * Programming language agnostic
    * Flexibility to create scripts
  * SDKs
    * Ability to use AWS in existing applications
    * Flexibility to create applications
* Create your own resources
* Access features on the go

# Module 2: AWS Core Services
## Amazon Elastic Cloud Compute (EC2)
* Pay as you go
* Broad selection of HW/SW
* Global hosting

## Amazon Elastic Block Store (EBS)
* EBS Volumes:
  * Choose between HDD and SSD types
  * Persistent and customizable block storage for EC2 instances
  * Replicated in the same Availability Zone
  * Backup using Snapshots
  * Easy and transparent Encryption
  * Elastic volumes

## Amazon Simple Storage Service (S3)
* What is Amazon S3?
  * Managed cloud storage device
  * Store virtually unlimited number of objects
  * Access any time, from anywhere
  * Rich security control
* Objects (Key, Object, bucket name)
* Common Use Cases
  * Storing applications assets
  * Static web hosting
  * Backup & Disaster recovery
  * Staging area for Big data, etc.

## AWS Global Infrastructure
* Region
* Availability zone: data center on a specific region
* Edge location: host a content delivery network or CDN

## Amazon Virtual Private Cloud (VPC)
* Introduction
  * A private, virtual network in the AWS Cloud
  * Allows complete control of network configuration
  * Offers several layers of security controls
  * Other AWS services deploy into VPC
* Features
  * Build upon high availability of AWS Regions and Availability Zones (AZ): lives within a Region, multiple VPCs per account
  * Subnets: used to divide Amazon VPS
  * Route tables: control traffic going out of the subnets
  * Internet Gateway (IGW): allows access to the Internet from Amazon VPC
  * NAT Gateway: allows private subnet
  * Network Access Control Lists (NACL): control access the subnets, stateless

## AWS Security Groups
* Security groups: act as built-in firewalls, control accessibility to instances.

# Module 3: Integrated Services

## Application Load Balancer
* is a stated earlier, the second type of load balancer introduced as part of the Elastic Load Balancing Service.
* Enhanced Features: Supported Protocols, CloudWatch Metrics, Access Logs, Health Checks
* Additional features:
  * Path and host-based routing
  * Native IPv6 support
  * AWS WAF
  * Dynamic ports
  * Deletion protection & request tracing
* Why use Application Load Balancer? Ability to use containers to host your microservices and route to those applications from a single load balancer.
* Key terms:
  * Listeners: a process that checks for connection requests, using the protocol and port that you configure.
  * Target: a destination for traffic based on the established listener rules.
  * Target group: each target group routes requests to one or more registered targets using the protocol and port number specified.

## Auto Scaling
* Helps you ensure that you have the correct number of Amazon EC2 instances available to handle the load for you.
* Auto Scaling adjusting capacity as needed
* Scalability: to ensure that our workload has enough EC2 resources to meet fluctuating performance requirements
* Automation: automate EC2 resource provisioning to occur on-demand
* Components:
  * Launch Configuration (what?): AMI, instance type, security groups, roles
  * Auto Scaling Group (where?): VPC and subnets, load balancer, minimum/maximum instances, desired capacity
  * Auto Scaling Policy (when?): scheduled, on-demand, scale-out policy, scale-in policy

## Amazon Route 53
* It's a Domain Name System, or DNS, web service designed to provide businesses and developers with a reliable and highly scalable way to route end-users to internet applications.
* DNS is a translator
* How does it work?
  * user search through website example.com -> internet service provider -> Route 53
  * Route 53 returns IP address 192.0.0.1 -> internet service provider -> user
* DNS resolution strategies:
  * Simple routing
  * Geo-location
  * Failover
  * Weighted round robin
  * Latency-based
  * Multi-value answer

## Amazon Relational Database Services (RDS)
* Challenges:
  * Server maintenance and energy footprint
  * Software install and patches
  * Database backups and high availability
  * Limits on scalability
  * Data security
  * OS install and patches
* Amazon RDS is a managed that sets up and operates a relational database in the cloud.
* With Amazon RDS, we only manage application optimization
* Ability to configure your database instance for high availability with a Multi-AZ deployment
* Amazon RDS Read Replicas:
  * Asynchronous replication method used
  * Offload read queries from the master DB instance
  * Ideal for read-heavy database workloads
  * Read replica can be promoted to Master if needed
* Benefits:
  * Highly scalable
  * High performance
  * Easy to administer
  * Available and durable
  * Secure and compliant

## AWS Lambda
* is an event-driven serverless compute service.
* is a compute service that lets you run code without provisioning or managing service.
* Benefits: no servers to manage, continuous scaling, subsecond metering
* How does it work? Example image recognition
  * image -> mobile app -> S3 -> AWS Lambda -> Detect Objects and Scenes
  * mobile app: captures an image
  * S3: image upload into S3
  * AWS Lambda: A Lambda function is triggered and calls Recognition
  * Recognition retrieves the image from S3 and returns labels

## AWS Elastic Beanstalk
* is A Platform as a Service
* Allows quick deployment of your applications
* Reduces management complexity
* Keeps control in your hand: instance type, database, update, log files, load balancer
* Supports a large range of platforms
* Components, it provides: application service, HTTP service, Operating system, Language interpreter, Host
* Update your applications as easily as you deployed it

## Amazon Simple Notification Service
* Flexible, fully managed pub/sub messaging and mobile communications service
* Coordinates the delivery of messages to subscribing endpoints and clients.
* Easy to setup, operate and send reliable communications.
* Decouple and scale microservices, distributed sytems and serverless applications.

## Amazon CloudWatch
* Monitors your AWS resources and the applications you run on AWS in real time
* Features:
  * Collect and track metrics
  * Collect and monitor log files
  * Set alarms
  * Automatically react to changes
* Components:
  * Metrics: represents a time-ordered set of data points that are published to CloudWatch
  * Alarms: watches a single metric.
  * Events: near real-time system events that describe changes in AWS resources.
  * Logs: monitor and troubleshoot systems and applications using existing log files.
  * Dashboard: customizable home pages in the CloudWatch console to monitor your resources in a single view.

## Amazon CloudFront
* You can leverage multiple locations around the world to deliver your content allowing your users to interact with your applications in a lower latency.
* CloudFront is a content delivery network (CDN).

## Amazon CloudFormation
* Simplifies the task of repeatedly and predictably creating groups of related resources that power your applications.
* Service: fully-managed service, create, update and delete resources in stacks.
* Components: template file + AWS CloudFormation -> Stack
  * Template file: resources to provision such as text file, json, yaml.
* Requirements: template and permission

# Module 4: AWS Architecture

## The AWS Well-Architecture Framework
* 5 Pillars: security, reliability, performance efficiency, cost optimization, operational excellence
* Security Pillar: ability to protect your information systems and assets while delivering business value through risk assessments and mitigation strategies.
  * Identity and access management (IAM): ensure only authorized and authenticated users are able to access our resources.
  * Detective controls: identify a potential security incident
  * Infrastructure protection: ensures that systems and services within our architecture are protected against unintended and unauthorized access.
  * Data protection: data classification, encryption, protecting data at rest and in transit, data backup, replication and recovery.
  * Incident response: ensures our architecture is updated to accommodate a timely investigation in recovery.
* Security Pillar: Design Principles
  * Implement security at all layers
  * Enable traceability
  * Apply principle of least privilege
  * Focus on securing your system
  * Automate
* Reliability Pillar
  * Recover from issues/failures
  * Apply best practices in: foundations, change management, failure management
  * Anticipate, respond, and prevent failures
* Reliability Pillar: Design Principles
  * Test recovery procedures
  * Automatically recover
  * Scale horizontally
  * Stop guessing capacity
  * Manage change in automation
* Performance Efficiency Pillar
  * Select customizable solutions
  * Review to continually innovate
  * Monitor AWS services
  * Consider the trade-offs
* Performance Efficiency Pillar: Design Principles
  * Democratize advanced technologies
  * Go global in minutes
  * Use a serverless architectures
  * Experiment more often
  * Have mechanically sympathy
* Cost Optimization Pillar
  * Use cost-effective resources
  * Matching supply with demands
  * Increase expenditure awareness
  * Optimize over time
* Cost Optimization Pillar: Design Principles
  * Adopt a consumption model
  * Measure overall efficiency
  * Reduce spending on data center operations
  * Analyze and attribute expenditure
  * Use managed services
* Operational Excellence Pillar
  * Manage and automate changes
  * Respond to events
  * Define the standards

## Fault Tolerance and High Availability
* Fault Tolerance: ability of a system to remain operational
* High Availability: ensure that your systems are always functioning and accessible, and that downtime is minimized as much as possible, without the need for human intervention.
* High Availability AWS:
  * multiple servers
  * availability zones
  * regions
  * fault-tolerance services
* High Availability Service Tools:
  * Elastic Load Balancers: distribute incoming traffic (loads)
  * Elastic IP Addresses: are static IP addresses
  * Route 53: authoritative DNS service
  * Auto scaling: terminates and launches instances, adjusting capacity
  * Amazon CloudWatch: distributed statistics gathering systems
* Fault Tolerant Tools:
  * Amazon Simple Queue Service: backbone of our fault-tolerant application.
  * Amazon Simple Storage Service (S3): fault-tolerant data storage
  * Amazon Relational Database Service (RDS): fault-tolerant relational database

## Web Hosting
* We can implement web hosting on AWS
* We can use on-demand provisioning to spin up additional servers so that we can adjust capacity, and only pay for what we use.
* AWS cloud allows to provision testing fleets only when you need them.

# Module 5: AWS Security

## Introduction to AWS Security
* Security is of the utmost importance to AWS
![aws-security](https://github.com/yasirabd/digitalent-OAAI-notes/blob/master/assets/aws-security.PNG "AWS Security")
* Keep your data safe:
  * Resilient infrastructure
  * High security
  * Strong safeguards
* Network security
  * firewalls
  * Encryption
  * Private/dedicated connections
  * DDoS mitigation
* Data Encryption
  * Encryption capabilities
  * Key management options
  * Hardware-based cryptographic key storage options
* Access Control and Management
  * Identity and Access Management (IAM)
  * Multi-factor authentication (MFA)
  * Integration and federation with corporate directories
  * Amazon Cognito
  * AWS SSO
* Monitoring and Logging

## The Shared Responsibility Model
* Stacks
  * User Data
  * Application
  * Guest OS
  * (If using EC2, there is a dividing line, you choose the OS)
  * Hypervisor
  * Network
  * Physical
* AWS is responsible for whatever is below the line, and we responsible for what is above the line

## Identity and Access Management (IAM)
![iam](https://github.com/yasirabd/digitalent-OAAI-notes/blob/master/assets/IAM.PNG "IAM")
* User: is a permanent name computer (human/machine)
* Group: is a collection of users
* Role: is an operator, authentication. It's a permanent set of credentials. The key is the credentials with a role are temporary.
* Policy documents: lists the specific API or wildcard group of APIs.

## Amazon Inspector
* Assesses applications for:
  * Vulnerabilities
  * Deviations from best practices
* Produces a detailed report with:
  * Security findings
  * Prioritized steps for remediation
* Benefits:
  * Identify application security issues
  * Integrate security into DevOps
  * Increase development agility
  * Leverage AWS security expertise
  * Streamline security compliance
  * Enforce security standards
* Accessing Amazon Inspector:
  * Console
  * SDKs
  * HTTPS API
  * Command line tools
* Enables you to:
  * Quickly and easily assess your AWS resources
  * Offload security assessments so you can focus on more complex security issues
  * Gain a deeper understanding of your AWS resources

## AWS Shield
* is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS.
* Denial of Service (DoS): a deliberate attempt to make your website or application unavailable to users.
* DDoS: multiple sources are used to attack target; infrastructure and application layers can be affected
* DDoS mitigation challenges:
  * Complex setup and implementation
  * Bandwidth limitations
  * Manual intervention
  * Time consuming
  * Degraded performance
  * Expensive
* AWS Shield tiers: standard, advanced
* AWS Shield Standard
  * Automatic protection
  * Quick detection (always-on)
  * Inline attack mitigation
  * Self service
* AWS Shield Advanced
  * Specialized report
  * Advanced attack mitigation
  * Visibility and attack notification
  * Always-on monitoring
  * Enhanced detection
  * DDoS cost protection
* Benefits:
  * Seamless integration and deployment
  * Customizable protection
  * Cost efficient

## Security Compliance
* AWS Compliance approach:
  * AWS responsibility: provide highly-secure and controlled platform, security features
  * Customer responsibility: Configure IT
  * Shared responsibility and control
* AWS shares security information by:
  * Industry certifications
  * Publishing security and control practices
  * Compliance report
* Assurance programs, AWS provides compliance information and resources:
  * Certifications/attestations
  * Legal/regulatory support
  * Alignments/Frameworks
* Components:
  * Risk management: established business plan and process
  * Control environment: establish and maintain an environment
  * Information security: designed to protect, publishes security whitepaper
* Risk management at work
![risk-management](https://github.com/yasirabd/digitalent-OAAI-notes/blob/master/assets/risk-management.PNG "Risk Management")
* Customer compliance
![customer-compliance](https://github.com/yasirabd/digitalent-OAAI-notes/blob/master/assets/customer-compliance.PNG "Customer Compliance")

# Module 6: Pricing and Support

## Fundamentals of Pricing
* With AWS you can:
  * Pay as you go
  * Pay less when you reserve
  * Pay even less per unit by using more
  * Pay even less as AWS grows
* Reserved instances:
  * All up-front (AURI)
  * Partial up-front (PURI)
  * No upfront payments (NURI)
* Free usage tier for new customers

## Pricing Details
* Cost fundamentals:
  * Pay for compute capacity, storage, outbound data transfer (aggregated)
  * No charge for inbound data transfer
* Amazon EC2
  * Charges only for capacity used
  * Cost factors: clock-second/hourly billing and instance configuration
  * Purchase types: on-demand instances, reserved instances, spot instances
  * OS prices included in instance prices
* Amazon S3
  * Storage cost: number and size of objects, type of storage
  * Cost factors: pricing based on requests and data transfer
* Amazon EBS
  * Cost factors: volumes and IOPS (input output operations per second)
  * Another cost factors: Snapshots (added cost per GB-month), Data transfer
* Amazon RDS
  * Cost factors: clock-hour billing, database characteristics, and DB purchase type (on-demand, reserved, provision multiple DB)
  * Another cost factors: provisioned storage, additional storage, deployment type, data transfer
* Amazon CloudFront
  * Cost factors: pricing varies across geographic regions, based on request and data transfer out

## AWS Trusted Advisor
* Provides best practices (or checks) in for categories: cost optimization, performance, security, and fault tolerance
* Benefits:
  * Over 50 millions recommendations
  * $500M+ in cost savings
* How Trusted Advisor works
![trusted-advisor](https://github.com/yasirabd/digitalent-OAAI-notes/blob/master/assets/trusted-advisor-works.PNG "Trusted Advisor Works")

## AWS Support Plans
* AWS Support:
  * Experimenting with AWS
  * Production use of AWS
  * Business critical use of AWS
* Support Plans:
  * Basic support
  * Developer support
  * Business support
  * Enterprise support
