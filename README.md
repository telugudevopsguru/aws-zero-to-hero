### What is AWS IAM?

AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS services and resources for your users. IAM enables you to manage users, groups, roles, and permissions to securely access AWS resources.

### Features of AWS IAM

1. **Centralized Control:** Manage access centrally for AWS accounts.
2. **Shared Access:** Grant permissions to users, groups, or roles as needed.
3. **Granular Permissions:** Define fine-grained permissions using policies.
4. **Multi-Factor Authentication (MFA):** Add an extra layer of security.
5. **Identity Federation:** Integrate with existing corporate directories.
6. **Identity Information:** Manage user identities and their permissions.

### What is AWS IAM User 

1. **Definition**: Represents an individual with unique credentials to access AWS services and resources.
2. **Credentials**: Assigned a username, password, access keys, or multi-factor authentication (MFA) device.
3. **Permissions**: Managed through policies that define allowed or denied actions on AWS resources.
4. **Access Management**: Permissions are specific to each user, allowing fine-grained control over access.
5. **Usage**: Typically used to grant access to AWS resources to individuals such as employees or contractors.
6. **Security**: Users can have their access credentials and permissions managed independently.

### Lab Session - AWS IAM Users

1. **Sign in to AWS Management Console:**
   - Navigate to the IAM Dashboard at [AWS Management Console](https://console.aws.amazon.com/iam/).

2. **Create IAM User:**
   - Click on "Users" in the left sidebar and then "Add user."
   - Enter a username and select access type (programmatic access, AWS Management Console access, or both).
   - Set permissions by adding the user to groups or attaching policies directly.
   - Complete the user creation and note down the access credentials.
----
### AWS IAM User Groups

1. **Definition**: A collection of IAM users for easier permission management.
2. **Permissions**: Permissions are assigned to groups rather than to individual users.
3. **Simplifies Management**: Users can be added to or removed from groups, inheriting permissions automatically.
4. **Efficiency**: Reduces administrative overhead by applying permissions at the group level.
5. **Flexibility**: Users can belong to multiple groups, inheriting permissions from all groups they are part of.
6. **Scalability**: Ideal for organizations managing access for multiple users with similar roles or permissions needs.
   
### Lab Session - AWS IAM User Groups

1. **Sign in to AWS Management Console:**
   - Navigate to the IAM Dashboard at [AWS Management Console](https://console.aws.amazon.com/iam/).

2. **Create IAM Group:**
   - Click on "Groups" in the left sidebar and then "Create group."
   - Enter a group name and attach policies to define permissions for the group.
   - Add IAM users to the group to inherit the group's permissions.
----
### What are AWS IAM Policies?

IAM policies are JSON documents that define permissions allowing or denying actions on AWS resources. They are attached to IAM identities (users, groups, roles) and control what actions these identities can perform.

### Types of AWS IAM Policies

1. **Managed Policies:** AWS-managed policies created and managed by AWS.
2. **Inline Policies:** Policies that you create and manage directly within an IAM identity (user, group, role).
3. **Custom Policies:** Policies tailored to specific needs and attached to IAM identities.

### Lab Session - Configuring AWS CLI

1. **Install AWS CLI:**
   - Install AWS CLI on your local machine. Instructions vary based on your operating system; refer to AWS documentation for detailed steps.

2. **Configure AWS CLI:**
   - Open a terminal or command prompt.
   - Run `aws configure` and enter your AWS Access Key ID, Secret Access Key, default region, and output format (optional).

### Lab Session - Named Profiles for the AWS CLI

1. **Edit AWS CLI Configuration:**
   - Open or create the AWS CLI configuration file (`~/.aws/config` or `%UserProfile%\.aws\config` on Windows).
   - Add a new profile under `[profile profile_name]` with `aws_access_key_id`, `aws_secret_access_key`, `region`, and `output` parameters.

2. **Use Named Profile:**
   - Specify the named profile with `--profile profile_name` parameter in AWS CLI commands (e.g., `aws s3 ls --profile profile_name`).

### What is an IAM Role?

An IAM role is an AWS identity with permissions to access AWS services and resources. It is used to delegate access to users, applications, or services that don’t normally have access to AWS resources.

### Lab Session - How to Attach the IAM Role to an EC2 Instance?

1. **Sign in to AWS Management Console:**
   - Navigate to the IAM Dashboard at [AWS Management Console](https://console.aws.amazon.com/iam/).

2. **Create IAM Role:**
   - Click on "Roles" in the left sidebar and then "Create role."
   - Select the type of trusted entity (AWS service, another AWS account, etc.).
   - Choose the use case policy (e.g., EC2) to define permissions.
   - Complete the role creation.

3. **Attach IAM Role to EC2 Instance:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).
   - Select the EC2 instance you want to attach the IAM role to.
   - Click on "Actions > Security > Modify IAM role" and select the IAM role you created.
   - Apply the changes to attach the IAM role to the EC2 instance.

### Root Account vs IAM User

- **Root Account:** The AWS account created when you first sign up with AWS. It has unrestricted access to all AWS resources and services.
- **IAM User:** Users created within an AWS account with defined permissions and access control. IAM users should be used instead of the root account for day-to-day activities to follow the principle of least privilege.

### Lab Session - AWS IAM Password Policy

1. **Sign in to AWS Management Console:**
   - Navigate to the IAM Dashboard at [AWS Management Console](https://console.aws.amazon.com/iam/).

2. **Configure Password Policy:**
   - Click on "Account settings" in the left sidebar.
   - Click on "Change password policy" to define requirements such as minimum length, complexity, and expiration.

### Lab Session - Multi-Factor Authentication (MFA) for AWS IAM

1. **Sign in to AWS Management Console:**
   - Navigate to the IAM Dashboard at [AWS Management Console](https://console.aws.amazon.com/iam/).

2. **Enable MFA:**
   - Click on "Users" in the left sidebar and select the IAM user.
   - Click on the "Security credentials" tab and locate "Assigned MFA device."
   - Follow the instructions to configure and activate MFA using a hardware device or virtual MFA app.

### IAM Best Practices

- **Use IAM Roles:** Instead of long-term access keys for applications.
- **Implement Least Privilege:** Grant only necessary permissions to users, groups, and roles.
- **Regularly Rotate Credentials:** Change passwords and access keys periodically.
- **Enable MFA:** Add an extra layer of security for user accounts.
- **Monitor and Audit:** Review IAM policies, roles, and permissions regularly.
  
