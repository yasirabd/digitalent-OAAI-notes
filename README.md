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
