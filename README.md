### What is an AWS Network Load Balancer?

AWS Network Load Balancer (NLB) is a load balancing solution designed to handle high volumes of traffic with low latency. It operates at the transport layer (Layer 4) and is capable of handling millions of requests per second while maintaining ultra-low latencies.

### Benefits of an AWS Network Load Balancer

1. **High Throughput:** Handles millions of requests per second with ultra-low latencies.
2. **Static IP:** Provides a static IP address per Availability Zone (AZ) for easy integration with applications.
3. **TLS Termination:** Supports TLS termination for end-to-end encryption.
4. **Target Group Support:** Routes traffic to target groups using IP addresses and ports.
5. **Health Checks:** Performs health checks on targets to ensure only healthy targets receive traffic.
----
### Lab Session - Creation of an AWS Network Load Balancer

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Create Network Load Balancer:**
   - Click on "Load Balancers" in the left sidebar under "EC2."
   - Click on "Create Load Balancer" and choose "Network Load Balancer."
   - Configure load balancer settings, including listeners, availability zones, security settings, and target groups.
   - Complete the creation and note the DNS name provided for your Network Load Balancer.
----
### Lab Session - Deletion of an NLB

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Delete Network Load Balancer:**
   - Click on "Load Balancers" in the left sidebar under "EC2."
   - Select the Network Load Balancer you want to delete.
   - Click on "Actions > Delete" and confirm the deletion.
----
### Difference between an ALB and an NLB

**AWS Application Load Balancer (ALB):**
- Operates at Layer 7 (Application layer).
- Ideal for HTTP/HTTPS traffic and provides advanced routing features like content-based routing and host-based routing.
- Supports URL-based routing and WebSocket traffic.
- Provides integration with AWS WAF for web application firewall protection.

**AWS Network Load Balancer (NLB):**
- Operates at Layer 4 (Transport layer).
- Ideal for handling millions of requests per second with ultra-low latencies.
- Routes traffic based on IP addresses and ports.
- Supports TLS termination for end-to-end encryption.
- Provides static IP addresses per Availability Zone (AZ).
----
### Lab Session - Attaching an ALB to a New Auto Scaling Group

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Create Auto Scaling Group (ASG):**
   - Click on "Auto Scaling Groups" in the left sidebar under "Auto Scaling."
   - Click on "Create Auto Scaling group" and follow the wizard to create a new Auto Scaling group.
   - Configure scaling policies, network settings, and tags.
   - Choose the existing Application Load Balancer (ALB) during the creation process to attach it to the Auto Scaling group.
----
### Lab Session - Attaching an ALB to an Existing Auto Scaling Group

1. **Sign in to AWS Management Console:**
   - Navigate to the EC2 Dashboard at [AWS Management Console](https://console.aws.amazon.com/ec2/).

2. **Modify Auto Scaling Group (ASG):**
   - Click on "Auto Scaling Groups" in the left sidebar under "Auto Scaling."
   - Select the Auto Scaling group to which you want to attach the Application Load Balancer (ALB).
   - Click on "Edit" and modify the ASG settings to attach the existing ALB.
   - Update the Auto Scaling group configuration to include the ALB and complete the modification process.
