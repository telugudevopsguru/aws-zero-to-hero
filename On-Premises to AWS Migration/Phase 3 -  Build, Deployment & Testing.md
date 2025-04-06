#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


## **Phase 3: Build, Deployment & Testing**  

### **Step 23: Development Team Preparation**  
- Developers implement any **necessary changes** to their applications for deployment.  

### **Step 24: Application Build**  
- Developers build the application using **Jenkins jobs**.  

### **Step 26: Deployment of Microservices/Monolithic Applications**  
- Developers deploy **microservices** in the **DEV environment** using **Jenkins jobs**. After deployment:  
  - **Load Balancers (LB), listeners, and Route 53 records** are automatically created using the **Ingress Controller** and **ExternalDNS**.  

- Developers deploy **monolithic applications** in the **DEV environment** using **Jenkins jobs**. After deployment:  
  - **Load Balancers, listeners, and Route 53 records** are automatically created via **Terraform**.  

**Note:** Before migrating the application, we will first build the application, deploy it to the **EKS cluster**, and validate its functionality.
