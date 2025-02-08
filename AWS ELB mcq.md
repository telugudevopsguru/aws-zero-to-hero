**1. Which of the following best describes AWS Elastic Load Balancing?**

A. A service that monitors and logs API calls across AWS services  
B. A tool that distributes incoming application traffic across multiple targets for high availability  
C. A service for deploying and managing containerized applications  
D. A tool to configure security groups and network ACLs

**Correct Answer:** B. A tool that distributes incoming application traffic across multiple targets for high availability  
**Explanation:** AWS Elastic Load Balancing automatically distributes incoming traffic across multiple targets—such as EC2 instances, containers, and IP addresses—to improve the availability and fault tolerance of your applications.

---

**2. Which of the following is a key benefit of AWS Elastic Load Balancing?**

A. It centralizes data storage in a single repository.  
B. It enhances fault tolerance and scalability by automatically distributing traffic.  
C. It eliminates the need for configuring security groups.  
D. It provides automated backup for EC2 instances.

**Correct Answer:** B. It enhances fault tolerance and scalability by automatically distributing traffic.  
**Explanation:** By balancing the load among multiple healthy targets, AWS ELB ensures that no single resource becomes a bottleneck, thereby increasing fault tolerance and scalability.

---

**3. What is an AWS Classic Load Balancer?**

A. The original AWS load balancing solution that distributes traffic across EC2 instances using basic features  
B. A modern load balancer that supports advanced features like path-based routing  
C. A service designed exclusively for containerized workloads  
D. A tool for managing IAM policies and user access

**Correct Answer:** A. The original AWS load balancing solution that distributes traffic across EC2 instances using basic features  
**Explanation:** The Classic Load Balancer is AWS’s first-generation load balancer. It offers basic load balancing across EC2 instances and supports features such as SSL termination and sticky sessions.

---

**4. Which of the following is a feature of a Classic Load Balancer?**

A. Advanced routing based on URL paths or host headers  
B. Basic load balancing across EC2 instances with support for SSL termination  
C. Dynamic scaling of backend services without user configuration  
D. Integrated serverless function routing

**Correct Answer:** B. Basic load balancing across EC2 instances with support for SSL termination  
**Explanation:** Classic Load Balancers offer simple load balancing functions—including distributing traffic and terminating SSL connections—but do not support some of the advanced routing features found in newer load balancers like the Application Load Balancer.

---

**5. During a lab session for creating an AWS Classic Load Balancer, which of the following parameters is typically specified?**

A. VPC peering connections and subnet associations  
B. Listener configurations, security groups, and the EC2 instances to register  
C. IAM roles and policy documents  
D. CloudFormation stack parameters and outputs

**Correct Answer:** B. Listener configurations, security groups, and the EC2 instances to register  
**Explanation:** When creating a Classic Load Balancer, you configure listener settings (protocols and ports), assign one or more security groups, and register the EC2 instances that will serve as targets for incoming traffic.

---

**6. What is the expected outcome of a lab session on deleting a Classic Load Balancer?**

A. The Classic Load Balancer is removed and all associated configuration data is permanently deleted  
B. The load balancer is temporarily suspended but can be reactivated later  
C. Only the registered EC2 instances are deregistered, while the load balancer remains active  
D. The load balancer is archived for auditing purposes

**Correct Answer:** A. The Classic Load Balancer is removed and all associated configuration data is permanently deleted  
**Explanation:** When you delete a Classic Load Balancer, the service and its configuration are completely removed from your account, and it no longer routes any traffic.

---

**7. What is an AWS Target Group?**

A. A collection of EC2 instances used for backup and disaster recovery  
B. A group of registered targets (such as EC2 instances, IP addresses, or Lambda functions) that receive traffic from a load balancer  
C. A security grouping mechanism for managing IAM policies  
D. A predefined set of CloudWatch alarms for monitoring network traffic

**Correct Answer:** B. A group of registered targets (such as EC2 instances, IP addresses, or Lambda functions) that receive traffic from a load balancer  
**Explanation:** Target Groups enable you to organize your backend resources so that load balancers (like Application Load Balancers and Network Load Balancers) can route requests to one or more registered targets based on specific rules and health check configurations.

---

**8. In the context of AWS Elastic Load Balancing, what is a Listener?**

A. A process that logs incoming requests for auditing purposes  
B. A rule that defines how incoming traffic is distributed among target groups  
C. A configuration setting that specifies the protocol and port for accepting incoming connections  
D. A monitoring agent installed on EC2 instances

**Correct Answer:** C. A configuration setting that specifies the protocol and port for accepting incoming connections  
**Explanation:** A Listener is configured on a load balancer to define the protocol (HTTP, HTTPS, TCP, etc.) and port on which the load balancer listens for incoming traffic and forwards requests to target groups.

---

**9. In a lab session focused on the creation of an AWS Target Group, which of the following settings is typically configured?**

A. The IAM roles and policies for the target resources  
B. The target type (instance, IP, or Lambda), port, protocol, and health check settings  
C. The CloudFront distribution settings for content delivery  
D. The RDS instance endpoints for database replication

**Correct Answer:** B. The target type (instance, IP, or Lambda), port, protocol, and health check settings  
**Explanation:** When creating a Target Group, you must define the target type (e.g., EC2 instance, IP address, or Lambda function), along with the port and protocol to use for routing traffic. Additionally, you configure health check parameters to monitor the status of the targets.

---

**10. Which AWS load balancer supports advanced routing features like host-based and path-based routing?**  
*(Note: While this question introduces another type of load balancer, understanding the differences helps clarify when to use a Classic Load Balancer.)*

A. Classic Load Balancer  
B. Application Load Balancer  
C. Network Load Balancer  
D. Global Accelerator

**Correct Answer:** B. Application Load Balancer  
**Explanation:** The Application Load Balancer is designed to support advanced routing features (such as host-based and path-based routing), making it ideal for modern web applications. In contrast, the Classic Load Balancer offers basic load distribution and is suited for simpler use cases.

---

**11. Which of the following is a key benefit of using AWS Elastic Load Balancing together with Auto Scaling?**

A. It automatically backs up application data.  
B. It evenly distributes traffic among healthy instances during scaling events.  
C. It replaces instances without verifying their health status.  
D. It encrypts all traffic between clients and backend instances by default.

**Correct Answer:** B. It evenly distributes traffic among healthy instances during scaling events.  
**Explanation:** By integrating with Auto Scaling, Elastic Load Balancing ensures that traffic is routed only to healthy instances. When Auto Scaling adds or removes instances, the load balancer dynamically updates its target list, maintaining high availability and performance.

---

**12. In a Classic Load Balancer, what is the purpose of the “sticky session” (session affinity) feature?**

A. To encrypt session data for enhanced security.  
B. To ensure that a user’s consecutive requests are directed to the same backend instance.  
C. To automatically balance the load across all available instances regardless of session data.  
D. To cache user sessions on the load balancer for faster access.

**Correct Answer:** B. To ensure that a user’s consecutive requests are directed to the same backend instance.  
**Explanation:** Sticky sessions maintain session state by directing all requests from a particular user to the same backend instance, which can be important for applications that store session information locally on the instance.

---

**13. During a lab session for creating an AWS Classic Load Balancer, which health check protocol is most commonly used to monitor web server availability?**

A. ICMP ping  
B. HTTP/HTTPS  
C. FTP  
D. SMTP

**Correct Answer:** B. HTTP/HTTPS  
**Explanation:** Health checks for web servers are typically performed using HTTP or HTTPS. This allows the load balancer to verify that the web application is responding correctly to requests by checking a specified URL or path.

---

**14. What happens if a target in an AWS Target Group fails its health checks repeatedly?**

A. The load balancer automatically redirects traffic to a backup target.  
B. The target is temporarily removed from the Target Group until it passes health checks again.  
C. The load balancer increases the target’s traffic allocation to help it recover.  
D. The target is permanently deregistered and requires manual re-registration.

**Correct Answer:** B. The target is temporarily removed from the Target Group until it passes health checks again.  
**Explanation:** When a target fails the configured health checks, it is marked as unhealthy and is temporarily removed from serving traffic. Once it passes subsequent health checks, it can be reinstated into the Target Group.

---

**15. Which statement best describes the role of a Listener in AWS Elastic Load Balancing?**

A. It defines the IP addresses permitted to access the load balancer.  
B. It configures the SSL certificate for secure communication only.  
C. It specifies the protocol and port on which the load balancer accepts incoming traffic.  
D. It monitors the health status of target instances.

**Correct Answer:** C. It specifies the protocol and port on which the load balancer accepts incoming traffic.  
**Explanation:** A Listener is the component that checks for incoming connections on a specified protocol and port. Once a connection is received, it forwards the request to an associated target group based on its rules.

---

**16. In a lab session for creating an AWS Target Group, which configuration is essential to ensure only healthy targets receive traffic?**

A. Assigning a static IP address to each target.  
B. Configuring detailed health check settings such as protocol, path, timeout, and interval.  
C. Enabling sticky sessions for the target group.  
D. Creating multiple listeners for redundancy.

**Correct Answer:** B. Configuring detailed health check settings such as protocol, path, timeout, and interval.  
**Explanation:** Health check settings are critical for assessing the availability and performance of each target. Proper configuration ensures that the load balancer routes traffic only to targets that are responsive and healthy.
