#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


## Phase 4: Final Cutover to AWS: Cutover Plan & Go-Live Checklist

### **Step 27: Schedule the Cutover Meeting**  
- Based on the final discussion, a **cutover date** will be finalized.  
- The **Scrum Master** will schedule the meeting.  
- The cutover process typically takes **3 to 4 hours**, but depending on the complexity of the applications, it may take longer.  

### **Step 28: Stop the Application in On-Premises**  
- Stop the on-premises application **after the final data sync**.  
- Ensure that no new transactions are being processed in the on-premises system.  

### **Step 29: DNS Cutover & Go-Live**  
- **Update DNS Records:** Modify **Route 53** records to point to the **AWS Load Balancer** endpoints.  
- **Enable AWS Application:** Make the AWS-hosted application live.  
- **Monitor Traffic Flow:** Ensure users are now connecting to AWS instead of the on-premises system.  

### **Step 30: Application Validation & QA Testing**  
- Developers and QA teams validate that the application functions as expected.  
- Ensure all **integrations, services, and APIs** are working correctly.  
- The QA team performs **regression testing** and notifies all relevant teams of any issues.  

### **Step 31: Monitoring & Stabilization**  
- Monitor the environment for a few **days** to detect any issues.  
- Address and resolve issues as needed with the **Development** or **DevOps** teams.
- 
### **Step 32: Rollback Plan (If Needed)**  
- If **issues occur**, attempt to **fix them on demand**.  
- If unresolved, **roll back the DNS endpoint** to the **on-premises** infrastructure.
  
### **Step 33: Migration to Other Environments**  
- If everything is **stable**, replicate the same process for:  
  - **TEST**  
  - **QA**  
  - **UAT**  
  - **Pre-Prod** 
  - **PROD**  
