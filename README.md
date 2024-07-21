### What is AWS FSx

Amazon FSx for Windows File Server is a fully managed service that provides a Windows-native file system built on Windows Server.
It is designed to handle the storage needs of Windows-based applications and workloads. Here are the key features and components of Amazon FSx for Windows File Server:

### Key Features

1. **Fully Managed**:
   - Amazon FSx handles all the administrative tasks, including hardware provisioning, patching, and backups, allowing you to focus on your applications.

2. **Windows File System**:
   - Provides a native Windows file system experience with support for SMB (Server Message Block) protocol, NTFS (New Technology File System), and Active Directory integration.

3. **Scalability**:
   - Scales up or down based on your storage needs. You can adjust capacity and performance based on workload requirements.

4. **High Availability**:
   - Offers built-in redundancy and automatic failover to ensure high availability. Data is replicated across multiple Availability Zones within a region.

5. **Backup and Restore**:
   - Supports automated backups with point-in-time recovery, allowing you to restore data to a specific point in time.

6. **Security**:
   - Integrates with AWS Identity and Access Management (IAM) and supports encryption of data at rest and in transit. You can also use AWS Key Management Service (KMS) for encryption keys.

7. **Active Directory Integration**:
   - Easily integrates with Microsoft Active Directory for user authentication and access control, allowing seamless access for users and applications.

8. **Performance**:
   - Offers performance options that can be tuned to match the needs of different applications, such as high IOPS or high throughput.

### Use Cases

1. **Windows-Based Applications**:
   - Ideal for applications that rely on Windows file system features and need compatibility with SMB protocols, such as enterprise applications, home directories, or shared file systems.

2. **File Storage**:
   - Provides centralized file storage for Windows workloads, including application data, shared files, and user profiles.

3. **Backup and Restore**:
   - Offers a reliable solution for backup and disaster recovery needs with point-in-time backups.

4. **Collaboration**:
   - Facilitates collaboration between users and applications by providing a shared file system with consistent access control and security.
----

### Creation of an Amazon FSx for Windows File Server
To create an Amazon FSx for Windows File Server, follow these steps:

**Step 1: Open the Amazon FSx Console**
1. Sign in to the [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to the **Amazon FSx** console by searching for **FSx** in the search bar and selecting **Amazon FSx**.

**Step 2: Create a New File System**
1. **Click** on the **Create file system** button.

**Step 3: Choose File System Type**
1. Select **Amazon FSx for Windows File Server**.

**Step 4: Configure File System**
1. **File System Details**:
   - **File System Name**: Enter a name for your file system.
   - **Storage Type**: Choose between **SSD** or **HDD** depending on your performance needs.
   
2. **Deployment Type**:
   - **Single-AZ** or **Multi-AZ**:
     - **Single-AZ** is cost-effective and suitable for non-critical workloads.
     - **Multi-AZ** provides high availability with data replication across multiple Availability Zones.

**Step 5: Configure Storage**
1. **Storage Capacity**: Specify the amount of storage you need (in GiB).
2. **Throughput Capacity**: Choose the desired throughput capacity based on your performance requirements.

**Step 6: Configure Network & Security**
1. **VPC**: Select the VPC where your FSx file system will be deployed.
2. **Subnets**: Choose the subnets in which the FSx file system should be deployed.
3. **Security Groups**: Select or create a security group to control network access to the FSx file system.

**Step 7: Configure Active Directory**
1. **Directory Service**:
   - **Create a new Active Directory**: If you don’t have an existing directory, you can create a new one.
   - **Use an existing Active Directory**: If you have an existing Active Directory, provide the necessary details (such as domain name, username, and password) to join the FSx file system to your directory.

**Step 8: Review and Create**
1. **Review** the configuration settings you have chosen.
2. **Click** **Create file system** to initiate the creation process.

**Step 9: Access the File System**
1. Once the file system is created, it will appear in the **Amazon FSx** console.
2. **Note** the DNS name or IP address provided for your FSx file system.
3. **Connect** to the file system from your Windows instances or applications using the provided DNS name and configure the necessary file shares and permissions.

**Step 10: Configure File System**
1. **Map Network Drive**: On your Windows instance, you can map the network drive to the FSx file system using the DNS name provided.
2. **Configure Permissions**: Set up NTFS permissions and share permissions as required for your application or users.
