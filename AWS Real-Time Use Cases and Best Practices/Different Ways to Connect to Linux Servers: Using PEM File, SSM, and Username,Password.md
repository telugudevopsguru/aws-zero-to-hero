### Different Ways to Connect to Linux Servers: Using PEM File, SSM, and Username/Password

We can connect to the Amazon Linux server in three different ways:  
1. Using a PEM file  
2. Using AWS SSM  
3. Using a username and password  

### **1. Using a PEM File (Private Key Method)**
#### Prerequisites:
- A `.pem` file containing your private key.
- SSH access configured on the Linux server.

#### Steps:
1. **Ensure SSH is Installed**:
   On your local system, ensure SSH is installed. Run:
   ```bash
   ssh -V
   ```
   If it's not installed, install it using the package manager (`apt`, `yum`, `brew`, etc.).

2. **Set Correct Permissions for the PEM File**:
   ```bash
   chmod 400 /path/to/your-key.pem
   ```

3. **Connect to the Server**:
   Use the SSH command to connect:
   ```bash
   ssh -i /path/to/your-key.pem username@server-ip
   ```
   Replace:
   - `/path/to/your-key.pem` with the full path to your PEM file.
   - `username` with the server's username (e.g., `ec2-user`, `ubuntu`, or `root`).
   - `server-ip` with the server's public IP or hostname.

4. **Verify Connection**:
   If successful, you'll be logged into the server's terminal.

---

### **2. Using AWS SSM (Session Manager)**

### **Prerequisites**
1. The instance must have the **SSM Agent** installed and running.
2. The instance must have an **IAM role** attached with the `AmazonSSMManagedInstanceCore` policy or equivalent permissions.
3. Ensure the instance has outbound internet access or access to AWS endpoints.

---

### **Steps to Connect via AWS Console**
1. **Log in to the AWS Management Console**:
   Navigate to the [AWS Management Console](https://aws.amazon.com/console/).

2. **Go to the Systems Manager Dashboard**:
   - In the AWS Management Console, search for **Systems Manager** in the search bar and select it.

3. **Open Session Manager**:
   - In the left-hand menu, select **Session Manager** under the **Node Management** section.

4. **Start a Session**:
   - Click the **Start session** button.
   - A list of instances managed by SSM will appear.

5. **Select the Target Instance**:
   - From the list, find the instance you want to connect to. Ensure the instance status is `Online`.
   - Select the instance by checking the box next to it.

6. **Connect to the Instance**:
   - Click **Start session** at the bottom of the page.

7. **Use the Interactive Shell**:
   - A new browser window will open with an interactive shell connected to your Linux server.

8. **End the Session**:
   - When you're done, click **Terminate session** in the Session Manager window.

---

### **Advantages of Using AWS Console for SSM**
- No need for SSH keys or passwords.
- Secure connection directly from the AWS Management Console.
- Centralized logging (session logs can be sent to Amazon CloudWatch or S3 for auditing).


### **3. Using Username and Password**
#### Prerequisites:
- The server is configured to accept password-based SSH authentication.
- You know the server's username and password.

#### Steps:
1. **Ensure Password Authentication is Enabled**:
   On the server, confirm that password authentication is allowed in the SSH configuration file:
   ```bash
   sudo nano /etc/ssh/sshd_config
   ```
   Ensure the following lines are set:
   ```plaintext
   PasswordAuthentication yes
   ```
   Restart the SSH service:
   ```bash
   sudo systemctl restart sshd
   ```

2. **Connect to the Server**:
   Use the following SSH command:
   ```bash
   ssh username@server-ip
   ```
   Enter the password when prompted.

3. **Verify Connection**:
   If successful, you'll be logged into the server.

---

### **Summary Table**

| Method          | Use Case                                       | Security Level                     | Prerequisites                             |
|------------------|-----------------------------------------------|------------------------------------|------------------------------------------|
| **PEM File**     | Secure, widely used in cloud environments     | High                              | Private key and SSH access configured    |
| **SSM**          | AWS-specific, no key/password required        | Very High                         | AWS CLI, SSM Agent, and IAM permissions  |
| **Username/Pass**| Legacy or quick setups (not recommended)      | Low (unless paired with other methods) | Password authentication enabled         |
