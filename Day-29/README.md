#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### What is AWS Directory Service?

- AWS Directory Service is a managed service provided by Amazon Web Services (AWS) that enables you to set up and run directories in the AWS Cloud.
- It offers multiple directory options, including AWS Managed Microsoft AD, Simple AD, and AD Connector, to integrate with your on-premises directories and to manage your AWS resources more efficiently.

### AWS Directory Service Options

1. **AWS Managed Microsoft AD:**
   - A fully managed Active Directory (AD) service that provides the same features and capabilities as an on-premises Microsoft AD.
   - Supports AWS applications and services that require AD.
   - Allows you to extend your on-premises AD to the AWS Cloud.

2. **Simple AD:**
   - A cost-effective, standalone directory powered by Samba 4.
   - Suitable for small to medium-sized businesses that need basic AD features.

3. **AD Connector:**
   - A directory gateway that connects your on-premises Microsoft Active Directory to AWS.
   - Allows you to proxy authentication requests to your on-premises AD without caching any information in the cloud.

### Getting Started with AWS Managed Microsoft AD

#### AWS Managed Microsoft AD Prerequisites

1. **AWS Account:**
   - Ensure you have an AWS account with the necessary permissions to create and manage directory services.

2. **VPC Configuration:**
   - Set up a Virtual Private Cloud (VPC) with at least two subnets in different Availability Zones.
   - Ensure that your VPC has the required network configuration for AD, including DNS settings.

#### Create Your AWS Managed Microsoft AD

1. **Navigate to the AWS Directory Service Console:**
   - Open the AWS Management Console.
   - Go to the AWS Directory Service section.

2. **Create a Directory:**
   - Click on "Set up Directory."
   - Choose "AWS Managed Microsoft AD" and click "Next."

3. **Configure Directory Details:**
   - Provide a directory name, short name, and description.
   - Set the Admin password and confirm it.

4. **Select VPC and Subnets:**
   - Choose the VPC and subnets where you want to deploy your directory.
   - Ensure the subnets are in different Availability Zones.

5. **Review and Create:**
   - Review the configuration details.
   - Click "Create Directory."

6. **Directory Creation Process:**
   - AWS will start creating your directory, which may take several minutes.
   - Once created, the directory status will change to "Active."

#### Deploy an Amazon EC2 Instance to Manage Your AWS Managed Microsoft AD

1. **Launch an EC2 Instance:**
   - Go to the EC2 section in the AWS Management Console.
   - Click "Launch Instance."

2. **Configure Instance Details:**
   - Choose an AMI (Amazon Machine Image) suitable for your needs (e.g., Windows Server 2019).
   - Select an instance type.
   - Configure instance details, ensuring it is launched in the same VPC and subnet as your AWS Managed Microsoft AD.

3. **Configure Security Group:**
   - Create a security group with the necessary inbound rules for RDP (Remote Desktop Protocol) and any other required ports.

4. **Add Storage and Tags:**
   - Configure storage and add tags as needed.

5. **Review and Launch:**
   - Review the instance configuration.
   - Click "Launch" and select an existing key pair or create a new one.

6. **Connect to the EC2 Instance:**
   - Once the instance is running, connect to it using RDP.

#### Verify that the Base Test Lab is Operational

1. **Join the EC2 Instance to the Directory:**
   - On the EC2 instance, open "Server Manager."
   - Navigate to "Local Server" and click on "WORKGROUP" to join the instance to the domain.
   - Enter the domain name and directory administrator credentials.

2. **Verify Domain Join:**
   - Restart the EC2 instance.
   - Log in using the directory administrator account.

3. **Verify Directory Functionality:**
   - Open the "Active Directory Users and Computers" console.
   - Check that the directory structure is visible and functional.

4. **Test Directory Operations:**
   - Create test users and groups.
   - Assign permissions and test logins to verify that the directory is operational.
