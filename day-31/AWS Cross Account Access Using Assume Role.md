### AWS Cross Account Access Using Assume Role

### Step 1: **Create the Role in the Target Account**

1. **Log in to the AWS Management Console** of the **target account** (the account you want to grant access to).
   
2. **Navigate to IAM (Identity and Access Management)**:
   - Go to the **IAM** dashboard.
   - Select **Roles** in the left sidebar and click **Create role**.

3. **Select Trusted Entity**:
   - Choose **Another AWS account**.
   - Enter the **Account ID** of the **source account** (the account that will assume the role).
   - Optionally, select **Require external ID** if you want to add an extra layer of security.

4. **Set Permissions**:
   - Attach the necessary **policies** to define the permissions for the role (e.g., `AmazonS3FullAccess` or a custom policy based on your requirements).
   - Click **Next: Tags** to add tags (optional).
   
5. **Review and Create the Role**:
   - Provide a **Role name** (e.g., `CrossAccountS3AccessRole`).
   - Review the settings and click **Create role**.

### Step 2: **Update the Trust Relationship for the Role**

1. After the role is created, select the **Role** you just created.
   
2. **Edit the Trust Relationship**:
   - Go to the **Trust relationships** tab.
   - Click **Edit Trust Relationship**.

3. **Modify the Trust Policy**:
   Replace the existing policy with the following (replace `<SourceAccountID>` with the account ID of the source account):

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": {
           "AWS": "arn:aws:iam::<SourceAccountID>:root"
         },
         "Action": "sts:AssumeRole"
       }
     ]
   }
   ```

   This will allow the source account to assume the role in the target account.

4. Click **Update Trust Policy** to save changes.

### Step 3: **Create a Policy in the Source Account (Optional)**

1. **Log in to the AWS Management Console** of the **source account** (the account that will assume the role).
   
2. **Navigate to IAM**:
   - Create a policy that allows the user or service in the source account to assume the role in the target account.

3. **Create the AssumeRole Policy**:
   Here’s a sample policy for assuming the role in the target account (replace `<TargetRoleArn>` with the ARN of the role you created in the target account):

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Action": "sts:AssumeRole",
         "Resource": "<TargetRoleArn>"
       }
     ]
   }
   ```

4. Attach the policy to the IAM user, group, or role in the source account that will be assuming the role.

### Step 4: **Assume the Role in the Source Account**

Now that everything is set up, you can use the AWS CLI, SDKs, or IAM console to assume the role from the source account.

#### Using the AWS CLI:

1. Run the following command to assume the role from the source account (replace `<RoleArn>` and `<SessionName>`):

   ```bash
   aws sts assume-role --role-arn arn:aws:iam::<TargetAccountID>:role/CrossAccountS3AccessRole --role-session-name <SessionName>
   ```

2. **Capture the Temporary Security Credentials**:
   The output will provide temporary **AccessKeyId**, **SecretAccessKey**, and **SessionToken** that can be used to make API requests in the target account.

3. **Set the temporary credentials in the environment** (optional):

   ```bash
   export AWS_ACCESS_KEY_ID=<AccessKeyId>
   export AWS_SECRET_ACCESS_KEY=<SecretAccessKey>
   export AWS_SESSION_TOKEN=<SessionToken>
   ```

### Step 5: **Verify Access**

To verify that the cross-account access is working, try accessing a resource (e.g., S3 bucket) in the target account using the temporary credentials obtained from the `sts:assume-role` command.

Example for accessing an S3 bucket in the target account:

```bash
aws s3 ls s3://<TargetBucketName> --profile assumed-role
```

### Summary

1. **Create a role in the target account** and set up the trust relationship to allow the source account to assume it.
2. **Update policies in the source account** to allow the IAM user or service to assume the role.
3. **Use AWS CLI or SDK** to assume the role and access resources in the target account using temporary credentials.

This is how you can securely set up cross-account access using the `AssumeRole` feature in AWS.### Step 1: **Create the Role in the Target Account**

1. **Log in to the AWS Management Console** of the **target account** (the account you want to grant access to).
   
2. **Navigate to IAM (Identity and Access Management)**:
   - Go to the **IAM** dashboard.
   - Select **Roles** in the left sidebar and click **Create role**.

3. **Select Trusted Entity**:
   - Choose **Another AWS account**.
   - Enter the **Account ID** of the **source account** (the account that will assume the role).
   - Optionally, select **Require external ID** if you want to add an extra layer of security.

4. **Set Permissions**:
   - Attach the necessary **policies** to define the permissions for the role (e.g., `AmazonS3FullAccess` or a custom policy based on your requirements).
   - Click **Next: Tags** to add tags (optional).
   
5. **Review and Create the Role**:
   - Provide a **Role name** (e.g., `CrossAccountS3AccessRole`).
   - Review the settings and click **Create role**.

### Step 2: **Update the Trust Relationship for the Role**

1. After the role is created, select the **Role** you just created.
   
2. **Edit the Trust Relationship**:
   - Go to the **Trust relationships** tab.
   - Click **Edit Trust Relationship**.

3. **Modify the Trust Policy**:
   Replace the existing policy with the following (replace `<SourceAccountID>` with the account ID of the source account):

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": {
           "AWS": "arn:aws:iam::<SourceAccountID>:root"
         },
         "Action": "sts:AssumeRole"
       }
     ]
   }
   ```

   This will allow the source account to assume the role in the target account.

4. Click **Update Trust Policy** to save changes.

### Step 3: **Create a Policy in the Source Account (Optional)**

1. **Log in to the AWS Management Console** of the **source account** (the account that will assume the role).
   
2. **Navigate to IAM**:
   - Create a policy that allows the user or service in the source account to assume the role in the target account.

3. **Create the AssumeRole Policy**:
   Here’s a sample policy for assuming the role in the target account (replace `<TargetRoleArn>` with the ARN of the role you created in the target account):

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Action": "sts:AssumeRole",
         "Resource": "<TargetRoleArn>"
       }
     ]
   }
   ```

4. Attach the policy to the IAM user, group, or role in the source account that will be assuming the role.

### Step 4: **Assume the Role in the Source Account**

Now that everything is set up, you can use the AWS CLI, SDKs, or IAM console to assume the role from the source account.

#### Using the AWS CLI:

1. Run the following command to assume the role from the source account (replace `<RoleArn>` and `<SessionName>`):

   ```bash
   aws sts assume-role --role-arn arn:aws:iam::<TargetAccountID>:role/CrossAccountS3AccessRole --role-session-name <SessionName>
   ```

2. **Capture the Temporary Security Credentials**:
   The output will provide temporary **AccessKeyId**, **SecretAccessKey**, and **SessionToken** that can be used to make API requests in the target account.

3. **Set the temporary credentials in the environment** (optional):

   ```bash
   export AWS_ACCESS_KEY_ID=<AccessKeyId>
   export AWS_SECRET_ACCESS_KEY=<SecretAccessKey>
   export AWS_SESSION_TOKEN=<SessionToken>
   ```

### Step 5: **Verify Access**

To verify that the cross-account access is working, try accessing a resource (e.g., S3 bucket) in the target account using the temporary credentials obtained from the `sts:assume-role` command.

Example for accessing an S3 bucket in the target account:

```bash
aws s3 ls s3://<TargetBucketName> --profile assumed-role
```

### Summary

1. **Create a role in the target account** and set up the trust relationship to allow the source account to assume it.
2. **Update policies in the source account** to allow the IAM user or service to assume the role.
3. **Use AWS CLI or SDK** to assume the role and access resources in the target account using temporary credentials.
