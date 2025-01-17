### **1. Understanding EC2 Instance Health Checks**

Amazon EC2 provides two types of status checks for instances:

- **System Status Check**: Monitors the health of the underlying hardware and network connectivity in the region.
- **Instance Status Check**: Monitors the software and configurations within the instance (e.g., operating system, application, etc.).

If an instance fails either of these checks, it indicates a potential issue with the underlying infrastructure or with the instance itself.

![image](https://github.com/user-attachments/assets/659e03d1-11db-44f4-a861-5af02b47fb9e)

---

### **2. Check Instance Status in the Console**

1. **Log in to the AWS Console**:
   - Navigate to **EC2 Dashboard** > **Instances**.

2. **Check Instance Health**:
   - Review the **Status Checks** column for each instance.
     - If the **Instance Status** is **Failed**, it means there’s a problem with the instance’s software or configuration.
     - If the **System Status** is **Failed**, the issue is related to the underlying hardware or network.

3. **Detailed Status Check**:
   - Click on the instance ID to view more details about the status check.
   - AWS will often provide diagnostic messages, which can guide you toward the root cause.

---

### **System Status Checks**

1. **What is a System Status Check?**
   - **System Status Checks** are automated health checks that monitor the **AWS infrastructure** on which your EC2 instance is running.
   - These checks specifically detect problems with **the host's hardware or software**, not with the instance itself.

2. **When Does System Status Check Fail?**
   - A **failed system status check** indicates a problem with the **host hardware** or **host software** that supports the EC2 instance.
   - Examples of issues include:
     - **Loss of network connectivity**.
     - **Loss of system power**.
     - **Software issues** affecting the physical host.
     - **Hardware problems** with the physical host that impact network reachability.

### **System Status Check Failure and Automatic Recovery**

1. **Automatic Instance Recovery**:
   - When a **system status check fails**, AWS automatically attempts to recover the affected instance by migrating it to **different hardware**.
   - This automatic recovery ensures that the instance is moved from a problematic host to healthy infrastructure, without the need for manual intervention.
   
2. **What Happens During Recovery?**
   - **Preserved Elements**:
     - The instance retains the following:
       - **Instance ID**.
       - **Elastic IP** (Public, Private, and Elastic IP addresses).
       - **Instance Metadata**.
       - **Placement Group**.
       - **Attached EBS Volumes**.
       - **Availability Zone**.
   
   - **Lost Elements**:
     - The following are **lost** during recovery:
       - **Data stored in volatile memory (RAM)** is lost.
       - **Data stored on instance store volumes** (only applies if the instance is configured with **instance store volumes** for temporary storage).
       - The **Operating System uptime** is reset to zero.
   
3. **Recovery Process**:
   - AWS recovers the instance by moving it to another **physical host**.
   - The **instance** remains the same in terms of its **instance ID** and networking setup, but it will undergo a **reboot**, and **volatile memory** is cleared out.
   - **Instance store volumes** (if present) will be lost, but any **attached EBS volumes** will remain intact.

---

### **Instance Status Checks**

- EC2 checks the health of your instance by sending an ARP request to the network interface (NIC).
- If a status check fails, you typically need to take action, such as rebooting or adjusting instance configuration.

### **Common Causes of Instance Status Check Failures**
- Incorrect networking or startup configuration.
- Exhausted memory.
- Corrupted file system.
- Incompatible kernel.

### **Behavior During Reboots**
- Status checks may fail temporarily during a reboot until the instance becomes available.

### **Bare Metal Instances**
- Restarting the operating system on bare metal instances may cause a temporary failure of status checks, but they should return to healthy once available.

### **Metrics**
- A failed status check increments the **StatusCheckFailed_Instance** metric.

### **Resolving Issues**
- Reboot the instance or review configuration settings.
- Inspect logs and system metrics to identify underlying problems.

---

### **7. When to Contact AWS Support**

- If you’ve exhausted all troubleshooting options and the issue persists, it’s time to reach out to **AWS Support**. They can help identify underlying issues that may not be visible from your console or logs.
