### What is AWS WAF?

**AWS WAF (Web Application Firewall):** AWS WAF is a web application firewall that helps protect your web applications from common web exploits that could affect application availability, compromise security, or consume excessive resources.

### How AWS WAF Works

AWS WAF works by allowing you to create rules that define the conditions under which the traffic should be allowed or blocked to your web applications. It operates on Layer 7 of the OSI model, which means it inspects HTTP and HTTPS requests.

Key features and workings of AWS WAF include:

1. **Conditions and Rules:** You can create conditions based on IP addresses, HTTP headers, URI strings, SQL injection strings, and more. Rules are then created to evaluate these conditions and take actions (allow, block, count, etc.) based on the match results.

2. **Web ACLs (Access Control Lists):** Web ACLs are collections of rules that identify potentially harmful traffic patterns. They are applied to CloudFront distributions, Application Load Balancers, or API Gateways to control which requests to allow or block.

3. **Managed Rule Sets:** AWS provides managed rule sets for common threats such as SQL injection, cross-site scripting (XSS), and known bad IP addresses. These can be used as part of your Web ACL to quickly implement protections against common attacks.

4. **Logging and Monitoring:** AWS WAF integrates with AWS CloudWatch for logging and monitoring, allowing you to gain insights into traffic patterns, rule effectiveness, and potential threats.

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

### Summary

AWS WAF provides essential protections for web applications against common exploits and threats by allowing you to create rules and conditions to filter and monitor HTTP and HTTPS traffic. Implementing Web ACLs, managing rules, and applying them to resources like ALBs are critical steps in securing your AWS-hosted applications from potential attacks.
