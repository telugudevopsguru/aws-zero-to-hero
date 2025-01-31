### What is AWS WAF?

- AWS WAF, or AWS Web Application Firewall, is a managed service provided by Amazon Web Services (AWS) that helps protect your web applications from common web exploits that could affect application availability, compromise security, or consume excessive resources.
- It allows you to control which traffic to allow or block to your web applications by defining customizable web security rules.
  
## What it Protects

- **Amazon CloudFront distributions**
- **Amazon API Gateway REST APIs**
- **Application Load Balancers**
- **AWS AppSync GraphQL APIs**
- **Amazon Cognito user pools**
- **AWS App Runner services**
- **AWS Verified Access instances**

  
### Key Features of AWS WAF:

1. **Managed Rulesets**:
   - AWS WAF provides managed rulesets that include pre-configured rules to protect against common threats such as SQL injection, cross-site scripting (XSS), and known bad bots.
   - These rulesets are regularly updated to include new protections.

2. **Customizable Rules**:
   - You can create custom rules to define specific conditions under which the AWS WAF should allow, block, or monitor web requests.
   - These rules can be based on IP addresses, HTTP headers, URI strings, or combinations thereof.

3. **Integration with AWS Services**:
   - AWS WAF integrates seamlessly with other AWS services like Amazon CloudFront (CDN), Application Load Balancer (ALB), API Gateway, and AWS AppSync, allowing you to protect applications deployed on these services.

4. **Monitoring and Logging**:
   - AWS WAF provides metrics and logs through AWS CloudWatch, giving you visibility into web traffic patterns and potential security threats.
   - You can set up alarms based on these metrics to alert you to potential attacks.

5. **Scalability and Performance**:
   - AWS WAF automatically scales with your application traffic and provides low-latency performance by leveraging AWS's global network of edge locations.

6. **Rate Limiting and Bot Control**:
   - You can configure rate-based rules to protect against application-layer attacks such as brute force login attempts or HTTP floods. AWS WAF also includes bot control features to identify and mitigate automated threats.

### Lab Sessions:

#### Creating a Web ACL

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS WAF & Shield Dashboard at [AWS Management Console](https://console.aws.amazon.com/wafv2/).

2. **Create a Web ACL:**
   - Click on "Create Web ACL."
   - Enter a name and description for your Web ACL.
   - Define rules using conditions (e.g., IP addresses, HTTP headers, URI strings).
   - Add rules to the Web ACL and configure actions (allow, block, count, etc.) based on rule matches.
   - Click "Create" to create the Web ACL.

#### Applying the Web ACL to an ALB (Application Load Balancer)

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS WAF & Shield Dashboard at [AWS Management Console](https://console.aws.amazon.com/wafv2/).

2. **Select Web ACL:**
   - Choose the Web ACL you created or want to apply.

3. **Associate with ALB:**
   - Click on "Associations" in the left-hand navigation pane.
   - Click "Add association" to associate the Web ACL with your Application Load Balancer (ALB).
   - Select the ALB and configure the association settings.
   - Save the association to apply the Web ACL to the ALB.
----
#### Blocking a Specific IP Address

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS WAF & Shield Dashboard at [AWS Management Console](https://console.aws.amazon.com/wafv2/).

2. **Create IP Set:**
   - Go to "IP sets" in the left-hand navigation pane.
   - Click on "Create IP set."
   - Enter a name for the IP set and add the IP addresses you want to block.

3. **Create Rule to Block IP:**
   - Go to "Rules" in the left-hand navigation pane.
   - Click on "Create rule."
   - Define a condition based on IP addresses and select the IP set you created.
   - Set the action to "Block."
   - Save the rule.

4. **Associate Rule with Web ACL:**
   - Go to the Web ACL where you want to apply the rule.
   - Add the rule to the Web ACL.
   - Save the changes to apply the rule, effectively blocking the specified IP addresses.

---

## 🔹 **1️⃣ AWS WAF Logs & CloudWatch Integration**  

✅ **Enabling AWS WAF Logging**  
- AWS WAF provides detailed logs of blocked and allowed requests.  
- Logging can be enabled for WebACLs and sent to:  
  - **Amazon S3** (for archival and analysis)  
  - **Amazon Kinesis Data Firehose** (for real-time processing)  
  - **CloudWatch Logs** (for monitoring and alerting)  

🔧 **Steps to Enable WAF Logging in CloudWatch**  
1. Go to the **AWS WAF Console**.  
2. Select your **WebACL** and navigate to the **Logging and Metrics** tab.  
3. Choose **Enable Logging**, select **CloudWatch Logs**, and configure the log destination.  
4. Apply filtering options to capture specific request details.  

🚀 **Benefits of CloudWatch Integration:**  
- Real-time visibility into **malicious traffic patterns**.  
- Ability to create **custom dashboards** for WAF logs.  
- Setting up **CloudWatch Alarms** for threat detection.  

---

## 🔹 **2️⃣ Analyzing Blocked & Allowed Requests**  

🔍 **Understanding AWS WAF Logs Format**  
- Logs contain critical information like:  
  - Source IP  
  - Request URI  
  - User-Agent  
  - Rule that triggered the action (ALLOW/BLOCK/COUNT)  
  - Country of origin  

---

## 🔹 **3️⃣ Configuring AWS WAF Metrics**  

📡 **Using CloudWatch Metrics for AWS WAF**  
AWS WAF automatically sends the following metrics to **Amazon CloudWatch**:  
- **AllowedRequests** – Number of requests allowed by WebACL rules.  
- **BlockedRequests** – Number of requests blocked by WebACL rules.  
- **CountedRequests** – Requests that match rules but are not blocked.  

📊 **Creating Custom CloudWatch Dashboards**  
- Navigate to **CloudWatch > Dashboards**.  
- Add a new widget with **AWS WAF Metrics** (AllowedRequests, BlockedRequests).  
- Apply **filters** to monitor specific rules or IP addresses.  

🚨 **Setting Up CloudWatch Alarms**  
- Create an **Alarm** for high blocked requests (>1000 in 5 min).  
- Configure SNS notifications to **alert security teams**.  
- Automate remediation using **AWS Lambda** (e.g., block a suspicious IP).  
