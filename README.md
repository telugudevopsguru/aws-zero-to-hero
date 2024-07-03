### What is AWS ECR?

**Amazon Elastic Container Registry (ECR):** A fully managed Docker container registry service provided by AWS. It allows developers to store, manage, and deploy Docker container images.

### Types of Repositories in AWS ECR

1. **Private Repositories:** Used to store and manage Docker container images privately.
2. **Public Repositories:** Used to share Docker container images publicly.

### Components of Amazon ECR

1. **Registry:** A collection of repositories, managed within an AWS account.
2. **Repository:** A collection of Docker images, with versioning support.
3. **Image:** A Docker container image stored in a repository.

### Features of Amazon ECR

1. **Fully Managed:** AWS manages infrastructure provisioning, scaling, and availability.
2. **Integrated with AWS Services:** Works seamlessly with services like Amazon ECS, Kubernetes, and AWS CodePipeline.
3. **Security:** Integrates with IAM for access control and supports encryption of images at rest.

### Lab Session - Creating an ECR Repository in AWS

1. **Sign in to AWS Management Console:**
   - Navigate to the ECR Dashboard at [AWS Management Console](https://console.aws.amazon.com/ecr/).

2. **Create ECR Repository:**
   - Click on "Create repository."
   - Enter a name for the repository.
   - Optionally, configure repository settings such as image scanning.
   - Click "Create repository."

### Lab Session - Pushing a Docker Image to AWS ECR

1. **Install Docker:** Ensure Docker is installed on your local machine.

2. **Authenticate Docker with ECR:**
   - Run `aws ecr get-login-password --region <region>` to retrieve authentication token.
   - Run `docker login -u AWS -p <password> <aws_account_id>.dkr.ecr.<region>.amazonaws.com` to authenticate Docker with ECR.

3. **Tag Docker Image:**
   - Tag your Docker image using `docker tag <local_image>:<tag> <aws_account_id>.dkr.ecr.<region>.amazonaws.com/<repository_name>:<tag>`.

4. **Push Docker Image:**
   - Push your Docker image to ECR using `docker push <aws_account_id>.dkr.ecr.<region>.amazonaws.com/<repository_name>:<tag>`.

### Lab Session - Setting up Lifecycle Policy in ECR

1. **Sign in to AWS Management Console:**
   - Navigate to the ECR Dashboard at [AWS Management Console](https://console.aws.amazon.com/ecr/).

2. **Set Lifecycle Policy:**
   - Select your repository and click on "Lifecycle policy."
   - Click on "Edit policy."
   - Define rules for image lifecycle management, such as expiring images after a certain number of days.
   - Save the policy.

### Lab Session - Setting up Replication Configuration in ECR

1. **Sign in to AWS Management Console:**
   - Navigate to the ECR Dashboard at [AWS Management Console](https://console.aws.amazon.com/ecr/).

2. **Configure Replication:**
   - Select your repository and click on "Replication configuration."
   - Click on "Edit replication configuration."
   - Define replication rules to replicate images to other AWS regions for improved availability.
   - Save the configuration.
