#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


## 📦 Cloud Migration Strategies: The 6 R's

When migrating workloads to the cloud, organizations typically follow one or more of the following six strategies, commonly known as the **6 R’s of Cloud Migration**:

---

### 1. 🚚 Lift and Shift (Rehost)

- **Definition**: Move applications to the cloud **without modifying** them.
- **When to Use**: 
  - Quick migrations
  - Legacy systems
  - When minimal change is required
- **Example**: Migrating a virtual machine from on-premises to AWS EC2 without altering the application.

---

### 2. 🔧 Replatform (Lift, Tinker, and Shift)

- **Definition**: Move to the cloud with **minor optimizations** to take advantage of cloud-native capabilities.
- **When to Use**:
  - To improve performance or cost
  - When small changes are feasible
- **Example**: Migrating an app to AWS EC2 and replacing a local database with Amazon RDS.

---

### 3. 🧬 Refactor / Rearchitect

- **Definition**: **Redesign** the application to be **cloud-native**, often involving significant changes.
- **When to Use**:
  - For scalability, agility, or long-term cost savings
  - To adopt microservices, containers, or serverless architectures
- **Example**: Refactoring a monolithic application into a microservices-based architecture using AWS Lambda for compute, API Gateway for routing, and DynamoDB as a scalable NoSQL database.

---

### 4. 🗑️ Retire

- **Definition**: **Decommission** applications that are no longer useful.
- **When to Use**:
  - During assessment, when apps are identified as obsolete or redundant
- **Example**: Shutting down an old internal reporting tool that is no longer used.

---

### 5. 🛑 Retain

- **Definition**: **Keep** certain applications on-premises or **delay** migration.
- **When to Use**:
  - Compliance or regulatory concerns
  - Low priority applications
  - Systems not yet ready for migration
- **Example**: Retaining an ERP system that requires on-prem hosting due to licensing constraints.

---

### 6. 🛒 Repurchase

- **Definition**: Move to a **SaaS-based solution**, effectively replacing the existing system.
- **When to Use**:
  - When a better SaaS alternative exists
  - For faster time to value and reduced management overhead
- **Example**: Moving from a self-hosted CRM to Salesforce or Microsoft 365.
