### What is AWS ACM?

**AWS ACM (AWS Certificate Manager):** AWS Certificate Manager is a service that lets you easily provision, manage, and deploy SSL/TLS certificates for use with AWS services and your internal connected resources.

### Lab Session - Creating AWS ACM

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS ACM Dashboard at [AWS Management Console](https://console.aws.amazon.com/acm/).

2. **Request a Certificate:**
   - Click on "Request a certificate."
   - Enter the domain names (e.g., example.com, *.example.com) for which you want to request the certificate.
   - Choose validation method (email validation or DNS validation).
   - Click "Next" to review and confirm the certificate request.
   - Complete the validation process based on the chosen method.

### Lab Session - Integrating AWS ACM with an Application Load Balancer

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS ACM Dashboard at [AWS Management Console](https://console.aws.amazon.com/acm/).

2. **Retrieve ACM Certificate:**
   - Find and select the ACM certificate you want to use.
   - Click on "Actions" -> "Edit in Amazon EC2 Console."
   - Copy the Amazon Resource Name (ARN) of the ACM certificate.

3. **Associate ACM Certificate with ALB:**
   - Navigate to the Amazon EC2 Console at [AWS Management Console](https://console.aws.amazon.com/ec2/).
   - Select "Load Balancers" from the navigation pane.
   - Choose the Application Load Balancer (ALB) where you want to associate the ACM certificate.
   - Click on "Listeners" tab, then "View/edit rules" for HTTPS listener.
   - Edit the listener to select the ACM certificate ARN for HTTPS traffic.
   - Save the changes to associate the ACM certificate with the ALB.

### Lab Session - Deletion of AWS ACM

1. **Sign in to AWS Management Console:**
   - Navigate to the AWS ACM Dashboard at [AWS Management Console](https://console.aws.amazon.com/acm/).

2. **Select Certificate:**
   - Choose the ACM certificate you want to delete.

3. **Delete ACM Certificate:**
   - Click on "Actions" -> "Delete."
   - Confirm the deletion when prompted.
