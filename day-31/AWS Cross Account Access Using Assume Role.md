## **How to Enable AWS Cross-Account Access Using an IAM Role**

To enable AWS Cross-Account Access using an IAM role (Assume Role) from an **Infrastructure Account (Infra Account)** to a **Development Account (Dev Account)**, follow these steps:

### **Step 1: Create an IAM Role in the Dev Account**

1. **Login to the Dev Account**:
   - Use credentials with sufficient permissions to create roles and policies.

2. **Create the IAM Role**:
   - Navigate to the **IAM Console** in the AWS Management Console.
   - Click **Roles** > **Create role**.

3. **Select Trusted Entity**:
   - Choose **Another AWS account**.
   - Enter the **Account ID** of the Infra Account.

4. **Add Permissions**:
   - Attach a policy that specifies the permissions the Infra Account should have when assuming this role. For example:
     - To grant full access to S3, attach the `AmazonS3FullAccess` policy.
     - Alternatively, create a custom policy with fine-grained permissions.

5. **Add Role Name and Description**:
   - Name the role (e.g., `InfraAssumeRole`).
   - Add a description for clarity.

6. **Review and Create**:
   - Review the settings and click **Create Role**.

---



### **Step 2: Assume Role in the AWS Console (Source Account)**

1. **Log in to the AWS Console** of the **source account** (the account that will assume the role).

2. **Access the Role in the Console**:
   - Go to the **IAM Console**.
   - In the top navigation, select **Switch Role** (found on the right-hand corner next to your account name).

3. **Fill in the Role Details**:
   - **Account**: Enter the **Account ID** of the **target account**.
   - **Role**: Enter the **Role name** you created in the target account (e.g., `CrossAccountS3AccessRole`).
   - Optionally, you can enter a **Display name** (this will show in the top navigation when you're switched to the assumed role).
   - Optionally, select a **Color** to visually differentiate the session.

   **Example**:
   - **Account ID**: `123456789012`
   - **Role name**: `CrossAccountS3AccessRole`

4. **Click Switch Role**.

---
### **Step 3: Configure Permissions in the Infra Account**

1. **Login to the Infra Account**:
   - Use credentials with sufficient permissions to update IAM users/groups or policies.

2. **Create or Update a Policy for the User/Group/Role**:
   - Create a policy allowing `sts:AssumeRole` for the role in the Dev Account.
   - Example policy:

     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Allow",
           "Action": "sts:AssumeRole",
           "Resource": "arn:aws:iam::<Dev-Account-ID>:role/InfraAssumeRole"
         }
       ]
     }
     ```

3. **Attach the Policy**:
   - Attach the policy to the IAM user, group, or role in the Infra Account.

---

### **Step 4: Access the Resources in the Target Account**

After you switch to the role, the AWS Console will load the resources from the **target account** based on the permissions attached to the role.

You will see that you are now logged in as the assumed role, and the console will display the role name and target account ID in the top-right corner.

---

### **Step 5: Assume the Role from the Infra Account**

1. **Use the AWS CLI**:
   - Run the following command to assume the role:

     ```bash
     aws sts assume-role \
       --role-arn "arn:aws:iam::<Dev-Account-ID>:role/InfraAssumeRole" \
       --role-session-name "InfraToDevSession"
     ```

   - The output will include temporary credentials: `AccessKeyId`, `SecretAccessKey`, and `SessionToken`.

2. **Use the Temporary Credentials**:
   - Configure these temporary credentials in your AWS CLI or SDK for subsequent API calls to the Dev Account.

     ```bash
     aws configure
     ```

---

### **Step 6: Test Access**

- Use the assumed role credentials to test access to the resources in the Dev Account (e.g., list S3 buckets, launch an EC2 instance).

---

### **Summary**

1. **Ensure the role in the target account** allows console access and has the appropriate permissions.  
2. In the **source account's AWS Console**, use **Switch Role** to assume the role in the target account.  
3. After switching roles, you will have access to the resources in the target account.

---

### **Security Best Practices**

1. **Least Privilege**:
   - Restrict permissions in the role's policy to the minimum required.

2. **Use Conditions**:
   - Add conditions to the trust policy (e.g., require MFA or source IP restrictions).

3. **Rotate Credentials**:
   - Regularly rotate access keys for the Infra Account users.

4. **Enable Logging and Monitoring**:
   - Use AWS CloudTrail to monitor cross-account activity and ensure compliance.
