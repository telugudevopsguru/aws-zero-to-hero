### **Userdata**

**What is it?**
- **Userdata** refers to a script or configuration passed to an EC2 instance during its launch.
- It is often used to perform automated actions when an instance starts for the first time.

**How does it work?**
- The script is executed by the cloud-init service (on Linux instances) or EC2Config/EC2Launch (on Windows instances).
- The execution occurs only during the first boot.

**Common Use Cases:**
1. **Install Software**: Automatically install packages or applications.
2. **Run Commands**: Execute initialization scripts, such as setting up a web server or database.
3. **Configuration**: Apply specific configurations, such as creating a user or modifying system settings.
4. **Download Files**: Retrieve files or dependencies from the internet or S3 buckets.

**Example:**
Auto-Tag EC2 Instance Using User Data Script:
```bash
#!/bin/bash

# Update the package index
yum update -y

# Fetch the instance ID from metadata
INSTANCE_ID=$(curl -s -H "X-aws-ec2-metadata-token: $(curl -s -X PUT -H "X-aws-ec2-metadata-token-ttl-seconds: 21600" http://169.254.169.254/latest/api/token)" http://169.254.169.254/latest/meta-data/instance-id)

# Fetch the region from metadata
REGION=$(curl -s -H "X-aws-ec2-metadata-token: $(curl -s -X PUT -H "X-aws-ec2-metadata-token-ttl-seconds: 21600" http://169.254.169.254/latest/api/token)" http://169.254.169.254/latest/meta-data/placement/region)

# Define the tag value
TAG_VALUE="ldev-eks-$INSTANCE_ID"

# Set the tag for the instance
aws ec2 create-tags --resources $INSTANCE_ID --tags Key=Name,Value=$TAG_VALUE --region $REGION
```

---

### **Metadata**

**What is it?**
- **Metadata** refers to instance-specific information that is available from within the instance itself.
- AWS provides this through a special metadata service accessible at `http://169.254.169.254/latest/meta-data/`.

**How does it work?**
- Metadata is not passed to the instance like userdata; instead, the instance retrieves it by making HTTP requests to the metadata service.

**Common Use Cases:**
1. **Retrieve Instance Information**: Such as instance ID, IP address, AMI ID, or region.
2. **Dynamic Configuration**: Use metadata to configure the instance dynamically based on its environment.
3. **IAM Role Credentials**: Access temporary security credentials for AWS services when using an instance profile (IAM role).

**Example Metadata Categories:**
- `ami-id`: AMI ID of the instance.
- `instance-id`: Unique ID of the instance.
- `public-ipv4`: Public IP address assigned to the instance.
- `security-groups`: Security groups associated with the instance.

**Retrieving Metadata Example:**
To get the instance ID:
```bash
curl http://169.254.169.254/latest/meta-data/instance-id
```

---

### Key Differences

| Aspect          | Userdata                                 | Metadata                                    |
|------------------|------------------------------------------|--------------------------------------------|
| Purpose          | Provide initialization scripts          | Retrieve instance-specific information     |
| Execution        | Run once at the first boot              | Accessed dynamically during runtime        |
| Scope            | Custom scripts or configurations        | Built-in AWS-provided instance details     |
| Accessibility    | Passed during instance launch           | Retrieved via HTTP calls inside the instance |
