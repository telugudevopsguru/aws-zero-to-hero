**1. Which AWS service automatically adjusts the number of EC2 instances based on demand?**

A. Elastic Load Balancer  
B. Auto Scaling Group  
C. CloudFormation  
D. AWS Config

**Correct Answer:** B. Auto Scaling Group  
**Explanation:** An Auto Scaling Group (ASG) automatically scales the number of EC2 instances in response to demand, ensuring that the appropriate number of instances is running to handle the load.

---

**2. Which of the following is a key benefit of using an Auto Scaling Group?**

A. It provides static instance counts for predictable workloads.  
B. It enables manual control over instance lifecycles.  
C. It reduces operational overhead by automatically scaling resources based on policies.  
D. It eliminates the need for monitoring instance health.

**Correct Answer:** C. It reduces operational overhead by automatically scaling resources based on policies.  
**Explanation:** Auto Scaling Groups automatically adjust capacity based on demand, which minimizes manual intervention and improves application availability and fault tolerance.

---

**3. What is a Launch Configuration in AWS?**

A. A configuration file that defines security settings for AWS accounts.  
B. A template that specifies instance configuration details (AMI, instance type, security groups, etc.) for use in an Auto Scaling Group.  
C. A monitoring tool for tracking EC2 performance.  
D. A service that deploys serverless applications.

**Correct Answer:** B. A template that specifies instance configuration details (AMI, instance type, security groups, etc.) for use in an Auto Scaling Group.  
**Explanation:** A Launch Configuration is a blueprint that includes all the settings required to launch an EC2 instance as part of an Auto Scaling Group.

---

**4. What is one of the primary benefits of using a Launch Configuration?**

A. It allows on-the-fly updates to instance configurations without creating a new version.  
B. It lets you define a reusable set of instance settings for launching new instances in an Auto Scaling Group.  
C. It automatically scales resources without the need for an Auto Scaling Group.  
D. It provides detailed billing reports for EC2 usage.

**Correct Answer:** B. It lets you define a reusable set of instance settings for launching new instances in an Auto Scaling Group.  
**Explanation:** Launch Configurations allow you to specify all necessary settings once, so that every instance launched by the ASG uses the same configuration.

---

**5. Which of the following is a drawback of using a Launch Configuration?**

A. They support versioning and can be updated at any time.  
B. They are immutable; any change requires creating a new Launch Configuration.  
C. They automatically integrate with third-party monitoring tools.  
D. They do not support specifying an Amazon Machine Image (AMI).

**Correct Answer:** B. They are immutable; any change requires creating a new Launch Configuration.  
**Explanation:** Once created, a Launch Configuration cannot be modified. If you need to change instance settings, you must create a new configuration and update your ASG accordingly.

---

**6. In a lab session for creating an AWS Launch Configuration, which of the following parameters would you typically define?**

A. S3 bucket policies and CloudFront distributions  
B. Instance type, AMI ID, security groups, and key pairs  
C. VPC subnets and route tables  
D. Lambda function configurations

**Correct Answer:** B. Instance type, AMI ID, security groups, and key pairs  
**Explanation:** When creating a Launch Configuration, you specify the details required to launch an EC2 instance, such as the instance type, the AMI, security groups, and key pairs.

---

**7. What is an AWS Launch Template?**

A. A legacy tool for launching EC2 instances with minimal configuration.  
B. A newer, more flexible version of a Launch Configuration that supports versioning and additional parameters.  
C. A service for deploying serverless applications.  
D. A monitoring dashboard for EC2 instances.

**Correct Answer:** B. A newer, more flexible version of a Launch Configuration that supports versioning and additional parameters.  
**Explanation:** AWS Launch Templates provide all the functionality of Launch Configurations plus additional features such as versioning and support for advanced configuration options.

---

**8. Which is a significant benefit of using an AWS Launch Template over a Launch Configuration?**

A. Launch Templates are immutable and cannot be versioned.  
B. Launch Templates support multiple versions and additional features like T2/T3 Unlimited settings and credit specifications.  
C. Launch Templates do not support instance metadata options.  
D. Launch Templates automatically update the AMI without user intervention.

**Correct Answer:** B. Launch Templates support multiple versions and additional features like T2/T3 Unlimited settings and credit specifications.  
**Explanation:** The versioning capability of Launch Templates allows you to manage changes over time, and they also support a broader range of configuration options compared to Launch Configurations.

---

**9. What is the primary difference between a Launch Template and a Launch Configuration?**

A. Launch Templates are used exclusively for container orchestration, while Launch Configurations are for EC2 instances.  
B. Launch Templates offer versioning and advanced settings, whereas Launch Configurations are immutable once created.  
C. Launch Configurations support dynamic updates, while Launch Templates require manual adjustments for every change.  
D. There is no functional difference between the two.

**Correct Answer:** B. Launch Templates offer versioning and advanced settings, whereas Launch Configurations are immutable once created.  
**Explanation:** The key difference is that Launch Templates allow you to create multiple versions and include additional configuration options, making them more flexible than Launch Configurations.

---

**10. When creating an Auto Scaling Group (ASG) using an AWS Launch Configuration in a lab session, which sequence of steps is most accurate?**

A. Create the ASG first, then define a Launch Configuration, and finally assign scaling policies.  
B. Define scaling policies, create a Launch Template, and then create the ASG.  
C. Create a Launch Configuration, then create an ASG that references it, and finally configure scaling policies.  
D. Set up CloudWatch alarms, then create a Launch Configuration, and finally link a VPC.

**Correct Answer:** C. Create a Launch Configuration, then create an ASG that references it, and finally configure scaling policies.  
**Explanation:** The typical process is to first create a Launch Configuration (or Launch Template), then create an ASG that uses that configuration, and finally set scaling policies to manage the instance count.

---

**11. In a lab session focused on creating an AWS Launch Template, which additional feature is directly supported compared to a Launch Configuration?**

A. The ability to assign IAM roles after instance launch  
B. Support for multiple versions of the template  
C. Automatic creation of Elastic Load Balancers  
D. Real-time billing reports

**Correct Answer:** B. Support for multiple versions of the template  
**Explanation:** AWS Launch Templates support versioning, allowing you to maintain and roll back to previous configurations if necessary.

---

**12. When creating an Auto Scaling Group using an AWS Launch Template in a lab session, which benefit does the Launch Template provide?**

A. It eliminates the need for CloudWatch monitoring.  
B. It allows you to choose a specific template version, enabling easy rollbacks and updates.  
C. It automatically updates all running instances with new software.  
D. It supports on-the-fly changes to instance types without recreating the ASG.

**Correct Answer:** B. It allows you to choose a specific template version, enabling easy rollbacks and updates.  
**Explanation:** With Launch Templates, you can specify which version to use when launching new instances, giving you better control over changes and facilitating easier updates.

---

**13. During a lab session, enabling CloudWatch monitoring for an ASG primarily helps you to:**

A. Automatically deploy new instances based on application updates.  
B. Monitor instance health and performance metrics for scaling decisions.  
C. Secure the network traffic to and from the instances.  
D. Manage cost allocation tags automatically.

**Correct Answer:** B. Monitor instance health and performance metrics for scaling decisions.  
**Explanation:** Enabling CloudWatch monitoring allows you to track metrics such as CPU utilization and network traffic, which are essential for making informed scaling decisions in an Auto Scaling Group.

---

**14. In a lab session for deleting an Auto Scaling Group (ASG), what is the typical outcome when the ASG is deleted?**

A. The ASG is removed, but all instances remain running indefinitely.  
B. Both the ASG and its associated instances are terminated based on the defined termination policies.  
C. Only the scaling policies are deleted, while the ASG continues to run.  
D. The ASG is archived, allowing you to restore it later with all instance data intact.

**Correct Answer:** B. Both the ASG and its associated instances are terminated based on the defined termination policies.  
**Explanation:** When you delete an ASG, the default behavior is to terminate all instances that were launched by it, following the termination policies set during creation.

**15. In an Auto Scaling Group (ASG), what happens when an EC2 instance fails its health check?**

A. The instance is rebooted automatically.  
B. The ASG ignores the failure and keeps the instance running.  
C. The instance is terminated and replaced with a new one.  
D. The ASG sends an alert but takes no action.

**Correct Answer:** C. The instance is terminated and replaced with a new one.  
**Explanation:** Auto Scaling Groups are designed to maintain the desired number of healthy instances. When an instance fails its health check, the ASG terminates it and launches a replacement based on the configured Launch Configuration or Launch Template.

---

**16. What is the primary purpose of a lifecycle hook in an Auto Scaling Group?**

A. To schedule regular backups of instance data.  
B. To perform custom actions (such as configuration updates or logging) before an instance is fully launched or terminated.  
C. To automatically adjust the instance type based on usage patterns.  
D. To integrate CloudWatch metrics into scaling decisions.

**Correct Answer:** B. To perform custom actions (such as configuration updates or logging) before an instance is fully launched or terminated.  
**Explanation:** Lifecycle hooks enable you to pause the instance launch or termination process, allowing you to run custom scripts or tasks (e.g., installing software, draining connections) before the instance transitions to its next state.

---

**17. Which of the following scaling policies maintains a specific target metric value for an Auto Scaling Group?**

A. Step Scaling Policy  
B. Simple Scaling Policy  
C. Target Tracking Scaling Policy  
D. Scheduled Scaling Policy

**Correct Answer:** C. Target Tracking Scaling Policy  
**Explanation:** A Target Tracking Scaling Policy adjusts the number of instances to maintain a target metric (for example, keeping CPU utilization at 50%), making it simpler to manage dynamic scaling.

---

**18. Which AWS service is primarily used to monitor metrics that drive scaling decisions in an Auto Scaling Group?**

A. AWS CloudTrail  
B. Amazon CloudWatch  
C. AWS Config  
D. AWS Inspector

**Correct Answer:** B. Amazon CloudWatch  
**Explanation:** Amazon CloudWatch collects and tracks metrics such as CPU utilization, network I/O, and disk usage. These metrics can trigger scaling actions in an ASG when thresholds are met.

---

**19. What advantage does versioning in an AWS Launch Template offer compared to a Launch Configuration?**

A. It allows you to update instance configurations without creating a new template version.  
B. It enables you to roll back to previous configurations if needed.  
C. It automatically synchronizes with multiple Auto Scaling Groups.  
D. It provides real-time performance analytics for each version.

**Correct Answer:** B. It enables you to roll back to previous configurations if needed.  
**Explanation:** With Launch Templates, you can create and manage multiple versions. This versioning feature allows you to revert to an earlier configuration if a recent change causes issues.

---

**20. When configuring scaling policies for an ASG, why is it important to set an appropriate cool-down period?**

A. It helps in automatically updating the operating system on the instances.  
B. It prevents rapid scaling activities that could lead to resource thrashing.  
C. It ensures that the ASG ignores any CloudWatch alarms during that period.  
D. It allows the ASG to permanently maintain the current number of instances.

**Correct Answer:** B. It prevents rapid scaling activities that could lead to resource thrashing.  
**Explanation:** A cool-down period gives the newly launched instances time to start up and stabilize before another scaling activity is triggered. This helps to avoid over-scaling or oscillation in response to short-lived metric spikes.
