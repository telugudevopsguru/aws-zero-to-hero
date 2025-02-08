**1. Which of the following best describes AWS IAM?**

A. A service that monitors and logs API calls in your AWS account  
B. A tool that automatically scales EC2 instances  
C. A web service for securely managing access to AWS resources  
D. A database service for storing user credentials

**Correct Answer:** C. A web service for securely managing access to AWS resources  
**Explanation:** AWS Identity and Access Management (IAM) enables you to manage users, groups, roles, and policies to control who can access your AWS resources and under what conditions.

---

**2. Which feature is a core benefit of AWS IAM?**

A. Centralized access management with fine-grained control  
B. Automated cost optimization for EC2 instances  
C. Integrated data warehousing and analytics  
D. Automatic deployment of containerized applications

**Correct Answer:** A. Centralized access management with fine-grained control  
**Explanation:** AWS IAM allows centralized management of permissions, letting you define specific policies that precisely control access to AWS resources for users and services.

---

**3. In a lab session focused on creating AWS IAM users, what is one of the primary pieces of information you must provide?**

A. The IAM user's name and credentials (password and/or access keys)  
B. The subnet ID for the IAM user  
C. The EC2 instance type for the IAM user  
D. The S3 bucket name associated with the IAM user

**Correct Answer:** A. The IAM user's name and credentials (password and/or access keys)  
**Explanation:** When creating an IAM user, you need to assign a unique name and create credentials (password for console access and/or access keys for programmatic access).

---

**4. What is the main purpose of creating IAM user groups in AWS?**

A. To deploy EC2 instances in batches  
B. To centrally manage permissions for multiple users with similar job functions  
C. To configure VPC security settings for users  
D. To automatically monitor user activity in CloudWatch

**Correct Answer:** B. To centrally manage permissions for multiple users with similar job functions  
**Explanation:** IAM user groups enable you to assign the same policies and permissions to many users at once, simplifying management and ensuring consistent access control.

---

**5. Which statement best defines an AWS IAM policy?**

A. A document that specifies who can access which AWS resources and under what conditions  
B. A configuration file used to launch EC2 instances  
C. A dashboard for tracking AWS spending  
D. A tool for monitoring network traffic in your VPC

**Correct Answer:** A. A document that specifies who can access which AWS resources and under what conditions  
**Explanation:** IAM policies are JSON documents that define permissions by listing allowed or denied actions on AWS resources under specified conditions.

---

**6. Which of the following is a type of AWS IAM policy?**

A. Inline Policy  
B. Instance Policy  
C. Container Policy  
D. Network Policy

**Correct Answer:** A. Inline Policy  
**Explanation:** AWS IAM supports two main types of policies: managed policies (AWS-managed or customer-managed) and inline policies, which are directly attached to a single user, group, or role.

---

**7. During a lab session on configuring the AWS CLI, which of the following is typically configured?**

A. EC2 instance launch configurations  
B. Access keys, secret keys, region, and default output format  
C. VPC routing tables  
D. CloudFormation stack parameters

**Correct Answer:** B. Access keys, secret keys, region, and default output format  
**Explanation:** Configuring the AWS CLI involves setting up your credentials (access key and secret key), your default region, and your output format to interact with AWS services from the command line.

---

**8. What is the benefit of using named profiles in the AWS CLI?**

A. They allow for simultaneous logins to multiple AWS accounts with different sets of credentials.  
B. They automatically enable Multi-Factor Authentication (MFA) for all sessions.  
C. They ensure that all AWS CLI commands run faster.  
D. They create an audit log for every CLI command executed.

**Correct Answer:** A. They allow for simultaneous logins to multiple AWS accounts with different sets of credentials.  
**Explanation:** Named profiles let you store separate configurations and credentials for different AWS accounts or roles, making it easier to switch contexts when using the AWS CLI.

---

**9. Which of the following best describes an IAM role?**

A. A type of IAM user with permanent credentials  
B. A set of permissions that can be assumed by trusted entities such as users, applications, or services  
C. A dedicated EC2 instance that manages access control  
D. A CloudWatch configuration for monitoring IAM activities

**Correct Answer:** B. A set of permissions that can be assumed by trusted entities such as users, applications, or services  
**Explanation:** IAM roles are designed to be assumed by trusted entities (including AWS services) to obtain temporary security credentials, allowing them to access AWS resources without sharing long-term credentials.

---

**10. In a lab session on attaching an IAM role to an EC2 instance, which step is typically performed?**

A. Configuring the VPC route tables for the instance  
B. Launching the EC2 instance with an associated IAM instance profile  
C. Directly embedding IAM credentials into the EC2 instance's code  
D. Assigning a static public IP address to the instance

**Correct Answer:** B. Launching the EC2 instance with an associated IAM instance profile  
**Explanation:** When you attach an IAM role to an EC2 instance, you do so via an instance profile that is linked to the role, either during the instance launch process or by associating it with a running instance.

---

**11. What is a key difference between the AWS root account and an IAM user?**

A. The root account is used solely for billing and cannot access AWS resources.  
B. An IAM user can have permissions limited by policies, whereas the root account has full, unrestricted access.  
C. IAM users are only for temporary access, while the root account is permanent.  
D. The root account cannot be used to manage AWS services.

**Correct Answer:** B. An IAM user can have permissions limited by policies, whereas the root account has full, unrestricted access.  
**Explanation:** AWS best practices recommend using the root account only for a few necessary tasks, and instead creating IAM users with limited, role-specific permissions for everyday operations.

---

**12. During a lab session on AWS IAM Password Policy, what is typically configured?**

A. The rules for password complexity, length, and expiration for IAM users  
B. The encryption methods for S3 bucket access  
C. The default EC2 instance type  
D. The configuration for automated scaling of resources

**Correct Answer:** A. The rules for password complexity, length, and expiration for IAM users  
**Explanation:** An IAM Password Policy defines the minimum requirements for IAM user passwords, such as minimum length, use of numbers or symbols, and password expiration rules, enhancing account security.

---

**13. Why is enabling Multi-Factor Authentication (MFA) for AWS IAM users considered a best practice?**

A. It allows for faster login times.  
B. It provides an extra layer of security by requiring a second form of authentication in addition to the password.  
C. It automatically encrypts all user data.  
D. It replaces the need for IAM policies.

**Correct Answer:** B. It provides an extra layer of security by requiring a second form of authentication in addition to the password.  
**Explanation:** MFA helps protect user accounts by requiring a second authentication factor (such as a time-based one-time password from a mobile device), reducing the risk of unauthorized access even if passwords are compromised.

---

**14. Which of the following is considered an AWS IAM best practice?**

A. Using the root account for all administrative tasks  
B. Sharing IAM user credentials among team members for convenience  
C. Regularly reviewing and applying the principle of least privilege to IAM policies  
D. Disabling CloudTrail to reduce logging overhead

**Correct Answer:** C. Regularly reviewing and applying the principle of least privilege to IAM policies  
**Explanation:** AWS recommends that you grant only the minimum permissions necessary for users to perform their tasks and review policies regularly, while also enabling security features such as MFA to strengthen overall account security.

---

**15. Which IAM feature allows you to simulate the effect of a policy before applying it to an IAM user or group?**

A. IAM Access Advisor  
B. IAM Credential Report  
C. IAM Policy Simulator  
D. IAM Role Tester

**Correct Answer:** C. IAM Policy Simulator  
**Explanation:** The IAM Policy Simulator enables you to test and troubleshoot policies by simulating policy evaluation for a user, group, or role before applying them in production.

---

**16. Which of the following is considered a best practice when using the AWS root account?**

A. Use the root account for everyday administrative tasks.  
B. Store the root account access keys in source control for easy access.  
C. Enable Multi-Factor Authentication (MFA) on the root account and limit its usage.  
D. Share root account credentials with team members to streamline operations.

**Correct Answer:** C. Enable Multi-Factor Authentication (MFA) on the root account and limit its usage.  
**Explanation:** AWS recommends securing the root account with MFA and using it sparingly—only for tasks that require unrestricted access—while relying on IAM users for daily operations.

---

**17. Which type of IAM policy is designed to be reused and attached to multiple IAM entities such as users, groups, and roles?**

A. Inline Policy  
B. Managed Policy  
C. Temporary Policy  
D. Embedded Policy

**Correct Answer:** B. Managed Policy  
**Explanation:** Managed policies (whether AWS-managed or customer-managed) are designed to be reusable and can be attached to multiple IAM identities, simplifying permission management across your AWS environment.

---

**18. In a lab session on configuring named profiles for the AWS CLI, where is the profile information typically stored?**

A. In a JSON file within the IAM console.  
B. In the EC2 instance metadata.  
C. In the AWS configuration file (commonly located at `~/.aws/config`).  
D. In the CloudFormation template for your infrastructure.

**Correct Answer:** C. In the AWS configuration file (commonly located at `~/.aws/config`).  
**Explanation:** Named profiles are configured in the AWS CLI configuration file, allowing you to manage multiple sets of credentials and settings (such as region and output format) for different accounts or roles.

---

**19. When attaching an IAM role to an EC2 instance using an instance profile, what is the primary benefit?**

A. The instance automatically installs the AWS CLI.  
B. The instance receives temporary credentials securely without embedding long-term access keys.  
C. The instance's performance is boosted by dedicated IAM processing.  
D. The instance is automatically backed up to S3.

**Correct Answer:** B. The instance receives temporary credentials securely without embedding long-term access keys.  
**Explanation:** Attaching an IAM role via an instance profile provides the EC2 instance with temporary security credentials, enhancing security by eliminating the need to store long-term credentials on the instance.

---

**20. Which AWS IAM feature provides detailed information about the status of credentials (e.g., last used time, password status, access key status) for IAM entities?**

A. IAM Access Analyzer  
B. IAM Credential Report  
C. IAM Policy Simulator  
D. IAM Role Inspector

**Correct Answer:** B. IAM Credential Report  
**Explanation:** The IAM Credential Report offers a comprehensive overview of your IAM entities and their credentials, helping you monitor and audit password usage, access key activity, and potential security issues.

---

**21. In a lab session on AWS IAM Users, what is a recommended step immediately after creating a new IAM user?**

A. Attach a broad inline policy that grants full access to all AWS services.  
B. Immediately add the user to a group that has pre-defined, least-privilege permissions.  
C. Generate and share the user’s access keys with all team members for redundancy.  
D. Disable console access to ensure the user works only via API calls.

**Correct Answer:** B. Immediately add the user to a group that has pre-defined, least-privilege permissions.  
**Explanation:** Grouping IAM users under a common set of permissions (using the principle of least privilege) simplifies management and ensures consistency in access controls.

---

**22. Which of the following practices is NOT recommended as part of IAM best practices?**

A. Granting only the minimum permissions necessary for users to perform their tasks.  
B. Regularly rotating credentials and enforcing strong password policies.  
C. Using the root account for all daily administrative tasks.  
D. Enabling MFA for highly privileged accounts.

**Correct Answer:** C. Using the root account for all daily administrative tasks.  
**Explanation:** It is a best practice to avoid using the root account for routine tasks; instead, use IAM users with appropriate permissions and reserve the root account for a minimal set of operations.

