### What is AWS Systems Manager?

**AWS Systems Manager** (SSM) is a management service that helps you automatically collect software inventory, apply patches, create and deploy system images, configure operating systems (OSs), and automate many tasks across your Amazon EC2 instances and on-premises servers. It provides a unified user interface so you can view operational data from multiple AWS services, and it allows you to automate operational tasks across your AWS resources.

### Supported Operating Systems and Machine Types

AWS Systems Manager supports a wide range of operating systems, including:
- Amazon Linux
- Amazon Linux 2
- Ubuntu
- CentOS
- Red Hat Enterprise Linux (RHEL)
- Microsoft Windows Server (2008 R2 and later)

It is compatible with various machine types, including Amazon EC2 instances, on-premises servers, and virtual machines in other cloud environments.

### What is SSM Agent?

**SSM Agent** is a software agent installed and configured on Amazon EC2 instances, on-premises servers, or virtual machines that are managed by AWS Systems Manager. The SSM Agent processes requests from Systems Manager services and securely communicates with the Systems Manager API.

### Working with SSM Agent

SSM Agent enables the following capabilities:
- **Managed Instances:** Enables Systems Manager to manage your instances, including installing or removing software, running scripts, and configuring applications.
- **Run Command:** Allows you to remotely execute scripts or commands on your instances without needing to SSH into them.
- **State Manager:** Ensures your instances are configured per your desired state, enforcing configurations and applying updates automatically.
- **Inventory and Patch Management:** Collects metadata about your instances, installed applications, and patches, facilitating inventory management and patch deployments.

**Install SSM Agent on EC2 Instance:**
   - SSH into your EC2 instance.
   - Install the SSM Agent using the appropriate commands for your operating system.
### What is Parameter Store?

**Parameter Store** is a secure AWS service that provides hierarchical storage for configuration data and secrets management. It allows you to store and manage configuration data such as database strings, passwords, API keys, and other sensitive information.

### Creating the Parameter Store

To create a parameter in Parameter Store:
1. **Sign in to AWS Management Console:**
   - Navigate to the Parameter Store section of AWS Systems Manager.

2. **Create a Parameter:**
   - Click on "Create Parameter."
   - Enter a name and value for the parameter.
   - Choose the type of parameter (e.g., SecureString for sensitive data).
   - Configure any additional options such as encryption and tags.
   - Click "Create Parameter" to create the parameter.

### What is Run Command?

**Run Command** is a Systems Manager feature that allows you to remotely and securely execute commands on your managed instances. It provides a simple way to automate common administrative tasks across a large number of instances.

### Setting up Run Command

To use Run Command:
1. **Select Managed Instances:**
   - Choose the EC2 instances or on-premises servers where you want to execute commands.

2. **Execute Commands:**
   - Enter the commands or scripts you want to run.
   - Choose parameters such as timeout and execution options.

3. **Monitor Execution:**
   - View the status and output of command executions in the Systems Manager console.
   - Optionally, schedule recurring commands or target commands based on resource groups.

### What is Patch Manager?

**Patch Manager** is a Systems Manager capability that helps you automate the process of patching managed instances with security-related updates and other types of updates. It simplifies the patching process across different operating systems and machine types.

### Working with Patch Manager

Patch Manager allows you to:
- Automatically scan instances for missing patches.
- Schedule patching operations to keep instances up to date with the latest security patches.
- Define patch baselines to specify which patches should be applied and when.
- View compliance reports to track patching status and remediate non-compliant instances.

**Configuring Patch Manager:**
   - Navigate to AWS Systems Manager -> Patch Manager.
   - Click on "Patch Manager" in the left-hand menu.
   - Create a patch baseline specifying which patches should be applied.
   - Define the schedule for patching operations.
   - Apply the patch baseline to your instances.

### What is Secrets Manager?

**Secrets Manager** is an AWS service that helps you securely store, manage, and access sensitive information such as API keys, database passwords, and other credentials. It enables you to rotate, manage access, and audit usage of secrets throughout their lifecycle.

### Working with Secrets Manager

Secrets Manager allows you to:
- **Store Secrets:** Securely store sensitive information in Secrets Manager using key encryption.
- **Rotate Secrets:** Automatically rotate secrets periodically or manually to enhance security.
- **Access Controls:** Define fine-grained access policies to control who can access and manage secrets.
- **Integration:** Integrate with AWS services and third-party applications securely using secrets.

**Creating and Managing Secrets:**
   - Navigate to AWS Secrets Manager.
   - Click on "Store a new secret."
   - Enter the secret details (e.g., key-value pairs, secrets).
   - Configure rotation settings if needed.
   - Click "Next" and review the settings.
   - Click "Store" to create the secret.
