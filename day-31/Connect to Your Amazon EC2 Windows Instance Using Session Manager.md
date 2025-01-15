# Connect to Your Amazon EC2 Windows Instance Using Session Manager

- **SSM Session Manager** is a feature of AWS Systems Manager that allows you to securely connect to and manage EC2 instances without needing SSH, RDP, or open inbound ports.
- It provides encrypted, auditable access to your instances through the AWS Management Console or CLI.
- You don’t need to expose your instances to the internet, and all actions are logged for security and compliance.
- It also integrates with AWS IAM to control access and supports both Linux and Windows instances.

Key Benefits:
- **Secure**: No need for SSH keys or open ports.
- **Auditable**: All sessions are logged.
- **Simple**: Access via the AWS Console or CLI without third-party tools.
- **Cost-effective**: Eliminates the need for bastion hosts.

