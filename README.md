# Digital Talent Scholarship | Online Academy Artificial Intelligence Notes
A collection of notes on Digital Talent Scholarship Online Academy Artifical Intelligence 2019.
Contributions are always welcome!


# Cloud Practitioner Essentials (Second Edition)

# Course 1: Introduction to the AWS Cloud
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
  1. AWS management console
    * Navigation
    * Usability
    * Convenient mobile app
  2. Command Line Interface
    * Programming language agnostic
    * Flexibility to create scripts
  3. SDKs
    * Ability to use AWS in existing applications
    * Flexibility to create applications
* Create your own resources
* Access features on the go

# Course 2: AWS Core Services
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

# Course 3: Integrated Services

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
