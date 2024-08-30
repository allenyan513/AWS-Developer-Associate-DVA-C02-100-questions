Question #71Topic 1

A developer is working on an existing application that uses Amazon DynamoDB as its data store. The DynamoDB table has the following attributes: partNumber (partition key), vendor (sort key), description, productFamily, and productType. When the developer analyzes the usage patterns, the developer notices that there are application modules that frequently look for a list of products based on the productFamily and productType attributes.  
  
The developer wants to make changes to the application to improve performance of the query operations.  
  
Which solution will meet these requirements?

- A. Create a global secondary index (GSI) with productFamily as the partition key and productType as the sort key.
- B. Create a local secondary index (LSI) with productFamily as the partition key and productType as the sort key.
- C. Recreate the table. Add partNumber as the partition key and vendor as the sort key. During table creation, add a local secondary index (LSI) with productFamily as the partition key and productType as the sort key.
- D. Update the queries to use Scan operations with productFamily as the partition key and productType as the sort key.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   6](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #72Topic 1

A developer creates a VPC named VPC-A that has public and private subnets. The developer also creates an Amazon RDS database inside the private subnet of VPC-A. To perform some queries, the developer creates an AWS Lambda function in the default VPC. The Lambda function has code to access the RDS database. When the Lambda function runs, an error message indicates that the function cannot connect to the RDS database.  
  
How can the developer solve this problem?

- A. Modify the RDS security group. Add a rule to allow traffic from all the ports from the VPC CIDR block.
- B. Redeploy the Lambda function in the same subnet as the RDS instance. Ensure that the RDS security group allows traffic from the Lambda function.
- C. Create a security group for the Lambda function. Add a new rule in the RDS security group to allow traffic from the new Lambda security group.
- D. Create an IAM role. Attach a policy that allows access to the RDS database. Attach the role to the Lambda function.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   32](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #73Topic 1

A company runs an application on AWS. The company deployed the application on Amazon EC2 instances. The application stores data on Amazon Aurora.  
  
The application recently logged multiple application-specific custom DECRYP_ERROR errors to Amazon CloudWatch logs. The company did not detect the issue until the automated tests that run every 30 minutes failed. A developer must implement a solution that will monitor for the custom errors and alert a development team in real time when these errors occur in the production environment.  
  
Which solution will meet these requirements with the LEAST operational overhead?

- A. Configure the application to create a custom metric and to push the metric to CloudWatch. Create an AWS CloudTrail alarm. Configure the CloudTrail alarm to use an Amazon Simple Notification Service (Amazon SNS) topic to send notifications.
- B. Create an AWS Lambda function to run every 5 minutes to scan the CloudWatch logs for the keyword DECRYP_ERROR. Configure the Lambda function to use Amazon Simple Notification Service (Amazon SNS) to send a notification.
- C. Use Amazon CloudWatch Logs to create a metric filter that has a filter pattern for DECRYP_ERROR. Create a CloudWatch alarm on this metric for a threshold >=1. Configure the alarm to send Amazon Simple Notification Service (Amazon SNS) notifications.
- D. Install the CloudWatch unified agent on the EC2 instance. Configure the application to generate a metric for the keyword DECRYP_ERROR errors. Configure the agent to send Amazon Simple Notification Service (Amazon SNS) notifications.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   6](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #74Topic 1

A developer created an AWS Lambda function that accesses resources in a VPC. The Lambda function polls an Amazon Simple Queue Service (Amazon SQS) queue for new messages through a VPC endpoint. Then the function calculates a rolling average of the numeric values that are contained in the messages. After initial tests of the Lambda function, the developer found that the value of the rolling average that the function returned was not accurate.  
  
How can the developer ensure that the function calculates an accurate rolling average?

- A. Set the function's reserved concurrency to 1. Calculate the rolling average in the function. Store the calculated rolling average in Amazon ElastiCache.
- B. Modify the function to store the values in Amazon ElastiCache. When the function initializes, use the previous values from the cache to calculate the rolling average.
- C. Set the function's provisioned concurrency to 1. Calculate the rolling average in the function. Store the calculated rolling average in Amazon ElastiCache.
- D. Modify the function to store the values in the function's layers. When the function initializes, use the previously stored values to calculate the rolling average.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   34](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #75Topic 1

A developer is writing unit tests for a new application that will be deployed on AWS. The developer wants to validate all pull requests with unit tests and merge the code with the main branch only when all tests pass.  
  
The developer stores the code in AWS CodeCommit and sets up AWS CodeBuild to run the unit tests. The developer creates an AWS Lambda function to start the CodeBuild task. The developer needs to identify the CodeCommit events in an Amazon EventBridge event that can invoke the Lambda function when a pull request is created or updated.  
  
Which CodeCommit event will meet these requirements?

- A. ![](https://img.examtopics.com/aws-certified-developer-associate-dva-c02/image4.png)  
    
- B. ![](https://img.examtopics.com/aws-certified-developer-associate-dva-c02/image5.png)  
    
- C. ![](https://img.examtopics.com/aws-certified-developer-associate-dva-c02/image6.png)  
    
- D. ![](https://img.examtopics.com/aws-certified-developer-associate-dva-c02/image7.png)

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   10](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #76Topic 1

A developer deployed an application to an Amazon EC2 instance. The application needs to know the public IPv4 address of the instance.  
  
How can the application find this information?

- A. Query the instance metadata from http://169.254.169.254/latest/meta-data/.
- B. Query the instance user data from http://169.254.169.254/latest/user-data/.
- C. Query the Amazon Machine Image (AMI) information from http://169.254.169.254/latest/meta-data/ami/.
- D. Check the hosts file of the operating system.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   6](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #77Topic 1

An application under development is required to store hundreds of video files. The data must be encrypted within the application prior to storage, with a unique key for each video file.  
  
How should the developer code the application?

- A. Use the KMS Encrypt API to encrypt the data. Store the encrypted data key and data.
- B. Use a cryptography library to generate an encryption key for the application. Use the encryption key to encrypt the data. Store the encrypted data.
- C. Use the KMS GenerateDataKey API to get a data key. Encrypt the data with the data key. Store the encrypted data key and data.
- D. Upload the data to an S3 bucket using server side-encryption with an AWS KMS key.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   5](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #78Topic 1

A company is planning to deploy an application on AWS behind an Elastic Load Balancer. The application uses an HTTP/HTTPS listener and must access the client IP addresses.  
  
Which load-balancing solution meets these requirements?

- A. Use an Application Load Balancer and the X-Forwarded-For headers.
- B. Use a Network Load Balancer (NLB). Enable proxy protocol support on the NLB and the target application.
- C. Use an Application Load Balancer. Register the targets by the instance ID.
- D. Use a Network Load Balancer and the X-Forwarded-For headers.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   5](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #79Topic 1

A developer wants to debug an application by searching and filtering log data. The application logs are stored in Amazon CloudWatch Logs. The developer creates a new metric filter to count exceptions in the application logs. However, no results are returned from the logs.  
  
What is the reason that no filtered results are being returned?

- A. A setup of the Amazon CloudWatch interface VPC endpoint is required for filtering the CloudWatch Logs in the VPC.
- B. CloudWatch Logs only publishes metric data for events that happen after the filter is created.
- C. The log group for CloudWatch Logs should be first streamed to Amazon OpenSearch Service before metric filtering returns the results.
- D. Metric data points for logs groups can be filtered only after they are exported to an Amazon S3 bucket.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)    [Discussion   4](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/8/#)

Question #80Topic 1

A company is planning to use AWS CodeDeploy to deploy an application to Amazon Elastic Container Service (Amazon ECS). During the deployment of a new version of the application, the company initially must expose only 10% of live traffic to the new version of the deployed application. Then, after 15 minutes elapse, the company must route all the remaining live traffic to the new version of the deployed application.  
  
Which CodeDeploy predefined configuration will meet these requirements?

- A. CodeDeployDefault.ECSCanary10Percent15Minutes
- B. CodeDeployDefault.LambdaCanary10Percent5Minutes
- C. CodeDeployDefault.LambdaCanary10Percentl15Minutes
- D. CodeDeployDefault.ECSLinear10PercentEvery1Minutes