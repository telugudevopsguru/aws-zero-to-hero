### Access Control List (ACL) in Amazon S3

**Access Control List (ACL):** Allows you to grant basic read/write permissions to users for individual objects or buckets in S3.

### Lab Session - Apply ACL for S3 Bucket

1. **Sign in to AWS Management Console:**
   - Navigate to the S3 Dashboard at [AWS Management Console](https://s3.console.aws.amazon.com/s3/).

2. **Apply ACL for S3 Bucket:**
   - Select the bucket for which you want to modify ACL.
   - Click on "Permissions."
   - Under "Access control list (ACL)," configure permissions for specific AWS accounts or users.
   - Choose permissions like read, write, or full control.

### S3 Bucket Lifecycle

**S3 Bucket Lifecycle:** Automates the management of objects over time, allowing you to define lifecycle rules to transition or expire objects based on their age or other criteria.

### Hosting a Static Website using Amazon S3

1. **Sign in to AWS Management Console:**
   - Navigate to the S3 Dashboard at [AWS Management Console](https://s3.console.aws.amazon.com/s3/).

2. **Hosting a Static Website:**
   - Select the bucket you want to use for hosting.
   - Click on "Properties" and then "Static website hosting."
   - Enable static website hosting and configure index and error documents.
   - Note the endpoint URL provided for accessing your static website.

### Presigned URLs in AWS S3

**Presigned URLs:** URLs that grant temporary access to download or upload a specific S3 object with a specified expiration time.

### Lab Session - Working with Presigned URLs in AWS S3

1. **Generate Presigned URL (Download):**
   - Use AWS SDK or AWS CLI to generate a presigned URL for an object.
   - Example using AWS CLI:
     ```bash
     aws s3 presign s3://<bucket_name>/<object_key> --expires-in 3600
     ```
   - This URL allows temporary access to download the object for one hour.

2. **Generate Presigned URL (Upload):**
   - Generate a presigned URL to allow temporary access for uploading an object to S3.
   - Example using AWS SDK:
     ```python
     import boto3
     s3_client = boto3.client('s3')
     presigned_url = s3_client.generate_presigned_url('put_object', Params={'Bucket': '<bucket_name>', 'Key': '<object_key>'}, ExpiresIn=3600)
     ```

### Server-side Encryption for Amazon S3 Buckets

**Server-side Encryption:** Ensures that S3 objects are encrypted at rest using encryption keys managed by AWS.

### Lab Session - Delete an S3 Bucket

1. **Sign in to AWS Management Console:**
   - Navigate to the S3 Dashboard at [AWS Management Console](https://s3.console.aws.amazon.com/s3/).

2. **Delete an S3 Bucket:**
   - Select the bucket you want to delete.
   - Click on "Actions > Delete bucket."
   - Confirm the deletion.
