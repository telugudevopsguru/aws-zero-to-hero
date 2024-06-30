# 30 Days AWS Zero to Hero

## Prerequisites:
1. Windows/ Mac laptop
2. Basic Linux Commands

## Day 1:
- What is Cloud Computing?
- Benefits of Cloud Computing
- Types of Cloud Computing
- Types of Cloud Services
- What is AWS?
- Advantages of AWS
- Disadvantages of AWS
- AWS Global Infrastructure
- Regions
- Availability Zones
- Lab Session - Creation of an AWS account

## Day 2:
- AWS Free Tier
- AWS Management Console Overview
- AWS Pricing Models
- AWS Support Plans
- AWS Trusted Advisor Overview
- Lab Session - Navigating AWS Management Console

## Day 3:
- AWS Services Overview
- Compute Services
- Storage Services
- Database Services
- Networking Services
- Security & Identity Services
- Management Tools
- Analytics Services
- Application Integration Services

## Day 4: Amazon Elastic Compute Cloud (EC2) Part 1
- What is Amazon EC2?
- Features of Amazon EC2
- Amazon EC2 Instance Types
- Lab Session - Creation of a Linux EC2 instance
- Lab Session - Downloading PuTTY and PuTTYgen
- Lab Session - Convert PEM to PPK file
- Lab Session - Connecting to Linux server
- Lab Session - Creation of a Windows EC2 instance
- Lab Session - Create an AMI from an Amazon EC2 Instance

## Day 5: Amazon Elastic Compute Cloud (EC2) Part 2
- What is an Elastic IP?
- Lab Session - Creating an Elastic IP and Attaching it to an EC2 Instance
- What is a Security Group?
- Lab Session - Creating a Security Group and Attaching it to an EC2 Instance
- Spot Instances, On-Demand Instances, Savings Plans, Reserved Instances, Dedicated Hosts, Scheduled Instances, Capacity Reservations
- Lab Session - Opening a support ticket with AWS
- Lab Session - Requesting Service Quotas in AWS
- Lab Session - Metadata and user data in EC2

## Day 6: AWS EBS (Elastic Block Storage)
- What is AWS EBS?
- Features of AWS EBS
- Types of EBS Volumes
- Lab Session - Creation of an EBS Volume
- Lab Session - Attach an EBS volume to a Linux EC2 instance
- Lab Session - Increase the size of an existing EBS volume on a Linux EC2 instance
- Lab Session - Attach an EBS volume to a Windows EC2 instance
- Lab Session - Increase the size of an existing EBS volume on a Windows EC2 instance
- Lab Session - Change the EBS volume type
- Lab Session - Encrypt an existing attached EBS volume

## Day 7: AWS EBS Snapshot
- What is a Snapshot in AWS?
- Lab Session - Creation of a snapshot from an EC2 instance
- Lab Session - Creation of a snapshot from an EBS volume
- Lab Session - Creation of an AWS AMI from a snapshot
- Lab Session - Creation of an EBS volume from a snapshot
- Options in a Snapshot
- Lab Session - Deletion of Snapshots, Volumes, and AMIs

## Day 8: AWS IAM (Identity Access Management)
- What is AWS IAM?
- Features of AWS IAM
- Lab Session - AWS IAM Users
- Lab Session - AWS IAM User Groups
- What are AWS IAM Policies?
- Types of AWS IAM Policies
- Lab Session - Configuring AWS CLI
- Lab Session - Named profiles for the AWS CLI
- What is an IAM role?
- Lab Session - How to attach the IAM role to an EC2 instance?
- Root Account vs IAM user
- Lab Session - AWS IAM Password Policy
- Lab Session - Multi-Factor Authentication (MFA) for AWS IAM
- IAM Best Practices

## Day 9: AWS ASG (Auto Scaling Group)
- What is an Auto Scaling Group?
- Benefits of an Auto Scaling Group
- What is a Launch Configuration?
- Benefits of a Launch Configuration
- Drawbacks of a Launch Configuration
- Lab Session - Creation of an AWS Launch Configuration
- What is an AWS Launch Template?
- Benefits of an AWS Launch Template
- Lab Session - Creation of an AWS Launch Template
- Difference between a Launch Template and a Launch Configuration
- Lab Session - Creation of an ASG through an AWS Launch Configuration
- Lab Session - Creation of an ASG through an AWS Launch Template
- Lab Session - Enabling CloudWatch monitoring in an ASG
- Lab Session - Deletion of an ASG

## Day 10: AWS ELB (Elastic Load Balancing)
- What is AWS Elastic Load Balancing?
- Benefits of AWS Elastic Load Balancing
- What is an AWS Classic Load Balancer?
- Features of a Classic Load Balancer
- Lab Session - Creation of an AWS Classic Load Balancer
- Lab Session - Deletion of a Classic Load Balancer
- What is an AWS Target Group?
- What is a Listener?
- Lab Session - Creation of an AWS Target Group
- What is an AWS Application Load Balancer?
- Benefits of an AWS Application Load Balancer
- Lab Session - Creation of an Application Load Balancer
- Lab Session - Deletion of an ALB

## Day 11: AWS ELB (Elastic Load Balancing) Part 2
- What is an AWS Network Load Balancer?
- Benefits of an AWS Network Load Balancer
- Lab Session - Creation of an AWS Network Load Balancer
- Lab Session - Deletion of an NLB
- Difference between an ALB and an NLB
- Lab Session - Attaching an ALB to a new Auto Scaling group
- Lab Session - Attaching an ALB to an existing Auto Scaling group

## Day 12: AWS S3 (Simple Storage Service)
- What is AWS Simple Storage Service (S3)?
- Buckets and Objects in Amazon S3
- Types of storage classes in AWS S3
- Lab Session - Create an S3 bucket
- Lab Session - Upload objects to S3 using the AWS Console
- Lab Session - Upload objects to S3 using the AWS CLI
- S3 Versioning and enabling it
- Bucket Policy in Amazon S3
- Working with the Bucket Policy for S3 bucket

## Day 13: AWS S3 (Simple Storage Service) Part 2
- Access Control List (ACL) in Amazon S3
- Lab Session - Apply ACL for S3 bucket
- S3 Bucket Lifecycle
- Hosting a static website using Amazon S3
- Presigned URLs in AWS S3
- Lab Session - Working with Presigned URLs in AWS S3
- Server-side encryption for Amazon S3 buckets
- Lab Session - Delete an S3 bucket

## Day 14: AWS VPC (Virtual Private Cloud)
- What is AWS VPC (Virtual Private Cloud)?
- Key features of AWS VPC
- CIDR (Classless Inter-Domain Routing)
- Lab Session - Choose the appropriate CIDR Block
- IPV4 and IPV6
- Subnets in AWS VPC
- Types of Subnets in AWS VPC
- Subnet sizing for IPV4
- Subnet routing in AWS VPC
- Route table in AWS VPC
- Components of a Route table
- Internet Gateway (IGW) in AWS VPC
- Lab Session - Overview of the Default VPC in AWS

## Day 15: AWS VPC (Virtual Private Cloud) Part 2
- Lab Session - Create a customized VPC in AWS
- NAT Gateway and NAT Instance in AWS VPC
- Differences between NAT Gateway and NAT Instance
- Lab Session - Create a NAT Instance in AWS VPC
- Lab Session - Create a NAT Gateway in AWS VPC
- Lab Session - Delete a NAT Gateway in AWS VPC

## Day 16: AWS VPC (Virtual Private Cloud) Part 3
- Network Access Control List (NACL) in AWS VPC
- Lab Session - Create a Network Access Control List (NACL) in AWS VPC
- Security Group in AWS VPC
- Lab Session - Create a Security Group in AWS VPC
- Differences between NACL and Security Group in AWS VPC
- VPC Flow Logs and how to create them
- Lab Session - Enable VPC Flow Logs

## Day 17: AWS VPC (Virtual Private Cloud) Part 4
- Options for configuring an AWS VPC
- DHCP Option Set in AWS VPC
- DNS Hostnames and DNS Resolution in AWS VPC
- VPC Endpoints in AWS and types available
- Lab Session - Create a Gateway VPC Endpoint for S3 in AWS
- Prefix Lists in AWS VPC
- Elastic Network Interface (ENI) in AWS
- Lab Session - Create an ENI in AWS
- Lab Session - Delete an AWS VPC

## Day 18: AWS VPC Peering
- What is VPC Peering?
- Key aspects of VPC Peering
- Types of VPC Peering
- Lab Session - Intra-region VPC peering within the same AWS account
- Lab Session - Delete intra-region VPC peering within the same AWS account
- Lab Session - Establish intra-region VPC peering with a different AWS account
- Lab Session - Terminate intra-region VPC peering with a different AWS account
- Lab Session - Inter-region VPC peering within the same AWS account
- Lab Session - Remove inter-region VPC peering within the same AWS account
- Lab Session - Configure inter-region VPC peering with a different AWS account
- Lab Session - Remove inter-region VPC peering with a different AWS account
