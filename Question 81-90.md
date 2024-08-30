Question #81Topic 1

A company hosts a batch processing application on AWS Elastic Beanstalk with instances that run the most recent version of Amazon Linux. The application sorts and processes large datasets.  
  
In recent weeks, the application's performance has decreased significantly during a peak period for traffic. A developer suspects that the application issues are related to the memory usage. The developer checks the Elastic Beanstalk console and notices that memory usage is not being tracked.  
  
How should the developer gather more information about the application performance issues?

- A. Configure the Amazon CloudWatch agent to push logs to Amazon CloudWatch Logs by using port 443.
- B. Configure the Elastic Beanstalk .ebextensions directory to track the memory usage of the instances.
- C. Configure the Amazon CloudWatch agent to track the memory usage of the instances.
- D. Configure an Amazon CloudWatch dashboard to track the memory usage of the instances.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   27](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #82Topic 1

A developer is building a highly secure healthcare application using serverless components. This application requires writing temporary data to /tmp storage on an AWS Lambda function.  
  
How should the developer encrypt this data?

- A. Enable Amazon EBS volume encryption with an AWS KMS key in the Lambda function configuration so that all storage attached to the Lambda function is encrypted.
- B. Set up the Lambda function with a role and key policy to access an AWS KMS key. Use the key to generate a data key used to encrypt all data prior to writing to /tmp storage.
- C. Use OpenSSL to generate a symmetric encryption key on Lambda startup. Use this key to encrypt the data prior to writing to /tmp.
- D. Use an on-premises hardware security module (HSM) to generate keys, where the Lambda function requests a data key from the HSM and uses that to encrypt data on all requests to the function.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   6](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #83Topic 1

A developer has created an AWS Lambda function to provide notification through Amazon Simple Notification Service (Amazon SNS) whenever a file is uploaded to Amazon S3 that is larger than 50 MB. The developer has deployed and tested the Lambda function by using the CLI. However, when the event notification is added to the S3 bucket and a 3,000 MB file is uploaded, the Lambda function does not launch.  
  
Which of the following is a possible reason for the Lambda function's inability to launch?

- A. The S3 event notification does not activate for files that are larger than 1,000 MB.
- B. The resource-based policy for the Lambda function does not have the required permissions to be invoked by Amazon S3.
- C. Lambda functions cannot be invoked directly from an S3 event.
- D. The S3 bucket needs to be made public.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   9](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #84Topic 1

A developer is creating a Ruby application and needs to automate the deployment, scaling, and management of an environment without requiring knowledge of the underlying infrastructure.  
  
Which service would best accomplish this task?

- A. AWS CodeDeploy
- B. AWS CloudFormation
- C. AWS OpsWorks
- D. AWS Elastic Beanstalk

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   4](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #85Topic 1

A company has a web application that is deployed on AWS. The application uses an Amazon API Gateway API and an AWS Lambda function as its backend.  
  
The application recently demonstrated unexpected behavior. A developer examines the Lambda function code, finds an error, and modifies the code to resolve the problem. Before deploying the change to production, the developer needs to run tests to validate that the application operates properly.  
  
The application has only a production environment available. The developer must create a new development environment to test the code changes. The developer must also prevent other developers from overwriting these changes during the test cycle.  
  
Which combination of steps will meet these requirements with the LEAST development effort? (Choose two.)

- A. Create a new resource in the current stage. Create a new method with Lambda proxy integration. Select the Lambda function. Add the hotfix alias. Redeploy the current stage. Test the backend.
- B. Update the Lambda function in the API Gateway API integration request to use the hotfix alias. Deploy the API Gateway API to a new stage named hotfix. Test the backend.
- C. Modify the Lambda function by fixing the code. Test the Lambda function. Create the alias hotfix. Point the alias to the $LATEST version.
- D. Modify the Lambda function by fixing the code. Test the Lambda function. When the Lambda function is working as expected, publish the Lambda function as a new version. Create the alias hotfix. Point the alias to the new version.
- E. Create a new API Gateway API for the development environment. Add a resource and method with Lambda integration. Choose the Lambda function and the hotfix alias. Deploy to a new stage. Test the backend.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   9](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #86Topic 1

A developer is implementing an AWS Cloud Development Kit (AWS CDK) serverless application. The developer will provision several AWS Lambda functions and Amazon API Gateway APIs during AWS CloudFormation stack creation. The developer's workstation has the AWS Serverless Application Model (AWS SAM) and the AWS CDK installed locally.  
  
How can the developer test a specific Lambda function locally?

- A. Run the sam package and sam deploy commands. Create a Lambda test event from the AWS Management Console. Test the Lambda function.
- B. Run the cdk synth and cdk deploy commands. Create a Lambda test event from the AWS Management Console. Test the Lambda function.
- C. Run the cdk synth and sam local invoke commands with the function construct identifier and the path to the synthesized CloudFormation template.
- D. Run the cdk synth and sam local start-lambda commands with the function construct identifier and the path to the synthesized CloudFormation template.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   9](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #87Topic 1

A company's new mobile app uses Amazon API Gateway. As the development team completes a new release of its APIs, a developer must safely and transparently roll out the API change.  
  
What is the SIMPLEST solution for the developer to use for rolling out the new API version to a limited number of users through API Gateway?

- A. Create a new API in API Gateway. Direct a portion of the traffic to the new API using an Amazon Route 53 weighted routing policy.
- B. Validate the new API version and promote it to production during the window of lowest expected utilization.
- C. Implement an Amazon CloudWatch alarm to trigger a rollback if the observed HTTP 500 status code rate exceeds a predetermined threshold.
- D. Use the canary release deployment option in API Gateway. Direct a percentage of the API traffic using the canarySettings setting.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   3](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #88Topic 1

A company caches session information for a web application in an Amazon DynamoDB table. The company wants an automated way to delete old items from the table.  
  
What is the simplest way to do this?

- A. Write a script that deletes old records; schedule the script as a cron job on an Amazon EC2 instance.
- B. Add an attribute with the expiration time; enable the Time To Live feature based on that attribute.
- C. Each day, create a new table to hold session data; delete the previous day's table.
- D. Add an attribute with the expiration time; name the attribute ItemExpiration.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   4](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #89Topic 1

A company is using an Amazon API Gateway REST API endpoint as a webhook to publish events from an on-premises source control management (SCM) system to Amazon EventBridge. The company has configured an EventBridge rule to listen for the events and to control application deployment in a central AWS account. The company needs to receive the same events across multiple receiver AWS accounts.  
  
How can a developer meet these requirements without changing the configuration of the SCM system?

- A. Deploy the API Gateway REST API to all the required AWS accounts. Use the same custom domain name for all the gateway endpoints so that a single SCM webhook can be used for all events from all accounts.
- B. Deploy the API Gateway REST API to all the receiver AWS accounts. Create as many SCM webhooks as the number of AWS accounts.
- C. Grant permission to the central AWS account for EventBridge to access the receiver AWS accounts. Add an EventBridge event bus on the receiver AWS accounts as the targets to the existing EventBridge rule.
- D. Convert the API Gateway type from REST API to HTTP API.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)    [Discussion   2](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/9/#)

Question #90Topic 1

A company moved some of its secure files to a private Amazon S3 bucket that has no public access. The company wants to develop a serverless application that gives its employees the ability to log in and securely share the files with other users.  
  
Which AWS feature should the company use to share and access the files securely?

- A. Amazon Cognito user pool
- B. S3 presigned URLs
- C. S3 bucket policy
- D. Amazon Cognito identity pool