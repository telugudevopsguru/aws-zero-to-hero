### AWS Elastic IP (EIP)

AWS Elastic IP (EIP) is a static, public IP address that can be allocated to your AWS resources, such as Amazon EC2 instances, to enable communication with the internet.

#### Key Features and Benefits:

1. **Static IP Address**
   - Unlike dynamic IP addresses that can change when an instance is stopped or started, an EIP remains constant.

2. **Persistent Association**
   - An EIP remains associated with your AWS account until you choose to release it, ensuring continuity of services and reliable access.

3. **Flexibility**
   - EIPs can be remapped to another instance within your account, allowing you to quickly recover from instance or availability zone failures.

4. **Availability**
   - EIPs enable your AWS resources to have a fixed public IP address, facilitating communication with the internet or external systems.

#### Use Cases:

1. **Web Hosting**
   - Assign an EIP to your EC2 instance running a web server to ensure users can reliably access your website.

2. **Disaster Recovery**
   - Quickly remap an EIP to a standby instance in case of failure, minimizing downtime and ensuring business continuity.

3. **Dynamic DNS**
   - Use an EIP with dynamic DNS services to maintain consistent access to applications even when underlying instances change.

#### Important Considerations:

- **Cost**
  - While EIPs themselves are free, AWS charges you if an EIP is associated with a stopped instance or not associated with any instance.

- **Limits**
  - AWS limits the number of EIPs you can have per region. You can request an increase if necessary.

- **Best Practices**
  - Use EIPs sparingly and release them when no longer needed to avoid unnecessary charges.

#### How to Allocate and Associate an EIP:

1. **Allocate an EIP**:
   - In the AWS Management Console, go to the EC2 Dashboard.
   - Click on "Elastic IPs" in the sidebar.
   - Click the "Allocate new address" button and confirm.

2. **Associate an EIP with an EC2 Instance**:
   - Select the allocated EIP.
   - Click on the "Actions" dropdown and select "Associate address."
   - Choose the instance or network interface you want to associate the EIP with, and confirm the association.

--
### AWS Security Groups

A security group acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic.

#### Key Features and Benefits:

1. **Inbound and Outbound Rules**
   - **Inbound Rules**: Control the incoming traffic to your instance.
   - **Outbound Rules**: Control the outgoing traffic from your instance.

2. **Default Security Group**
   - If you don't specify a security group when you launch an instance, Amazon EC2 uses the default security group.

3. **Flexible Rule Management**
   - You can add, modify, or remove rules in a security group at any time.
   - New and modified rules are automatically applied to all instances associated with the security group.

4. **Multiple Security Groups**
   - You can specify one or more security groups when you launch an instance.
   - Amazon EC2 evaluates all rules from all security groups associated with an instance to decide whether to allow traffic.

#### How Security Groups Work:

- **Creating Security Groups**:
  - In the AWS Management Console, go to the EC2 Dashboard.
  - Click on "Security Groups" in the sidebar.
  - Click the "Create security group" button and define the group name, description, and VPC.
  - Add inbound and outbound rules as needed.

- **Inbound and Outbound Rules**:
  - **Inbound Rules**: Define which traffic is allowed to reach your instance. Example: Allow SSH access on port 22 from a specific IP range.
  - **Outbound Rules**: Define which traffic is allowed to leave your instance. Example: Allow all outbound traffic to any destination.

- **Modifying Security Groups**:
  - Select the security group you want to modify.
  - Add, edit, or remove inbound and outbound rules as necessary.
  - Changes are automatically applied to all associated instances.

#### Example Use Cases:

1. **Web Servers**:
   - Allow inbound HTTP (port 80) and HTTPS (port 443) traffic from anywhere.
   - Allow SSH (port 22) access only from a specific IP address or range.

2. **Database Servers**:
   - Allow inbound traffic only from specific application servers.
   - Restrict outbound traffic to limit external connections.

3. **Application Servers**:
   - Allow inbound traffic on specific ports required by the application.
   - Allow outbound traffic to databases and other services.

#### Important Considerations:

- **Stateful Nature**:
  - Security groups are stateful, meaning if you allow an incoming request from an IP, the response is automatically allowed.

- **Evaluation of Rules**:
  - When Amazon EC2 decides whether to allow traffic to reach an instance, it evaluates all of the rules from all of the security groups associated with the instance.

- **Changes Applied Automatically**:
  - Any changes to security group rules are immediately applied to all associated instances without needing to restart them.

By effectively managing security groups, you can enhance the security of your AWS environment by controlling access to and from your EC2 instances.
--
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
