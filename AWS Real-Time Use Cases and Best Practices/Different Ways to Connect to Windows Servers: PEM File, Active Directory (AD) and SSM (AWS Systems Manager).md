#### Different Ways to Connect to Windows Servers: PEM File, Active Directory (AD) and SSM (AWS Systems Manager)

We can connect to the Amazon Windows server in three different ways:  
1. Using a PEM file  
2. Using Active Directory (AD)
3. Using a SSM (AWS Systems Manager)
### **1. Using PEM File (For AWS EC2 Windows Instances)**
#### Prerequisites:
- PEM file associated with your Windows instance.
- Instance must be running and have RDP enabled.

#### Steps:
1. **Obtain the Administrator Password**:
   - For an AWS EC2 instance, navigate to the **EC2 Dashboard** in the AWS Console.
   - Select your **Windows instance**.
   - Click on **Connect**.
   - Under the **RDP client** tab, click **Get Password**.
   - Upload the **PEM file** (private key) used for launching the instance to decrypt the password.
   - Copy the **Administrator password** generated.

2. **Connect via RDP**:
   - Download an RDP client (if not installed) such as **Remote Desktop Connection** on Windows or any other RDP client.
   - Open **Remote Desktop Connection** (`mstsc`), and enter the **Public IP address** of the instance.
   - When prompted, use the **Administrator username** and the decrypted **password** to log in.

3. **Access Windows Server**:
   - Once authenticated, you will have full remote desktop access to the server.

---

### **2. Using Active Directory (AD) Authentication**
#### Prerequisites:
- The Windows server must be joined to a **Windows Active Directory domain**.
- You need a valid **AD user account** with the appropriate permissions.

#### Steps:
1. **Join the Windows Server to the AD Domain**:
   - On the server, open **Server Manager**.
   - Under **Local Server**, click on the **Workgroup** link next to **Computer Name**.
   - Click **Change** and select **Domain**.
   - Enter the **domain name** and credentials of a domain administrator.
   - After successful domain joining, restart the server if prompted.

2. **Login Using Active Directory Account**:
   - On the server's login screen, click **Other User**.
   - Enter the **domain\username** and the **AD password**.
   - You can now log in using your domain credentials.

3. **Access via RDP (Remote Desktop)**:
   - If you want to use **RDP**, open **Remote Desktop Connection** and enter the **IP address** of the server.
   - Use **domain\username** and your **AD password** to log in.

4. **Use AD Credentials to Manage the Server**:
   - Once logged in, you can use your AD permissions to manage the server as per the roles assigned to your account.

---

### **3. Using AWS Systems Manager (SSM)**
#### Prerequisites:
- The **SSM Agent** must be installed and running on the Windows server.
- The server must have an **IAM role** with permissions for SSM (`AmazonSSMManagedInstanceCore` policy).
- The instance must have network access to the necessary AWS endpoints.

#### Steps:
1. **Verify SSM Agent**:
   - Ensure that the **SSM Agent** is installed and running on the Windows instance.
   - You can check this by running the following PowerShell command:
     ```powershell
     Get-Service AmazonSSMAgent
     ```

2. **Attach IAM Role with SSM Permissions**:
   - If not already done, attach an **IAM role** with the `AmazonSSMManagedInstanceCore` policy to the Windows instance.
   - This allows the instance to communicate with SSM and perform actions.

3. **Connect via Systems Manager Console**:
   - In the **AWS Management Console**, navigate to **Systems Manager**.
   - In the left sidebar, select **Session Manager** under **Node Management**.
   - Click **Start session**.

4. **Choose the Target Instance**:
   - From the list, select the **Windows instance** you want to connect to.
   - Click **Start session**.

5. **Access Windows Server**:
   - A session will open directly in your browser with an interactive PowerShell interface.
   - You can execute PowerShell commands on the Windows instance through this session.

6. **End the Session**:
   - Once done, click **Terminate session** in the Systems Manager console to disconnect.

---

### **Summary of Methods**

| Method               | Use Case                                       | Prerequisites                                  | Security Level            |
|----------------------|-----------------------------------------------|------------------------------------------------|---------------------------|
| **PEM File**          | Secure connection via RDP (AWS EC2)           | PEM file for key-based login, EC2 instance with RDP enabled | Medium (secure, but must keep PEM safe) |
| **Active Directory (AD)** | Domain-based login, enterprise environments | Windows Server joined to AD, valid AD credentials | High (centralized, controlled access) |
| **SSM (AWS Systems Manager)** | Secure CLI access without RDP/SSH | SSM Agent installed, IAM role with SSM permissions | Very High (no direct access needed) |
`````````
