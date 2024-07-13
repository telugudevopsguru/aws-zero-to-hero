### What is AWS EBS?

- Amazon Elastic Block Store (EBS) is a high-performance block storage service designed for use with Amazon EC2 instances.
- It provides persistent block-level storage volumes that can be attached to EC2 instances. EBS volumes are highly available and reliable storage volumes that can be used for databases, file systems, or any other application requiring durable storage.

### Types of AWS EBS Volumes

Amazon Elastic Block Store (EBS) offers several types of volumes tailored to different performance and cost requirements. Here are the main types:

#### 1. General Purpose SSD (gp2)

- **Description**: Default EBS volume type, suitable for a wide variety of workloads.
- **Performance**:
  - Balanced price and performance.
  - Supports burstable IOPS up to 16,000 and throughput up to 250 MiB/s.
- **Use Cases**:
  - Small to medium-sized databases.
  - Development and test environments.
  - Boot volumes.

#### 2. Provisioned IOPS SSD (io1)

- **Description**: Designed for I/O-intensive workloads that require consistent and high performance.
- **Performance**:
  - Offers up to 64,000 IOPS and 1,000 MiB/s throughput.
  - Allows you to specify IOPS requirements.
- **Use Cases**:
  - Critical business applications.
  - Large relational databases (e.g., MySQL, PostgreSQL).
  - NoSQL databases (e.g., MongoDB, Cassandra).

#### 3. Throughput Optimized HDD (st1)

- **Description**: Optimized for frequently accessed, throughput-intensive workloads.
- **Performance**:
  - Provides up to 500 MiB/s throughput.
  - Lower cost per GB than SSD volumes.
- **Use Cases**:
  - Big data analytics.
  - Data warehouses.
  - Log processing.

#### 4. Cold HDD (sc1)

- **Description**: Designed for less frequently accessed workloads that are cost-sensitive.
- **Performance**:
  - Provides up to 250 MiB/s throughput.
  - Lowest cost per GB among EBS volume types.
- **Use Cases**:
  - Infrequent data access.
  - Scenarios where cost optimization is critical (e.g., backups, disaster recovery).

#### 5. Magnetic (standard)

- **Description**: Older generation EBS volume type, gradually being phased out.
- **Performance**:
  - Provides the lowest cost per GB of all EBS volume types.
  - Suitable for workloads with low I/O requirements.
- **Use Cases**:
  - Non-critical workloads.
  - Scenario where cost is the primary consideration over performance.

### Key Features of AWS EBS

- **Elasticity**: Volumes can be dynamically scaled in size and performance to meet changing application demands.
- **Durability**: Data is automatically replicated within an Availability Zone to protect against component failures.
- **Snapshotting**: Point-in-time snapshots enable backup and recovery of EBS volumes.
- **Encryption**: Volumes can be encrypted using AWS-managed or customer-managed keys for enhanced security.
- **Availability**: Available in all AWS regions, allowing attachment to instances within the same region.

----
### Lab Session - Creation of an EBS Volume

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Create EBS Volume:**
   - In the left sidebar, under "Elastic Block Store," click on "Volumes."
   - Click on "Create Volume" and configure the volume settings, including volume type, size, and Availability Zone.

3. **Create Volume:**
   - Review the configuration and click "Create Volume" to create the EBS volume.

### Lab Session - Attach an EBS Volume to a Linux EC2 Instance

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Attach EBS Volume:**
   - In the left sidebar, under "Elastic Block Store," click on "Volumes."
   - Select the EBS volume you want to attach and click "Actions > Attach Volume."
   - Choose the EC2 instance to attach the volume to and specify the device name (e.g., /dev/xvdf).

3. **Mount Volume:**
   - SSH into your Linux EC2 instance.
   - Use commands like `lsblk` to list available block devices and `sudo mkfs -t ext4 /dev/xvdf` to format the volume (if necessary).
   - Create a mount point (`sudo mkdir /mnt/data`) and mount the volume (`sudo mount /dev/xvdf /mnt/data`).

### Lab Session - Increase the Size of an Existing EBS Volume on a Linux EC2 Instance

1. **Resize EBS Volume:**
   - In the EC2 Dashboard, navigate to "Volumes."
   - Select the EBS volume you want to resize and click "Actions > Modify Volume."
   - Increase the size of the volume and click "Modify."

2. **Resize File System:**
   - SSH into your Linux EC2 instance.
   - Use `lsblk` to verify the new size of the volume.
   - Resize the file system on the volume (`sudo resize2fs /dev/xvdf`) to reflect the increased volume size.

### Lab Session - Attach an EBS Volume to a Windows EC2 Instance

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Attach EBS Volume:**
   - In the left sidebar, under "Elastic Block Store," click on "Volumes."
   - Select the EBS volume you want to attach and click "Actions > Attach Volume."
   - Choose the EC2 instance to attach the volume to and specify the device name (e.g., `\\.\D:`).

3. **Initialize and Format Volume:**
   - RDP into your Windows EC2 instance.
   - Open Disk Management (`diskmgmt.msc`), locate the new volume, and initialize and format it as needed.

### Lab Session - Increase the Size of an Existing EBS Volume on a Windows EC2 Instance

1. **Resize EBS Volume:**
   - In the EC2 Dashboard, navigate to "Volumes."
   - Select the EBS volume you want to resize and click "Actions > Modify Volume."
   - Increase the size of the volume and click "Modify."

2. **Extend Volume in Windows:**
   - RDP into your Windows EC2 instance.
   - Open Disk Management (`diskmgmt.msc`), right-click on the volume, and select "Extend Volume."
   - Follow the wizard to extend the volume using the unallocated space.

### Lab Session - Change the EBS Volume Type

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Modify EBS Volume Type:**
   - In the left sidebar, under "Elastic Block Store," click on "Volumes."
   - Select the EBS volume you want to modify and click "Actions > Modify Volume."
   - Choose the new volume type (e.g., from gp2 to io1) and click "Modify."

### Lab Session - Encrypt an Existing Attached EBS Volume

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Encrypt EBS Volume:**
   - In the left sidebar, under "Elastic Block Store," click on "Volumes."
   - Select the EBS volume you want to encrypt and click "Actions > Modify Volume."
   - Check the box for "Encrypt this volume" and select a KMS key for encryption.
   - Click "Modify" to start the encryption process.
