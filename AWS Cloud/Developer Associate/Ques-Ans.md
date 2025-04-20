## ❓ AWS DevOps & Cloud Q/A

### Amazon ECS

**How does Amazon ECS handle service discovery for tasks within the same VPC?**  
**A:** C) It integrates with AWS Cloud Map for service discovery.

**What is the default scheduler for Amazon ECS?**  
**A:** C) ECS Service Scheduler

**How do you update a running service to use a new container image version in ECS?**  
**A:** B) Update the task definition with the new image and redeploy the service.

---

### Amazon ECR

**How do you enforce image scanning in Amazon ECR?**  
**A:** B) By turning on ECR image scanning on push.

**Which AWS CLI command lists all repositories in Amazon ECR?**  
**A:** A) aws ecr describe-repositories

---

### Amazon EKS

**What component ensures high availability of the Kubernetes API server in EKS?**  
**A:** C) AWS Managed Control Plane

**Which service is responsible for storing cluster configuration data in EKS?**  
**A:** D) etcd

---

### AWS App Mesh

**What is the main advantage of using AWS App Mesh with ECS?**  
**A:** B) It simplifies service-to-service communication in microservices architectures.

---

### AWS Elastic Beanstalk

**Which deployment strategy is NOT supported in Elastic Beanstalk?**  
**A:** C) Canary deployments

**How does Elastic Beanstalk handle logging?**  
**A:** A) Logs can be viewed and stored in Amazon S3

---

### AWS CloudFormation

**In CloudFormation, what is a "Stack"?**  
**A:** D) A collection of AWS resources managed as a unit

---

### AWS CodeDeploy

**Which AWS service allows blue/green deployments for ECS?**  
**A:** A) AWS CodeDeploy

**What are the two types of deployment approaches in AWS CodeDeploy?**  
**A:** C) In-place and Blue/Green

**AWS CodeDeploy hooks can be used for which purpose?**  
**A:** B) Running scripts before and after deployment

---

### AWS Config

**Which AWS service integrates with CloudFormation to enforce security policies?**  
**A:** B) AWS Config

---

### AWS CodeCommit

**What is the default AWS CodeCommit branch protection rule?**  
**A:** D) No default branch protection

**What is the main benefit of integrating AWS Cloud9 with CodeCommit?**  
**A:** B) Provides real-time code collaboration

---

### AWS SAM (Serverless Application Model)

**When using AWS SAM to deploy an application, what is required for `sam deploy` to work correctly?**  
**A:** A) A manually created S3 bucket

**Which AWS SAM feature allows defining multiple resources and deploying them as a single application?**  
**A:** D) AWS SAM Applications

---

### AWS Cognito

**What is the default expiration time for an AWS Cognito Access Token?**  
**A:** B) 1 hour

---

### AWS Amplify

**AWS Amplify allows you to create backend resources using which technology?**  
**A:** B) AWS CloudFormation  
**A:** C) AWS CDK

**What type of hosting does AWS Amplify provide for front-end applications?**  
**A:** A) Static web hosting

---

### AWS Step Functions

**What is the maximum execution duration for an AWS Step Function Standard Workflow?**  
**A:** C) 1 year

---

### AWS AppSync

**AWS AppSync resolvers use which template language to map requests and responses?**  
**A:** C) Apache Velocity Template Language (VTL)
