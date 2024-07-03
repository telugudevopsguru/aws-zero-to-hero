### What is CloudWatch?

**CloudWatch:** A monitoring and observability service from AWS that provides real-time monitoring of AWS resources and applications running on AWS.

### Key Features of CloudWatch

1. **Metrics:** Collect and track metrics, visualize them through graphs, and set alarms.
2. **Logs:** Collect, monitor, and store log files from AWS resources and applications.
3. **Events:** Respond to state changes in AWS resources with automated actions.
4. **Dashboards:** Create customizable dashboards to monitor your resources and applications.
5. **Alarms:** Set alarms to notify when certain thresholds are reached.

### Lab Session - Creating a Log Group in AWS CloudWatch

1. **Sign in to AWS Management Console:**
   - Navigate to the CloudWatch Dashboard at [AWS Management Console](https://console.aws.amazon.com/cloudwatch/).

2. **Create Log Group:**
   - Click on "Logs" in the left menu and then "Log groups."
   - Click on "Create log group."
   - Enter a name for the log group and click "Create log group."

### Lab Session - Sending VPC Flow Logs to a CloudWatch Log Group

1. **Sign in to AWS Management Console:**
   - Navigate to the VPC Dashboard at [AWS Management Console](https://console.aws.amazon.com/vpc/).

2. **Configure VPC Flow Logs:**
   - Select your VPC and click on "Flow Logs" in the left menu.
   - Click on "Create Flow Log."
   - Choose settings for flow log creation, including the destination log group in CloudWatch.
   - Review and create the flow log.

### Lab Session - Setting Up a CloudWatch Alarm for an EC2 Instance

1. **Sign in to AWS Management Console:**
   - Navigate to the CloudWatch Dashboard at [AWS Management Console](https://console.aws.amazon.com/cloudwatch/).

2. **Create Alarm:**
   - Click on "Alarms" in the left menu and then "Create alarm."
   - Choose the metric (e.g., CPU utilization) for the EC2 instance.
   - Configure the threshold and actions (e.g., send notification to SNS topic).
   - Review and create the alarm.

### What is AWS CloudTrail?

**AWS CloudTrail:** A service that enables governance, compliance, and operational and risk auditing of your AWS account. It records AWS API calls made on your account and delivers log files to an Amazon S3 bucket.

### Log Event Types in CloudTrail

1. **Management Events:** API calls related to management operations in AWS services (e.g., create, delete, modify).
2. **Data Events:** API calls related to data plane operations performed on resources in AWS services (e.g., S3 object-level API calls).

### Lab Session - Setting Up AWS CloudTrail to Send Logs to an S3 Bucket

1. **Sign in to AWS Management Console:**
   - Navigate to the CloudTrail Dashboard at [AWS Management Console](https://console.aws.amazon.com/cloudtrail/).

2. **Create Trail:**
   - Click on "Trails" in the left menu and then "Create trail."
   - Enter a name for the trail and choose the S3 bucket where log files will be delivered.
   - Configure trail settings, including log file encryption and CloudWatch Logs integration.
   - Review and create the trail.

### Lab Session - Deletion of CloudTrail

1. **Sign in to AWS Management Console:**
   - Navigate to the CloudTrail Dashboard at [AWS Management Console](https://console.aws.amazon.com/cloudtrail/).

2. **Delete CloudTrail:**
   - Select the CloudTrail trail you want to delete.
   - Click on "Actions > Delete trail."
   - Confirm the deletion.
