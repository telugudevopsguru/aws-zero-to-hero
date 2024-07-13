### What is AWS EBS?

- Amazon Elastic Block Store (EBS) is a high-performance block storage service designed for use with Amazon EC2 instances.
- It provides persistent block-level storage volumes that can be attached to EC2 instances. EBS volumes are highly available and reliable storage volumes that can be used for databases, file systems, or any other application requiring durable storage.

### Key Features of AWS EBS

- **Elasticity**: Volumes can be dynamically scaled in size and performance to meet changing application demands.
- **Durability**: Data is automatically replicated within an Availability Zone to protect against component failures.
- **Snapshotting**: Point-in-time snapshots enable backup and recovery of EBS volumes.
- **Encryption**: Volumes can be encrypted using AWS-managed or customer-managed keys for enhanced security.
- **Availability**: Available in all AWS regions, allowing attachment to instances within the same region.


### Types of AWS EBS Volumes

Certainly! Let's expand on each AWS EBS volume type with their description, performance characteristics, and specific use cases:

### 1. General Purpose SSD (gp2)

- **Description:**
  - Default EBS volume type offering a balance of price and performance.
  - Designed for a wide range of transactional and interactive workloads.

- **Performance:**
  - Supports up to 16,000 IOPS and 250 MiB/s throughput.
  - Burstable performance capabilities for handling occasional spikes in workload.

- **Use Cases:**
  - **Small to Medium Databases:** Suitable for relational databases like MySQL, PostgreSQL.
  - **Development and Test Environments:** Ideal for testing applications and prototypes.
  - **Boot Volumes:** Used as boot volumes for EC2 instances due to their balance of performance and cost.

### 2. General Purpose SSD (gp3)

- **Description:**
  - Enhanced version of gp2 with higher IOPS and throughput capabilities.
  - Designed for applications requiring higher performance than gp2.

- **Performance:**
  - Supports up to 16,000 IOPS and 3,000 MiB/s throughput.
  - Provides consistent performance for a variety of workloads.

- **Use Cases:**
  - **Database Workloads:** Better suited for databases requiring higher IOPS and throughput than gp2.
  - **Transactional Applications:** Applications needing reliable and scalable performance.
  - **Virtual Desktops:** Supporting multiple users with consistent performance.

### 3. Provisioned IOPS SSD (io1)

- **Description:**
  - Designed for I/O-intensive workloads that require predictable and consistent performance.
  - Offers the highest performance level among EBS volumes.

- **Performance:**
  - Provides up to 64,000 IOPS and 1,000 MiB/s throughput.
  - Allows users to specify IOPS requirements for their applications.

- **Use Cases:**
  - **Critical Business Applications:** Such as ERP systems, CRM applications that demand high and consistent IOPS.
  - **Big Data Analytics:** Handling large-scale analytics queries and data processing.
  - **High-Performance Databases:** NoSQL databases like MongoDB, Cassandra requiring predictable I/O performance.

### 4. Throughput Optimized HDD (st1)

- **Description:**
  - Designed for frequently accessed, large, sequential workloads that require high throughput.
  - Cost-effective solution for throughput-intensive applications.

- **Performance:**
  - Provides up to 500 MiB/s throughput.
  - Optimized for scenarios with large, sequential data access patterns.

- **Use Cases:**
  - **Big Data Processing:** Handling large datasets for processing and analytics.
  - **Log Processing:** Continuous data ingestion and processing logs.
  - **Data Warehousing:** Storing and querying large volumes of structured data.

### 5. Cold HDD (sc1)

- **Description:**
  - Designed for infrequently accessed workloads where cost efficiency is paramount.
  - Lower-cost option for data that doesn’t require frequent access.

- **Performance:**
  - Provides up to 250 MiB/s throughput.
  - Suitable for scenarios where storage cost is the primary consideration.

- **Use Cases:**
  - **Infrequent Access Storage:** Storing backups, archives, and disaster recovery data.
  - **Long-term Storage:** Data that is accessed less frequently but needs to be retained.
  - **Cost-Sensitive Workloads:** Where cost efficiency is critical over high performance.

### 6. Magnetic (standard)

- **Description:**
  - Older generation EBS volume type being phased out.
  - Provides the lowest cost per GB among EBS volume types.

- **Performance:**
  - Provides basic, low-performance storage.
  - Suitable for applications with minimal I/O requirements.

- **Use Cases:**
  - **Low I/O Workloads:** Suitable for workloads with minimal I/O operations, such as legacy applications.
  - **Non-Critical Applications:** Development and testing environments where performance is not a primary concern.
  - **Budget-Conscious Environments:** Where minimizing costs is the primary consideration.


----
### Lab Session - Creation of an EBS Volume

Creating an EBS (Elastic Block Store) volume in AWS involves a few straightforward steps. Here’s a concise guide on how to create an EBS volume:

### Steps to Create an EBS Volume in AWS

1. **Navigate to the EC2 Console:**
   - Log in to your AWS Management Console.
   - Go to the EC2 dashboard.

2. **Access the Volumes Section:**
   - In the left-hand navigation pane, click on **"Volumes"** under the **"Elastic Block Store"** section.

3. **Create Volume:**
   - Click on **"Create Volume"** button.

4. **Configure Volume Settings:**
   - **Volume Type:** Choose the appropriate type based on your workload (e.g., gp2, io1, st1, sc1).
   - **Size (GiB):** Specify the size of the volume in gigabytes (GB).
   - **Availability Zone:** Select the availability zone where your EC2 instance that will use this volume is located.

5. **Configure Additional Settings (Optional):**
   - **Snapshot:** You can create a new volume from an existing snapshot if needed.
   - **Encryption:** Choose whether to encrypt the volume using AWS-managed keys or customer-managed keys.
   - **Tags:** Add tags to label your volume for easier management.

6. **Review and Create:**
   - Review your configuration settings.
   - Click **"Create Volume"** to create the EBS volume.

### Example:

Let's say you want to create a 50 GiB General Purpose SSD (gp2) volume in the us-east-1a availability zone without encryption:

- **Volume Type:** General Purpose SSD (gp2)
- **Size:** 50 GiB
- **Availability Zone:** us-east-1a
- **Encryption:** None (optional)

After reviewing your settings, click **"Create Volume"**. The EBS volume will be created and will appear in the list of volumes in the EC2 console. You can then attach this volume to your EC2 instance as needed.


### Lab Session - Attach an EBS Volume to a Linux EC2 Instance

Attaching an EBS (Elastic Block Store) volume to a Linux EC2 instance in AWS involves a few steps. Here’s a guide on how to attach an EBS volume to a Linux EC2 instance:

### Steps to Attach an EBS Volume to a Linux EC2 Instance

1. **Navigate to the EC2 Console:**
   - Log in to your AWS Management Console.
   - Go to the EC2 dashboard.

2. **Identify Your EC2 Instance:**
   - Note the Instance ID of the Linux EC2 instance to which you want to attach the EBS volume.

3. **Create an EBS Volume (if not already created):**
   - Follow the steps mentioned earlier to create an EBS volume, specifying the size, type, and availability zone.

4. **Attach the EBS Volume:**

   - In the EC2 dashboard, click on **"Volumes"** under **"Elastic Block Store"** in the left-hand navigation pane.
   - Select the EBS volume you want to attach by clicking its checkbox.

5. **Attach Volume Action:**
   - Click **"Actions"** and then **"Attach Volume"**.

6. **Configure Attachment:**
   - In the **"Instance"** field, start typing the instance ID or name of your Linux EC2 instance.
   - Select the instance from the drop-down list.
   - In the **"Device"** field, specify the device name on the instance (e.g., `/dev/xvdf`). This is the device path where the volume will be mounted in the instance.

7. **Attach the Volume:**
   - Click **"Attach"** to attach the EBS volume to your Linux EC2 instance.

### Example:

Let's say you have an existing Linux EC2 instance with Instance ID `i-0abcdef1234567890` and you want to attach a 100 GiB General Purpose SSD (gp3) volume (`vol-1234567890abcdef0`) to it as `/dev/sdf`:

- **Instance ID:** `i-0abcdef1234567890`
- **EBS Volume ID:** `vol-1234567890abcdef0`
- **Device:** `/dev/sdf`

After attaching the volume, you can log in to your Linux EC2 instance and proceed to mount the attached volume to make use of it.

### Mounting the EBS Volume on Linux

Once attached, you typically need to mount the EBS volume to make it accessible within your Linux instance. Here are basic steps for mounting on a typical Linux system:

1. **SSH into Your Linux Instance:**
   - Use SSH to connect to your Linux instance where the volume is attached.

2. **Check Attached Volumes:**
   - Use the `lsblk` command to list all block devices including your newly attached volume. Identify the device name (e.g., `/dev/xvdf`).

3. **Create a Mount Point:**
   - Create a directory where you will mount the volume. For example, `sudo mkdir /mnt/data`.

4. **Format the Volume (if not formatted):**
   - If the volume is new or needs to be formatted, use a command like `sudo mkfs -t ext4 /dev/xvdf` to format it as ext4 (replace `/dev/xvdf` with your device name).

5. **Mount the Volume:**
   - Mount the volume to the mount point you created: `sudo mount /dev/xvdf /mnt/data`.

6. **Verify Mounting:**
   - Use `df -h` to verify that the volume is mounted correctly and check its available space.

7. **Automate Mounting (Optional):**
   - Edit `/etc/fstab` to automatically mount the volume on system boot. Add a line like `/dev/xvdf   /mnt/data   ext4   defaults,nofail   0   2`.

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
