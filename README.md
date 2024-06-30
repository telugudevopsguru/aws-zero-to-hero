# AWS Training Syllabus

## Day 1:
- What is Cloud Computing?
- Benefits of Cloud Computing
- Types of Cloud Computing
- Types of Cloud Services
- What is AWS
- Advantages of AWS
- Disadvantages of AWS
- AWS Global Infrastructure
  - Regions
  - Availability Zones
- **Lab Session:** Creation of an AWS account

## Day 2: Tools Installation
- **Lab Session:** Creating an AWS IAM User
- **Lab Session:** Creation of Amazon Linux EC2 instance
- **Lab Session:** Creation of Ubuntu EC2 instance
- **Lab Session:** Creation of Windows EC2 instance
- **Lab Session:** Installation of AWS CLI in Windows
- **Lab Session:** Installation of AWS CLI in Ubuntu
- **Lab Session:** Installation of kubectl in Linux
- **Lab Session:** Installation of kubectl in Windows

## Day 3: AWS IAM (Identity Access Management)
- What is AWS IAM?
- Features of AWS IAM
- **Lab Session:** AWS IAM Users
- **Lab Session:** AWS IAM User Groups
- What are AWS IAM Policies?
- Types of AWS IAM Policies
- **Lab Session:** Configuring AWS CLI
- **Lab Session:** Named profiles for the AWS CLI
- What is an IAM role?
- **Lab Session:** How to attach the IAM role to an EC2 instance?
- Root Account vs IAM user
- **Lab Session:** AWS IAM Password Policy
- **Lab Session:** Multi-Factor Authentication (MFA) for AWS IAM
- IAM Best Practices

## Day 4: Amazon Elastic Compute Cloud (EC2) Part 1
- What is Amazon Elastic Compute Cloud (EC2)?
- Features of Amazon EC2
- Amazon EC2 Instance Types
- **Lab Session:** Creation of a Linux EC2 instance
- **Lab Session:** Downloading PuTTY and PuTTYgen
- **Lab Session:** How to convert PEM to PPK file
- **Lab Session:** Connecting to the Linux server
- **Lab Session:** Creation of a Windows EC2 instance
- **Lab Session:** Create an AMI from an Amazon EC2 Instance

## Day 5: Amazon Elastic Compute Cloud (EC2) Part 2
- What is an Elastic IP?
- **Lab Session:** Creating an Elastic IP and Attaching it to an EC2 Instance
- What is a Security Group?
- **Lab Session:** Creating a Security Group and Attaching it to an EC2 Instance
- Spot Requests, On-Demand Instances, Savings Plans, Reserved Instances, Dedicated Hosts, Scheduled Instances, Capacity Reservations
- **Lab Session:** Opening a support ticket with AWS
- **Lab Session:** Requesting Service Quotas in AWS
- **Lab Session:** What is metadata and user data in EC2?

## Day 6: AWS EBS (Elastic Block Storage)
- What is AWS EBS?
- Features of AWS EBS
- Types of EBS Volumes
- **Lab Session:** Creation of an EBS Volume
- **Lab Session:** How to attach an EBS volume to a Linux EC2 instance
- **Lab Session:** How to increase the size of an existing EBS volume on a Linux EC2 instance
- **Lab Session:** How to attach an EBS volume to a Windows EC2 instance
- **Lab Session:** How to increase the size of an existing EBS volume on a Windows EC2 instance
- **Lab Session:** How to change the EBS volume type
- **Lab Session:** How to encrypt an existing attached EBS volume

## Day 7: AWS EBS Snapshot
- What is a Snapshot in AWS?
- **Lab Session:** Creation of a snapshot from an EC2 instance
- **Lab Session:** Creation of a snapshot from an EBS volume
- **Lab Session:** Creation of an AWS AMI from a snapshot
- **Lab Session:** Creation of an EBS volume from a snapshot
- Options in a Snapshot
- **Lab Session:** Deletion of Snapshots, Volumes, and AMIs

## Day 8: AWS ASG (Auto Scaling Group)
- What is an Auto Scaling Group?
- Benefits of an Auto Scaling Group
- What is a Launch Configuration?
- Benefits of a Launch Configuration
- Drawbacks of a Launch Configuration
- **Lab Session:** Creation of an AWS Launch Configuration
- What is an AWS Launch Template?
- Benefits of an AWS Launch Template
- **Lab Session:** Creation of an AWS Launch Template
- Difference between a Launch Template and a Launch Configuration
- **Lab Session:** Creation of an ASG through an AWS Launch Configuration
- **Lab Session:** Creation of an ASG through an AWS Launch Template
- **Lab Session:** Enabling CloudWatch monitoring in an ASG
- **Lab Session:** Deletion of an ASG

## Day 9: AWS ELB (Elastic Load Balancing)
- What is AWS Elastic Load Balancing?
- Benefits of AWS Elastic Load Balancing
- What is an AWS Classic Load Balancer?
- Features of a Classic Load Balancer
- **Lab Session:** Creation of an AWS Classic Load Balancer
- **Lab Session:** Deletion of a Classic Load Balancer
- What is an AWS Target Group?
- What is a Listener?
- **Lab Session:** Creation of an AWS Target Group
- What is an AWS Application Load Balancer?
- Benefits of an AWS Application Load Balancer
- **Lab Session:** Creation of an Application Load Balancer
- **Lab Session:** Deletion of an ALB

## Day 10: AWS ELB (Elastic Load Balancing)
- What is an AWS Network Load Balancer?
- Benefits of an AWS Network Load Balancer
- **Lab Session:** Creation of an AWS Network Load Balancer
- **Lab Session:** Deletion of an NLB
- Difference between an ALB and an NLB
- **Lab Session:** Attaching an ALB to a new Auto Scaling group
- **Lab Session:** Attaching an ALB to an existing Auto Scaling group

## Day 11: AWS S3 (Simple Storage Service) Part 1
- What is AWS Simple Storage Service (S3)?
- What are Buckets and Objects in Amazon S3?
- What are the different types of storage classes in AWS S3?
- **Lab Session:** How do you create an S3 bucket?
- **Lab Session:** How do you upload objects to S3 using the AWS Console?
- **Lab Session:** How do you upload objects to S3 using the AWS CLI?
- **Lab Session:** What is S3 Versioning, and how can it be enabled?
- **Lab Session:** What is a Bucket Policy in Amazon S3?
- **Lab Session:** Working with the Bucket Policy for S3 bucket?

## Day 12: AWS S3 (Simple Storage Service) Part 2
- What is an Access Control List (ACL) in Amazon S3?
- **Lab Session:** How do you apply the ACL for S3 bucket?
- **Lab Session:** Working with the S3 Bucket Lifecycle
- How can you host a static website using Amazon S3?
- What are Presigned URLs in AWS S3, and how do you create one?
- **Lab Session:** Working with the Presigned URLs in AWS S3
- **Lab Session:** How do you manage server-side encryption for Amazon S3 buckets?
- **Lab Session:** How do you delete an S3 bucket?

## Day 13: AWS VPC (Virtual Private Cloud) Part 1
- What is AWS VPC (Virtual Private Cloud)?
- What are the key features of AWS VPC?
- What is CIDR (Classless Inter-Domain Routing)?
- **Lab Session:** How do you choose the appropriate CIDR Block?
- What are IPV4 and IPV6?
- What are Subnets in the context of AWS VPC?
- What are the different types of Subnets in AWS VPC?
- How do you determine subnet sizing for IPV4?
- What is subnet routing in AWS VPC?
- What is a Route table in AWS VPC?
- What are the components of a Route table?
- What is an Internet Gateway (IGW) in AWS VPC?
- **Lab Session:** Overview of the Default VPC in AWS?

## Day 14: AWS VPC (Virtual Private Cloud) Part 2
- **Lab Session:** How do you create a customized VPC in AWS?
- What are NAT Gateway and NAT Instance in AWS VPC?
- What are the differences between NAT Gateway and NAT Instance?
- **Lab Session:** How do you create a NAT Instance in AWS VPC?
- **Lab Session:** How do you create a NAT Gateway in AWS VPC?
- **Lab Session:** How can you delete a NAT Gateway in AWS VPC?

## Day 15: AWS VPC (Virtual Private Cloud) Part 3
- What is a Network Access Control List (NACL) in AWS VPC?
- **Lab Session:** How do you create a Network Access Control List (NACL) in AWS VPC?
- What is a Security Group in AWS VPC?
- **Lab Session:** How do you create a Security Group in AWS VPC?
- What are the differences between NACL and Security Group in AWS VPC?
- What are VPC Flow Logs, and how do you create them?
- **Lab Session:** How to Enable VPC Flow Logs

## Day 16: AWS VPC (Virtual Private Cloud) Part 4
- What options are available for configuring an AWS VPC?
- What is a DHCP Option Set in AWS VPC?
- What are DNS Hostnames and DNS Resolution in AWS VPC?
- What are VPC Endpoints in AWS, and what are the types available?
- **Lab Session:** How do you create a Gateway VPC Endpoint for S3 in AWS?
- **Lab Session:** How do you manage Prefix Lists in AWS VPC?
- What is an ENI (Elastic Network Interface) in AWS?
- **Lab Session:** How do you create an ENI in AWS?
- **Lab Session:** How can you delete an AWS VPC?

## Day 17: AWS VPC Peering
- What is VPC Peering?
- What are the key aspects of VPC Peering?
- What are the different types of VPC Peering?
- **Lab Session:** How do you create intra-region VPC peering within the same AWS account?
- **Lab Session:** How do you delete intra-region VPC peering within the same AWS account?
- **Lab Session:** How do you establish intra-region VPC peering with a different AWS account?
- **Lab Session:** How do you terminate intra-region VPC peering with a different AWS account?
- **Lab Session:** How do you set up inter-region VPC peering within the same AWS account?
- **Lab Session:** How do you remove inter-region VPC peering within the same AWS account?
- **Lab Session:** How do you configure inter-region VPC peering with a different AWS account?
- **Lab Session:** How do you remove inter-region VPC peering with a different AWS account?

## Day 18: AWS CloudWatch and AWS CloudTrail
- What is CloudWatch?
- Key Features of CloudWatch
- **Lab Session:** Creating a log group in AWS CloudWatch
- **Lab Session:** Sending VPC Flow logs to a CloudWatch log group
- **Lab Session:** Setting up a CloudWatch alarm for an EC2 Instance
- What is AWS CloudTrail?
- Log event types in CloudTrail
- **Lab Session:** Setting up AWS CloudTrail to send logs to an S3 bucket
- **Lab Session:** Deletion of CloudTrail

## Day 19: AWS ECR (Elastic Container Registry)
- What is AWS ECR?
- Types of Repositories
- Components of Amazon ECR
- Features of Amazon ECR
- **Lab Session:** Creating an ECR repository in AWS
- **Lab Session:** Pushing a Docker image to AWS ECR
- **Lab Session:** Setting up the Lifecycle Policy in ECR
- **Lab Session:** Setting up Replication configuration in ECR

## Day 20: AWS EKS (Elastic Kubernetes Service)
- What is Amazon Elastic Kubernetes Service?
- How does Amazon EKS work?
- **Lab Session:** Installation of AWS CLI in Windows
- **Lab Session:** Installation of kubectl in Linux
- **Lab Session:** Installation of kubectl in Windows
- **Lab Session:** Creating an AWS IAM User
- **Lab Session:** Creating an EKS Cluster through the AWS Console
- **Lab Session:** Connecting to the EKS cluster
- **Lab Session:** Deploying a sample application in Kubernetes

## Day 21: AWS KMS (Key Management Service), AWS SES, SNS
- What is AWS KMS?
- Features and benefits of KMS
- Different types of keys in KMS
- **Lab Session:** Creating a KMS key
- **Lab Session:** Encrypting an EBS volume using AWS KMS
- **Lab Session:** Deletion of KMS
- What is AWS SES?
- **Lab Session:** Creating AWS SES
- **Lab Session:** Deletion of AWS SES
- What is AWS SNS?
- **Lab Session:** Creating AWS SNS
- **Lab Session:** Deletion of AWS SNS

## Day 22: AWS RDS (Relational Database Service)
- What is RDS?
- Features of RDS
- RDS Subnet Group
- Parameter groups
- Option groups
- Amazon RDS storage types
- **Lab Session:** Creating a MySQL database in AWS RDS
- **Lab Session:** Connecting to the RDS MySQL from an AWS EC2 instance
- **Lab Session:** Installation of MySQL Workbench
- **Lab Session:** Connecting to the RDS MySQL from MySQL Workbench
- **Lab Session:** Deletion of RDS MySQL version

## Day 23: AWS Route53
- What is AWS Route53?
- Benefits of Route53
- What is a hosted zone in Route53?
- Types of hosted zones
- **Lab Session:** Creating a public hosted zone in AWS Route53
- What are records in a hosted zone?
- Types of records
- What is Routing Policy?
- Types of Routing policies
- **Lab Session:** Creating a record in a hosted zone
- What are Route53 Health Checks?
- **Lab Session:** Creating a private hosted zone in AWS Route53
- **Lab Session:** Configuring query logging for a Hosted Zone
- **Lab Session:** Deletion of a Hosted Zone

## Day 24: AWS ACM (AWS Certificate Manager)
- What is AWS ACM?
- **Lab Session:** Creating AWS ACM
- **Lab Session:** Integrating AWS ACM with an Application Load Balancer
- **Lab Session:** Deletion of AWS ACM

## Day 25: AWS WAF (Web Application Firewall)
- What is WAF?
- How AWS WAF works
- Creating a Web ACL
- Applying the Web ACL to an ALB
- Blocking a Specific IP Address

## Day 26: AWS EFS (Elastic File System)
- What is AWS EFS?
- Use cases of AWS EFS
- Types of AWS EFS Storage Classes
- **Lab Session:** Creation of AWS EFS
- **Lab Session:** Mounting AWS EFS in an EC2 instance
- **Lab Session:** Deletion of AWS EFS

## Day 27: AWS Directory Service
- What is AWS Directory Service?
- AWS Directory Service options
- Getting started with AWS Managed Microsoft AD
- AWS Managed Microsoft AD prerequisites
- Create your AWS Managed Microsoft AD
- Deploy an Amazon EC2 instance to manage your AWS Managed Microsoft AD Active Directory
- Verify that the base test lab is operational

Reference link: [AWS Directory Service Guide](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ms_ad_tutorial_test_lab.html)

## Day 28: Final Preparations
- Resume Preparation
- Conducting Mock Interview
- Interview Questions and Answer
