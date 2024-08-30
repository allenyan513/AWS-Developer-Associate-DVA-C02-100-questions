Question #61Topic 1

A company is building a web application on AWS. When a customer sends a request, the application will generate reports and then make the reports available to the customer within one hour. Reports should be accessible to the customer for 8 hours. Some reports are larger than 1 MB. Each report is unique to the customer. The application should delete all reports that are older than 2 days.  
Which solution will meet these requirements with the LEAST operational overhead?

- A. Generate the reports and then store the reports as Amazon DynamoDB items that have a specified TTL. Generate a URL that retrieves the reports from DynamoDB. Provide the URL to customers through the web application.
- B. Generate the reports and then store the reports in an Amazon S3 bucket that uses server-side encryption. Attach the reports to an Amazon Simple Notification Service (Amazon SNS) message. Subscribe the customer to email notifications from Amazon SNS.
- C. Generate the reports and then store the reports in an Amazon S3 bucket that uses server-side encryption. Generate a presigned URL that contains an expiration date Provide the URL to customers through the web application. Add S3 Lifecycle configuration rules to the S3 bucket to delete old reports.
- D. Generate the reports and then store the reports in an Amazon RDS database with a date stamp. Generate an URL that retrieves the reports from the RDS database. Provide the URL to customers through the web application. Schedule an hourly AWS Lambda function to delete database records that have expired date stamps.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   8](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #62Topic 1

A company has deployed an application on AWS Elastic Beanstalk. The company has configured the Auto Scaling group that is associated with the Elastic Beanstalk environment to have five Amazon EC2 instances. If the capacity is fewer than four EC2 instances during the deployment, application performance degrades. The company is using the all-at-once deployment policy.  
What is the MOST cost-effective way to solve the deployment issue?

- A. Change the Auto Scaling group to six desired instances.
- B. Change the deployment policy to traffic splitting. Specify an evaluation time of 1 hour.
- C. Change the deployment policy to rolling with additional batch. Specify a batch size of 1.
- D. Change the deployment policy to rolling. Specify a batch size of 2.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   12](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #63Topic 1

A developer is incorporating AWS X-Ray into an application that handles personal identifiable information (PII). The application is hosted on Amazon EC2 instances. The application trace messages include encrypted PII and go to Amazon CloudWatch. The developer needs to ensure that no PII goes outside of the EC2 instances.  
Which solution will meet these requirements?

- A. Manually instrument the X-Ray SDK in the application code.
- B. Use the X-Ray auto-instrumentation agent.
- C. Use Amazon Macie to detect and hide PII. Call the X-Ray API from AWS Lambda.
- D. Use AWS Distro for Open Telemetry.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   21](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #64Topic 1

A developer is migrating some features from a legacy monolithic application to use AWS Lambda functions instead. The application currently stores data in an Amazon Aurora DB cluster that runs in private subnets in a VPC. The AWS account has one VPC deployed. The Lambda functions and the DB cluster are deployed in the same AWS Region in the same AWS account.  
The developer needs to ensure that the Lambda functions can securely access the DB cluster without crossing the public internet.  
Which solution will meet these requirements?

- A. Configure the DB cluster's public access setting to Yes.
- B. Configure an Amazon RDS database proxy for he Lambda functions.
- C. Configure a NAT gateway and a security group for the Lambda functions.
- D. Configure the VPC, subnets, and a security group for the Lambda functions.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   10](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #65Topic 1

A developer is building a new application on AWS. The application uses an AWS Lambda function that retrieves information from an Amazon DynamoDB table. The developer hard coded the DynamoDB table name into the Lambda function code. The table name might change over time. The developer does not want to modify the Lambda code if the table name changes.  
Which solution will meet these requirements MOST efficiently?

- A. Create a Lambda environment variable to store the table name. Use the standard method for the programming language to retrieve the variable.
- B. Store the table name in a file. Store the file in the /tmp folder. Use the SDK for the programming language to retrieve the table name.
- C. Create a file to store the table name. Zip the file and upload the file to the Lambda layer. Use the SDK for the programming language to retrieve the table name.
- D. Create a global variable that is outside the handler in the Lambda function to store the table name.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   6](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #66Topic 1

A company has a critical application on AWS. The application exposes an HTTP API by using Amazon API Gateway. The API is integrated with an AWS Lambda function. The application stores data in an Amazon RDS for MySQL DB instance with 2 virtual CPUs (vCPUs) and 64 GB of RAM.  
  
Customers have reported that some of the API calls return HTTP 500 Internal Server Error responses. Amazon CloudWatch Logs shows errors for “too many connections.” The errors occur during peak usage times that are unpredictable.  
  
The company needs to make the application resilient. The database cannot be down outside of scheduled maintenance hours.  
  
Which solution will meet these requirements?

- A. Decrease the number of vCPUs for the DB instance. Increase the max_connections setting.
- B. Use Amazon RDS Proxy to create a proxy that connects to the DB instance. Update the Lambda function to connect to the proxy.
- C. Add a CloudWatch alarm that changes the DB instance class when the number of connections increases to more than 1,000.
- D. Add an Amazon EventBridge rule that increases the max_connections setting of the DB instance when CPU utilization is above 75%.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   9](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #67Topic 1

A company has installed smart meters in all its customer locations. The smart meters measure power usage at 1-minute intervals and send the usage readings to a remote endpoint for collection. The company needs to create an endpoint that will receive the smart meter readings and store the readings in a database. The company wants to store the location ID and timestamp information.  
  
The company wants to give its customers low-latency access to their current usage and historical usage on demand. The company expects demand to increase significantly. The solution must not impact performance or include downtime while scaling.  
  
Which solution will meet these requirements MOST cost-effectively?

- A. Store the smart meter readings in an Amazon RDS database. Create an index on the location ID and timestamp columns. Use the columns to filter on the customers' data.
- B. Store the smart meter readings in an Amazon DynamoDB table. Create a composite key by using the location ID and timestamp columns. Use the columns to filter on the customers' data.
- C. Store the smart meter readings in Amazon ElastiCache for Redis. Create a SortedSet key by using the location ID and timestamp columns. Use the columns to filter on the customers' data.
- D. Store the smart meter readings in Amazon S3. Partition the data by using the location ID and timestamp columns. Use Amazon Athena to filter on the customers' data.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   10](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #68Topic 1

A company is building a serverless application that uses AWS Lambda functions. The company needs to create a set of test events to test Lambda functions in a development environment. The test events will be created once and then will be used by all the developers in an IAM developer group. The test events must be editable by any of the IAM users in the IAM developer group.  
  
Which solution will meet these requirements?

- A. Create and store the test events in Amazon S3 as JSON objects. Allow S3 bucket access to all IAM users.
- B. Create the test events. Configure the event sharing settings to make the test events shareable.
- C. Create and store the test events in Amazon DynamoDB. Allow access to DynamoDB by using IAM roles.
- D. Create the test events. Configure the event sharing settings to make the test events private.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   18](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #69Topic 1

A developer is configuring an application's deployment environment in AWS CodePipeline. The application code is stored in a GitHub repository. The developer wants to ensure that the repository package's unit tests run in the new deployment environment. The developer has already set the pipeline's source provider to GitHub and has specified the repository and branch to use in the deployment.  
  
Which combination of steps should the developer take next to meet these requirements with the LEAST overhead? (Choose two.)

- A. Create an AWS CodeCommit project. Add the repository package's build and test commands to the project's buildspec.
- B. Create an AWS CodeBuild project. Add the repository package's build and test commands to the project's buildspec.
- C. Create an AWS CodeDeploy project. Add the repository package's build and test commands to the project's buildspec.
- D. Add an action to the source stage. Specify the newly created project as the action provider. Specify the build artifact as the action's input artifact.
- E. Add a new stage to the pipeline after the source stage. Add an action to the new stage. Specify the newly created project as the action provider. Specify the source artifact as the action's input artifact.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)    [Discussion   9](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/7/#)

Question #70Topic 1

An engineer created an A/B test of a new feature on an Amazon CloudWatch Evidently project. The engineer configured two variations of the feature (Variation A and Variation B) for the test. The engineer wants to work exclusively with Variation A. The engineer needs to make updates so that Variation A is the only variation that appears when the engineer hits the application's endpoint.  
  
Which solution will meet this requirement?

- A. Add an override to the feature. Set the identifier of the override to the engineer's user ID. Set the variation to Variation A.
- B. Add an override to the feature. Set the identifier of the override to Variation A. Set the variation to 100%.
- C. Add an experiment to the project. Set the identifier of the experiment to Variation B. Set the variation to 0%.
- D. Add an experiment to the project. Set the identifier of the experiment to the AWS account's account ISet the variation to Variation A.