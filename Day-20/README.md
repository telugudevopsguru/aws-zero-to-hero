#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### What is AWS KMS?

**AWS Key Management Service (KMS):** A managed service that makes it easy for you to create and control the encryption keys used to encrypt your data. It integrates with other AWS services to help you protect your data.

### Features and Benefits of AWS KMS

1. **Centralized Key Management:** Create, rotate, and manage encryption keys used across AWS services and your applications.
2. **Integration with AWS Services:** Seamlessly integrates with services like S3, EBS, RDS, and more for encryption at rest.
3. **Secure:** Uses hardware security modules (HSMs) to protect the security and integrity of your keys.
4. **Auditable:** Logs API calls made to KMS keys, providing visibility and compliance.
5. **Cost-Effective:** Pay only for what you use, with no upfront costs.

### Different Types of Keys in AWS KMS

1. **Customer Master Keys (CMKs):** Used to encrypt and decrypt data. Can be either symmetric or asymmetric.
   - **Symmetric CMKs:** Used for encrypting and decrypting data.
   - **Asymmetric CMKs:** Used for signing and verifying data.

2. **AWS Managed Keys:** KMS-managed keys that AWS creates, owns, and manages on your behalf for specific AWS services (e.g., S3, EBS).
----
### Lab Session - Creating a KMS Key

1. **Sign in to AWS Management Console:**
   - Navigate to the KMS Dashboard at [AWS Management Console](https://console.aws.amazon.com/kms/).

2. **Create KMS Key:**
   - Click on "Create key."
   - Choose whether you want to create a symmetric or asymmetric key.
   - Configure key settings (e.g., key alias, description).
   - Click "Next" and then "Finish."

3. **Take Note of Key ARN:**
   - Make a note of the key ARN (Amazon Resource Name) for later use.
----
### Lab Session - Encrypting an EBS Volume Using AWS KMS

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Encrypt EBS Volume:**
   - Create or select an existing EBS volume.
   - Modify the volume to enable encryption and choose the KMS key created earlier.
   - Apply the changes.

3. **Verify Encryption:**
   - Verify that the EBS volume is now encrypted using the selected KMS key.
----
### Lab Session - Deletion of KMS

1. **Sign in to AWS Management Console:**
   - Navigate to the KMS Dashboard at [AWS Management Console](https://console.aws.amazon.com/kms/).

2. **Delete KMS Key:**
   - Select the KMS key you want to delete.
   - Click "Delete key."
   - Follow the confirmation steps to delete the key.
----
### What is AWS SES?

**AWS Simple Email Service (SES):** A cloud-based email sending service designed to help digital marketers and application developers send marketing, notification, and transactional emails.

----
### Lab Session - Creating AWS SES

1. **Sign in to AWS Management Console:**
   - Navigate to the SES Dashboard at [AWS Management Console](https://console.aws.amazon.com/ses/).

2. **Verify Email Addresses or Domains:**
   - Before sending emails, verify email addresses or domains that you plan to use for sending.

3. **Send Test Emails:**
   - Use the SES console or API to send test emails to ensure configurations are correct.
----
### Lab Session - Deletion of AWS SES

1. **Sign in to AWS Management Console:**
   - Navigate to the SES Dashboard at [AWS Management Console](https://console.aws.amazon.com/ses/).

2. **Delete SES Configuration:**
   - Delete verified email addresses or domains.
   - Optionally, delete SES configurations and settings if no longer needed.
----
### What is AWS SNS?

Amazon Simple Notification Service (SNS) is a fully managed messaging service provided by AWS that enables the decoupling of microservices, distributed systems, and serverless applications. Here are the key features and components of SNS:

### Key Features
1. **Message Delivery**: SNS can deliver messages to a variety of endpoints, including email, SMS, HTTP/HTTPS endpoints, and AWS Lambda functions.
2. **Topic-Based**: Messages are published to topics, which are logical access points and communication channels.
3. **Scalability**: SNS can handle large volumes of messages and scale automatically to accommodate varying loads.
4. **Reliability**: It ensures high availability and durability of messages with multiple copies stored redundantly across multiple Availability Zones.
5. **Security**: Supports encryption at rest, and in-transit, and integrates with AWS Identity and Access Management (IAM) for fine-grained access control.

### Components
1. **Topics**: 
   - Central communication channels where messages are sent and subscribers receive them.
2. **Subscriptions**: 
   - Endpoints (e.g., email, SMS, HTTP/HTTPS, AWS Lambda) that receive messages published to topics.
3. **Publishers**: 
   - Entities that send messages to SNS topics.
4. **Subscribers**: 
   - Entities that receive messages from SNS topics based on their subscriptions.

### Use Cases
1. **Application Integration**: Decouple components of an application to improve modularity and scalability.
2. **Mobile Notifications**: Send push notifications to mobile devices.
3. **Email and SMS Alerts**: Send alerts and notifications via email or SMS to users or administrators.
4. **Event-Driven Computing**: Trigger AWS Lambda functions or other services in response to events.
----
### Lab Session - Creating AWS SNS

1. **Sign in to AWS Management Console:**
   - Navigate to the SNS Dashboard at [AWS Management Console](https://console.aws.amazon.com/sns/).

2. **Create a Topic:**
   - Click on "Create topic."
   - Enter a topic name and optionally configure other settings.
   - Click "Create topic."

3. **Subscribe Endpoints:**
   - Subscribe endpoints (e.g., email addresses, HTTP endpoints, Lambda functions) to the topic to receive notifications.

----
### Lab Session - Deletion of AWS SNS

1. **Sign in to AWS Management Console:**
   - Navigate to the SNS Dashboard at [AWS Management Console](https://console.aws.amazon.com/sns/).

2. **Delete SNS Topic:**
   - Select the SNS topic you want to delete.
   - Click "Delete topic."
   - Confirm the deletion.

