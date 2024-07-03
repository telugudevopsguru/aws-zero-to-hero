### What is an Elastic IP?

An Elastic IP (EIP) is a static IPv4 address designed for dynamic cloud computing. It is associated with your AWS account rather than a specific instance, allowing you to quickly remap it to another instance within your AWS infrastructure.

### Lab Session - Creating an Elastic IP and Attaching it to an EC2 Instance

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Allocate Elastic IP:**
   - In the left sidebar, under "Network & Security," click on "Elastic IPs."
   - Click on "Allocate Elastic IP address" and allocate a new one if you don't have one already.

3. **Associate Elastic IP:**
   - Select the Elastic IP you just allocated and click on "Actions > Associate Elastic IP address."
   - Choose the instance you want to associate it with and confirm.

4. **Verify Association:**
   - Check the EC2 instance details to ensure the Elastic IP is successfully associated.

### What is a Security Group?

A Security Group acts as a virtual firewall for your EC2 instances to control inbound and outbound traffic. You define rules that specify the type of traffic allowed or denied to your instances.

### Lab Session - Creating a Security Group and Attaching it to an EC2 Instance

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Create Security Group:**
   - In the left sidebar, under "Network & Security," click on "Security Groups."
   - Click on "Create Security Group" and provide a name, description, and VPC.

3. **Configure Inbound Rules:**
   - Define inbound rules to allow specific types of traffic (e.g., SSH, HTTP, HTTPS).
   - Click "Add Rule" for each rule and specify the protocol, port range, and source (IP address or CIDR block).

4. **Configure Outbound Rules:**
   - Define outbound rules to control the traffic leaving your instance.

5. **Associate Security Group:**
   - Select the EC2 instance you want to associate with this security group.
   - Click on "Actions > Networking > Change Security Groups" and select the newly created security group.

6. **Verify Security Group:**
   - Verify that the security group is successfully associated with your EC2 instance.

### Spot Instances, On-Demand Instances, Savings Plans, Reserved Instances, Dedicated Hosts, Scheduled Instances, Capacity Reservations

These are different pricing and provisioning models in AWS:

- **Spot Instances:** Bid for spare Amazon EC2 computing capacity at a discount compared to On-Demand prices.
- **On-Demand Instances:** Pay for compute capacity by the hour or second with no long-term commitments.
- **Savings Plans:** Flexible pricing model that offers significant savings on EC2 and AWS Fargate usage.
- **Reserved Instances:** Reserve capacity for one or three years in exchange for a lower hourly rate.
- **Dedicated Hosts:** Physical servers dedicated to your use to help meet compliance requirements.
- **Scheduled Instances:** Launch instances that run on a recurring schedule.
- **Capacity Reservations:** Reserve capacity in an AWS region to ensure it's available when needed.

### Lab Session - Opening a Support Ticket with AWS

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS Support Center at [AWS Support Center](https://console.aws.amazon.com/support/).

2. **Open Support Ticket:**
   - Click on "Create case" to open a new support ticket.
   - Choose the appropriate service category and describe your issue or request.

3. **Provide Details:**
   - Fill in the required fields, including contact information, severity level, and a detailed description of your issue.

4. **Submit Ticket:**
   - Review the information and submit the ticket. Note down the case ID for reference.

### Lab Session - Requesting Service Quotas in AWS

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS Service Quotas Dashboard at [AWS Service Quotas](https://console.aws.amazon.com/servicequotas/).

2. **View Service Quotas:**
   - Browse through the available service quotas for different AWS services.

3. **Request Increase:**
   - Select a quota and click on "Request quota increase."
   - Fill out the request form, including details such as the desired limit increase and the reason for the request.

4. **Submit Request:**
   - Submit the request for AWS to review. Monitor the request status in the Service Quotas dashboard.

### Lab Session - Metadata and User Data in EC2

- **Metadata:** EC2 instance metadata provides information about the instance itself, such as instance ID, instance type, public IP address, and more. Metadata is accessible from within the instance using a special endpoint (`http://169.254.169.254/latest/meta-data/`).

- **User Data:** User data allows you to pass startup scripts or configuration to your EC2 instances when they are launched. This can be used to automate instance configuration tasks, install software, or run custom scripts during instance initialization.
