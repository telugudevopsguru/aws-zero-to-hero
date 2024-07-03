### What is AWS EBS?

Amazon Elastic Block Store (EBS) is a high-performance block storage service designed for use with Amazon EC2 instances. It provides persistent block-level storage volumes that can be attached to EC2 instances. EBS volumes are highly available and reliable storage volumes that can be used for databases, file systems, or any other application requiring durable storage.

### Features of AWS EBS

1. **High Performance:** EBS volumes offer low-latency performance needed for a variety of workloads.
2. **Durability:** Data on EBS volumes is replicated within the same Availability Zone to protect against component failure.
3. **Snapshots:** EBS volumes can be backed up using point-in-time snapshots for data protection and disaster recovery.
4. **Encryption:** EBS volumes support encryption at rest to help meet compliance requirements and secure data.
5. **Scalability:** Easily increase the size or performance of EBS volumes to meet changing application requirements.

### Types of EBS Volumes

AWS offers several types of EBS volumes optimized for different use cases:

1. **General Purpose SSD (gp2):** Suitable for a broad range of workloads, providing balanced price and performance.
2. **Provisioned IOPS SSD (io1):** Designed for I/O-intensive workloads requiring high performance with consistent and low-latency I/O.
3. **Throughput Optimized HDD (st1):** Low-cost HDD volume designed for frequently accessed, throughput-intensive workloads.
4. **Cold HDD (sc1):** Lowest cost HDD volume designed for less frequently accessed workloads.
5. **Magnetic (standard):** Previous generation HDD volume for workloads where data is accessed infrequently.

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
