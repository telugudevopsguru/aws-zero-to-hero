### What is AWS Simple Storage Service (S3)?

- AWS Simple Storage Service (S3) is an object storage service that offers scalable storage for data in the cloud.
- It is designed to store and retrieve any amount of data from anywhere on the web.
- S3 provides high availability, durability, and security for your data.

### Buckets and Objects in Amazon S3

- **Buckets:** Containers for storing objects (files) in S3. Every object is contained within a bucket.
- **Objects:** Data files stored in S3, which can range in size from a few bytes to several terabytes. Each object is identified by a unique key within its bucket.

### Types of Storage Classes in AWS S3

1. **Standard:** Provides high durability, availability, and performance for frequently accessed data.
2. **Intelligent-Tiering:** Automatically moves objects between two access tiers based on changing access patterns.
3. **Standard-IA (Infrequent Access):** For data that is accessed less frequently but requires rapid access when needed.
4. **One Zone-IA:** Lower-cost option for infrequently accessed data that doesn't require multiple Availability Zone resilience.
5. **Glacier and Glacier Deep Archive:** For archival data with retrieval times ranging from minutes to hours.

----
### Lab Session - Create an S3 Bucket

1. **Sign in to AWS Management Console:**
   - Navigate to the S3 Dashboard at [AWS Management Console](https://s3.console.aws.amazon.com/s3/).

2. **Create S3 Bucket:**
   - Click on "Create bucket."
   - Enter a unique bucket name and choose a region.
   - Configure optional settings like versioning, logging, and tags.
   - Review and create the bucket.
----
### Lab Session - Upload Objects to S3 using the AWS Console

1. **Sign in to AWS Management Console:**
   - Navigate to the S3 Dashboard at [AWS Management Console](https://s3.console.aws.amazon.com/s3/).

2. **Upload Objects:**
   - Select the bucket to which you want to upload objects.
   - Click on "Upload" and select files from your local machine.
   - Configure upload options and permissions as needed.
   - Upload the files to the S3 bucket.
----
### Lab Session - Upload Objects to S3 using the AWS CLI

1. **Open Command Line Interface:**
   - Open a terminal or command prompt on your local machine.

2. **Upload Objects using AWS CLI:**
   - Use the `aws s3 cp` command to copy files to S3:
     ```bash
     aws s3 cp <local_file_path> s3://<bucket_name>/<remote_file_name>
     ```
   - Optionally, use `aws s3 sync` for syncing directories:
     ```bash
     aws s3 sync <local_directory> s3://<bucket_name>/<remote_directory>
     ```
----
### S3 Versioning and Enabling it

- **Versioning:** Keeps multiple variants of an object in the same bucket.
- **Enable Versioning:**
   - Sign in to AWS Management Console.
   - Navigate to S3 Dashboard.
   - Select the bucket and click on "Properties."
   - Under "Advanced settings," enable versioning.
----
### Bucket Policy in Amazon S3

- **Bucket Policy:** JSON-based access policy applied at the bucket level to manage permissions.
- **Working with Bucket Policy for S3 Bucket:**
   - Define permissions for who can access (e.g., IAM users, roles, or specific IP ranges).
   - Define actions allowed (e.g., read, write, delete).
   - Apply conditions for access (e.g., based on IP address, user agent).
----
### Lab Session - Working with the Bucket Policy for S3 Bucket

1. **Sign in to AWS Management Console:**
   - Navigate to the S3 Dashboard at [AWS Management Console](https://s3.console.aws.amazon.com/s3/).

2. **Configure Bucket Policy:**
   - Select the bucket and click on "Permissions."
   - Click on "Bucket Policy" and enter or modify the JSON policy document.
   - Use AWS policy generator to generate a policy based on requirements.
   - Review and apply the policy to manage access to the S3 bucket.
