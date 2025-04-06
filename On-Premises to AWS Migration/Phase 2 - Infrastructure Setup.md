## **Phase 2: Infrastructure Setup**  

### **Step 10: Architecture Design**  
- Respective **Architects** will design the implementation architecture for this migration.  

### **Step 11: Task Execution Begins**  
- Based on assigned tasks in JIRA, **DevOps engineers** and the **Development team** start executing tasks based on priority.  

### **Step 12: AWS Account Creation**  
- If AWS accounts are not already available, create AWS accounts as per the migration plan.  
- Either set up **environment-specific accounts** (e.g., separate accounts for **Dev, Test, QA**) or consolidate **all lower environments** into a single AWS account.  
- **Production, Pre-Prod, and Infrastructure** accounts should be separate for security and compliance.  

### **Step 13: AWS Networking Setup via Terraform**  
- The **DevOps engineer** sets up AWS networking components, including:  
  - **VPC, Subnets, Route Tables, NAT Gateways, Internet Gateways, Security Groups, NACLs**  
  - Setting up the **Transit Gateway (TGW)** if required for multi-environment networking  

#### **Example: VPC CIDR Blocks**  
- **DEV CIDR** - 10.20.0.0/16  
- **TEST CIDR** - 10.30.0.0/16  
- **UAT CIDR** - 10.40.0.0/16  
- **PRE-PROD CIDR** - 10.50.0.0/16  
- **PROD CIDR** - 10.60.0.0/16  
- **INFRA CIDR** - 10.70.0.0/16  
**Note:** Wherever applicable, we will use **Terraform** to automate infrastructure provisioning.  
### **Step 14: Site-to-Site VPN Setup**  
- Work with the **on-premises network team** to establish a **Site-to-Site VPN** between **on-premises** and **AWS**.  
- Test **connectivity** to ensure smooth integration with AWS resources.  
**Note:** Wherever applicable, we will use **Terraform** to automate infrastructure provisioning.  
### **Step 15: AWS Client VPN / Cisco VPN Setup**  
- Set up **AWS Client VPN** or **Cisco VPN** to allow secure access to private AWS resources.  
- Example use case: **Accessing internal application URLs (e.g., https://user-registration-dev.techworldwithmurali.in).**  

**Prerequisites for AWS Client VPN Setup:**  
1. **AWS Directory Service** configuration  
2. **Amazon Certificate Manager (ACM)** for SSL/TLS certificates  

**Note:** Wherever applicable, we will use **Terraform** to automate infrastructure provisioning.  

### **Step 16: DevOps Tools Installation in Infra VPC**  
- Deploy essential DevOps tools in the **Infra VPC** for automation and CI/CD processes.  

**Tools to be installed:**  
- **Jenkins** - for CI/CD pipeline automation  
- **JFrog Artifactory** - for artifact storage  
- **SonarQube** - for code quality analysis  

#### **Example URLs:**  
- **Jenkins** - https://jenkins.techworldwithmurali.in  
- **JFrog Artifactory** - https://artifactory.techworldwithmurali.in  
- **SonarQube** - https://sonarqube.techworldwithmurali.in  

**Note:** These tools can either be deployed on **individual EC2 instances** or hosted in an **EKS (Kubernetes) cluster** for better scalability.  

### **Step 17: ECS or EKS setup for a microservice applications via Terraform.**  
- Deploy microservices in either:  
  - **ECS (Elastic Container Service)**  
  - **EKS (Elastic Kubernetes Service)**  
- The choice depends on **application architecture** and **team discussions**.
   
**Note:** Wherever applicable, we will use **Terraform** to automate infrastructure provisioning.  
### **Step 18: Monolithic Applications Setup via Terraform**  
- For **monolithic applications**, set up:  
  - **Auto Scaling Groups (ASG)**  
  - **Application Load Balancer (ALB)** (internal/external) for traffic distribution  
  - Create/update the records in **Route 53 hosted zone** etc.
    
**Note:** Wherever applicable, we will use **Terraform** to automate infrastructure provisioning.  
### **Step 19: Route 53 DNS Configuration**  
- Create a **Hosted Zone** in **Route 53**. Example:  
  - `techworldwithmurali.in`  
- Migrate DNS records to the **Route 53 hosted zone**, if applicable.  

### **Step 20: Database Setup**  
- Set up **Amazon RDS MySQL Cluster** as per the database requirements.  
- Inform the **DBA team** once provisioning is complete.  
**Note:** Wherever applicable, we will use **Terraform** to automate infrastructure provisioning.  
### **Step 21: Database Migration**  
- Migrate databases from **on-premises to AWS** using the appropriate strategy:  
  - **AWS DMS (Database Migration Service)**  
  - **Log Shipping**  
  - **Other database replication techniques**  

**Responsibility:** The **DBA team** will handle this migration process.  

### **Step 22: Infrastructure Setup Completion Notification**  
- Once the infrastructure setup is complete:  
  - The **DevOps team** will notify the **Scrum Master**, **Development team**, and **QA team**.  
  - All corresponding **JIRA/Rally tickets** will be updated accordingly.  
  - A final **infrastructure validation checklist** will be completed to ensure:  
    - Networking components (VPC, subnets, security groups) are correctly configured.  
    - VPN connectivity is established and tested.  
    - DevOps tools are accessible and functional.  
    - Databases are provisioned, and accessible.  
    - Route 53 DNS records are correctly set up.  
  - Documentation, including **architecture diagrams, and access credentials**, will be shared in the designated **Confluence/JIRA **. 
