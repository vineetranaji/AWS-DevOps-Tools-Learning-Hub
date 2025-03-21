# AWS CLI Commands

This document provides a list of useful AWS CLI commands for managing AWS resources.

## AWS Configuration and Setup

### `aws configure`
- Configures AWS CLI with your credentials (Access Key, Secret Key, Region, and Output Format).

### `aws configure list`
- Displays the current configuration settings (Access Key, Secret Key, Region, etc.).

### `aws configure get <config_value>`
- Retrieves a specific configuration value (e.g., `aws configure get region`).

### `aws configure set <config_value> <value>`
- Sets a specific configuration value (e.g., `aws configure set region us-west-2`).

## AWS EC2 Commands

### `aws ec2 describe-instances`
- Lists all EC2 instances.

### `aws ec2 describe-instances --instance-ids <instance_id>`
- Describes specific EC2 instances by instance IDs.

### `aws ec2 run-instances --image-id <image_id> --instance-type <instance_type> --key-name <key_name>`
- Launches a new EC2 instance with the specified image, instance type, and key pair.

### `aws ec2 start-instances --instance-ids <instance_id>`
- Starts one or more stopped EC2 instances.

### `aws ec2 stop-instances --instance-ids <instance_id>`
- Stops one or more running EC2 instances.

### `aws ec2 terminate-instances --instance-ids <instance_id>`
- Terminates one or more EC2 instances.

### `aws ec2 reboot-instances --instance-ids <instance_id>`
- Reboots one or more EC2 instances.

### `aws ec2 describe-security-groups`
- Lists all security groups.

### `aws ec2 describe-key-pairs`
- Lists all EC2 key pairs.

## AWS S3 Commands

### `aws s3 ls`
- Lists all S3 buckets in your account.

### `aws s3 ls s3://<bucket_name>`
- Lists the contents of a specific S3 bucket.

### `aws s3 cp <file> s3://<bucket_name>/`
- Uploads a file to a specified S3 bucket.

### `aws s3 cp s3://<bucket_name>/<file> <local_path>`
- Downloads a file from an S3 bucket to the local machine.

### `aws s3 sync <local_directory> s3://<bucket_name>/`
- Syncs a local directory to an S3 bucket.

### `aws s3 rm s3://<bucket_name>/<file>`
- Deletes a file from an S3 bucket.

### `aws s3 mb s3://<bucket_name>`
- Creates a new S3 bucket.

### `aws s3 rb s3://<bucket_name> --force`
- Removes an S3 bucket and all its contents.

## AWS IAM Commands

### `aws iam create-user --user-name <user_name>`
- Creates a new IAM user.

### `aws iam delete-user --user-name <user_name>`
- Deletes an IAM user.

### `aws iam list-users`
- Lists all IAM users.

### `aws iam attach-user-policy --user-name <user_name> --policy-arn <policy_arn>`
- Attaches a policy to an IAM user.

### `aws iam detach-user-policy --user-name <user_name> --policy-arn <policy_arn>`
- Detaches a policy from an IAM user.

### `aws iam create-group --group-name <group_name>`
- Creates a new IAM group.

### `aws iam add-user-to-group --group-name <group_name> --user-name <user_name>`
- Adds a user to an IAM group.

### `aws iam remove-user-from-group --group-name <group_name> --user-name <user_name>`
- Removes a user from an IAM group.

## AWS Lambda Commands

### `aws lambda list-functions`
- Lists all Lambda functions in your account.

### `aws lambda create-function --function-name <function_name> --runtime <runtime> --role <role_arn> --handler <handler> --zip-file fileb://<file.zip>`
- Creates a new Lambda function.

### `aws lambda invoke --function-name <function_name> output.txt`
- Invokes a Lambda function.

### `aws lambda update-function-code --function-name <function_name> --zip-file fileb://<file.zip>`
- Updates the code of an existing Lambda function.

### `aws lambda delete-function --function-name <function_name>`
- Deletes a Lambda function.

## AWS CloudFormation Commands

### `aws cloudformation create-stack --stack-name <stack_name> --template-body file://<template_file>`
- Creates a new CloudFormation stack.

### `aws cloudformation delete-stack --stack-name <stack_name>`
- Deletes a CloudFormation stack.

### `aws cloudformation describe-stacks`
- Describes all CloudFormation stacks in your account.

### `aws cloudformation describe-stack-resources --stack-name <stack_name>`
- Lists resources in a specific CloudFormation stack.

## AWS VPC Commands

### `aws ec2 describe-vpcs`
- Lists all VPCs in your account.

### `aws ec2 create-vpc --cidr-block <cidr_block>`
- Creates a new VPC with a specified CIDR block.

### `aws ec2 delete-vpc --vpc-id <vpc_id>`
- Deletes a specified VPC.

### `aws ec2 describe-subnets`
- Lists all subnets in your account.

### `aws ec2 create-subnet --vpc-id <vpc_id> --cidr-block <cidr_block>`
- Creates a new subnet in a specified VPC.

### `aws ec2 delete-subnet --subnet-id <subnet_id>`
- Deletes a specified subnet.

### `aws ec2 describe-security-groups`
- Lists all security groups in your account.

### `aws ec2 create-security-group --group-name <group_name> --description <description> --vpc-id <vpc_id>`
- Creates a new security group in a VPC.

### `aws ec2 authorize-security-group-ingress --group-id <group_id> --protocol tcp --port <port> --cidr <cidr_block>`
- Adds an inbound rule to a security group.

### `aws ec2 revoke-security-group-ingress --group-id <group_id> --protocol tcp --port <port> --cidr <cidr_block>`
- Removes an inbound rule from a security group.

## AWS RDS Commands

### `aws rds describe-db-instances`
- Lists all RDS instances in your account.

### `aws rds create-db-instance --db-instance-identifier <db_instance_identifier> --allocated-storage <storage_size> --db-instance-class <db_instance_class> --engine <db_engine> --master-username <username> --master-user-password <password>`
- Creates a new RDS database instance.

### `aws rds delete-db-instance --db-instance-identifier <db_instance_identifier>`
- Deletes an RDS database instance.

### `aws rds modify-db-instance --db-instance-identifier <db_instance_identifier> --apply-immediately`
- Modifies an existing RDS database instance.

## AWS CloudWatch Commands

### `aws cloudwatch describe-alarms`
- Lists all CloudWatch alarms.

### `aws cloudwatch set-alarm-state --alarm-name <alarm_name> --state-value <state_value> --state-reason <state_reason>`
- Sets the state of a CloudWatch alarm.

### `aws cloudwatch put-metric-data --namespace <namespace> --metric-name <metric_name> --value <value>`
- Publishes custom metric data to CloudWatch.

## AWS SQS Commands

### `aws sqs list-queues`
- Lists all SQS queues.

### `aws sqs create-queue --queue-name <queue_name>`
- Creates a new SQS queue.

### `aws sqs delete-queue --queue-url <queue_url>`
- Deletes a specified SQS queue.

### `aws sqs send-message --queue-url <queue_url> --message-body <message_body>`
- Sends a message to an SQS queue.

### `aws sqs receive-message --queue-url <queue_url>`
- Receives messages from an SQS queue.

## AWS EC2 Spot Instances Commands

### `aws ec2 request-spot-instances --spot-price <price> --instance-count <count> --type <type> --launch-specification <spec>`
- Requests a Spot instance.

### `aws ec2 describe-spot-instance-requests`
- Describes the status of Spot instance requests.

### `aws ec2 cancel-spot-instance-requests --spot-instance-request-ids <request_ids>`
- Cancels one or more Spot instance requests.

## Other Useful AWS CLI Commands

### `aws sts get-caller-identity`
- Displays the IAM identity (user/role) associated with the current credentials.

### `aws s3api create-bucket --bucket <bucket_name> --region <region>`
- Creates an S3 bucket in a specified region.

### `aws iam list-users`
- Lists all IAM users in your account.
