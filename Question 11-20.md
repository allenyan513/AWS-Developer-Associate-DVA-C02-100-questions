## Question 11

A company is migrating legacy internal applications to AWS. Leadership wants to rewrite the internal employee directory to use native AWS services. A developer needs to create a solution for storing employee contact details and high-resolution photos for use with the new application.  
Which solution will enable the search and retrieval of each employee's individual details and high-resolution photos using AWS APIs?

- A. Encode each employee's contact information and photos using Base64. Store the information in an Amazon DynamoDB table using a sort key.
- B. Store each employee's contact information in an Amazon DynamoDB table along with the object keys for the photos stored in Amazon S3.
- C. Use Amazon Cognito user pools to implement the employee directory in a fully managed software-as-a-service (SaaS) method.
- D. Store employee contact information in an Amazon RDS DB instance with the photos stored in Amazon Elastic File System (Amazon EFS).

**Answer: B. Store each employee's contact information in an Amazon DynamoDB table along with the object keys for the photos stored in Amazon S3.**

### Explanation:

- **Amazon DynamoDB** is a fully managed NoSQL database service that is well-suited for storing and retrieving structured data such as employee contact details. DynamoDB provides fast and flexible querying capabilities, which makes it an ideal choice for an employee directory where you need to search and retrieve individual employee details quickly.
    
- **Amazon S3** (Simple Storage Service) is designed for storing and retrieving large amounts of unstructured data, such as high-resolution photos. By storing photos in S3, you can take advantage of its scalable storage, durability, and availability. Additionally, you can use the object keys in S3 as references within DynamoDB, ensuring that each employee's contact information is efficiently linked to their respective photo.
    
- **Why not the other options?**
    
    - **Option A** (Encoding and storing in DynamoDB): While DynamoDB can store Base64-encoded data, this approach is not efficient for storing large objects like high-resolution photos. DynamoDB is optimized for small, quick reads and writes rather than large binary objects.
    - **Option C** (Amazon Cognito): Amazon Cognito is primarily used for managing user authentication and authorization, not for storing and retrieving arbitrary employee data and photos.
    - **Option D** (RDS and EFS): Amazon RDS is a relational database service, and Amazon EFS is a file storage service for use with Amazon EC2. This option would work but is less optimal compared to DynamoDB and S3. DynamoDB with S3 provides a more scalable, cost-effective, and purpose-built solution for this use case.

## Question 12

A developer is creating an application that will give users the ability to store photos from their cellphones in the cloud. The application needs to support tens of thousands of users. The application uses an Amazon API Gateway REST API that is integrated with AWS Lambda functions to process the photos. The application stores details about the photos in Amazon DynamoDB.  
Users need to create an account to access the application. In the application, users must be able to upload photos and retrieve previously uploaded photos. The photos will range in size from 300 KB to 5 MB.  
Which solution will meet these requirements with the LEAST operational overhead?

- A. Use Amazon Cognito user pools to manage user accounts. Create an Amazon Cognito user pool authorizer in API Gateway to control access to the API. Use the Lambda function to store the photos and details in the DynamoDB table. Retrieve previously uploaded photos directly from the DynamoDB table.
- B. Use Amazon Cognito user pools to manage user accounts. Create an Amazon Cognito user pool authorizer in API Gateway to control access to the API. Use the Lambda function to store the photos in Amazon S3. Store the object's S3 key as part of the photo details in the DynamoDB table. Retrieve previously uploaded photos by querying DynamoDB for the S3 key.
- C. Create an IAM user for each user of the application during the sign-up process. Use IAM authentication to access the API Gateway API. Use the Lambda function to store the photos in Amazon S3. Store the object's S3 key as part of the photo details in the DynamoDB table. Retrieve previously uploaded photos by querying DynamoDB for the S3 key.
- D. Create a users table in DynamoDB. Use the table to manage user accounts. Create a Lambda authorizer that validates user credentials against the users table. Integrate the Lambda authorizer with API Gateway to control access to the API. Use the Lambda function to store the photos in Amazon S3. Store the object's S3 key as par of the photo details in the DynamoDB table. Retrieve previously uploaded photos by querying DynamoDB for the S3 key.

B

## Question #13

A company receives food orders from multiple partners. The company has a microservices application that uses Amazon API Gateway APIs with AWS Lambda integration. Each partner sends orders by calling a customized API that is exposed through API Gateway. The API call invokes a shared Lambda function to process the orders.  
Partners need to be notified after the Lambda function processes the orders. Each partner must receive updates for only the partner's own orders. The company wants to add new partners in the future with the fewest code changes possible.  
Which solution will meet these requirements in the MOST scalable way?

- A. Create a different Amazon Simple Notification Service (Amazon SNS) topic for each partner. Configure the Lambda function to publish messages for each partner to the partner's SNS topic.
- B. Create a different Lambda function for each partner. Configure the Lambda function to notify each partner's service endpoint directly.
- C. Create an Amazon Simple Notification Service (Amazon SNS) topic. Configure the Lambda function to publish messages with specific attributes to the SNS topic. Subscribe each partner to the SNS topic. Apply the appropriate filter policy to the topic subscriptions.
- D. Create one Amazon Simple Notification Service (Amazon SNS) topic. Subscribe all partners to the SNS topic.

C. with specific attributes to the SNS topic
**Option C:** Create an Amazon Simple Notification Service (SNS) topic. Configure the Lambda function to publish messages with specific attributes (such as partner ID) to the SNS topic. Subscribe each partner to the SNS topic. Apply the appropriate filter policy to the topic subscriptions.

- **Scalability:** This approach allows you to easily add new partners by creating new subscriptions with specific filter policies without modifying the existing Lambda function or SNS topic. The filter policy ensures that each partner receives only the messages relevant to their own orders.
- **Minimal Code Changes:** When adding a new partner, you only need to create a new subscription with the appropriate filter policy, which requires minimal changes compared to other options.


## Question #14

A financial company must store original customer records for 10 years for legal reasons. A complete record contains personally identifiable information (PII). According to local regulations, PII is available to only certain people in the company and must not be shared with third parties. The company needs to make the records available to third-party organizations for statistical analysis without sharing the PII.  
A developer wants to store the original immutable record in Amazon S3. Depending on who accesses the S3 document, the document should be returned as is or with all the PII removed. The developer has written an AWS Lambda function to remove the PII from the document. The function is named removePii.  
What should the developer do so that the company can meet the PII requirements while maintaining only one copy of the document?

- A. Set up an S3 event notification that invokes the removePii function when an S3 GET request is made. Call Amazon S3 by using a GET request to access the object without PII.
- B. Set up an S3 event notification that invokes the removePii function when an S3 PUT request is made. Call Amazon S3 by using a PUT request to access the object without PII.
- C. Create an S3 Object Lambda access point from the S3 console. Select the removePii function. Use S3 Access Points to access the object without PII.
- D. Create an S3 access point from the S3 console. Use the access point name to call the GetObjectLegalHold S3 API function. Pass in the removePii function name to access the object without PII.



**Option C:** Create an S3 Object Lambda access point from the S3 console. Select the `removePii` function. Use S3 Access Points to access the object without PII.

- **S3 Object Lambda:** This feature allows you to transform data as it is retrieved from Amazon S3 by invoking a Lambda function. In this case, the `removePii` function can be used to remove PII from the document dynamically. When a user with permission to see PII accesses the document, they can retrieve the original version. When a third-party organization accesses the document, the S3 Object Lambda access point will automatically invoke the `removePii` function to remove the PII before returning the document. 
- **Single Copy of the Document:** With this approach, only one copy of the document is stored in S3, which simplifies data management and ensures compliance with the requirement to maintain original records for 10 years.
- **Controlled Access:** By configuring different S3 Access Points and permissions, the company can control who can access the original document and who can access the document with PII removed.

## Question #15

A developer is deploying an AWS Lambda function The developer wants the ability to return to older versions of the function quickly and seamlessly.  
How can the developer achieve this goal with the LEAST operational overhead?

- A. Use AWS OpsWorks to perform blue/green deployments.
- B. Use a function alias with different versions.
- C. Maintain deployment packages for older versions in Amazon S3.
- D. Use AWS CodePipeline for deployments and rollbacks.

B
[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)    [Discussion   8](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)

## Question #16

A developer has written an AWS Lambda function. The function is CPU-bound. The developer wants to ensure that the function returns responses quickly.  
How can the developer improve the function's performance?

- A. Increase the function's CPU core count.
- B. Increase the function's memory.
- C. Increase the function's reserved concurrency.
- D. Increase the function's timeout.

B

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)    [Discussion   15](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)

## Question #17

For a deployment using AWS Code Deploy, what is the run order of the hooks for in-place deployments?

- A. BeforeInstall -> ApplicationStop -> ApplicationStart -> AfterInstall
- B. ApplicationStop -> BeforeInstall -> AfterInstall -> ApplicationStart
- C. BeforeInstall -> ApplicationStop -> ValidateService -> ApplicationStart
- D. ApplicationStop -> BeforeInstall -> ValidateService -> ApplicationStart

B

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)    [Discussion   28](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)

## Question #18

A company is building a serverless application on AWS. The application uses an AWS Lambda function to process customer orders 24 hours a day, 7 days a week. The Lambda function calls an external vendor's HTTP API to process payments.  
During load tests, a developer discovers that the external vendor payment processing API occasionally times out and returns errors. The company expects that some payment processing API calls will return errors.  
The company wants the support team to receive notifications in near real time only when the payment processing external API error rate exceed 5% of the total number of transactions in an hour. Developers need to use an existing Amazon Simple Notification Service (Amazon SNS) topic that is configured to notify the support team.  
Which solution will meet these requirements?

- A. Write the results of payment processing API calls to Amazon CloudWatch. Use Amazon CloudWatch Logs Insights to query the CloudWatch logs. Schedule the Lambda function to check the CloudWatch logs and notify the existing SNS topic.
- B. Publish custom metrics to CloudWatch that record the failures of the external payment processing API calls. Configure a CloudWatch alarm to notify the existing SNS topic when error rate exceeds the specified rate.
- C. Publish the results of the external payment processing API calls to a new Amazon SNS topic. Subscribe the support team members to the new SNS topic.
- D. Write the results of the external payment processing API calls to Amazon S3. Schedule an Amazon Athena query to run at regular intervals. Configure Athena to send notifications to the existing SNS topic when the error rate exceeds the specified rate.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)    [Discussion   8](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)

## Question #19

A company is offering APIs as a service over the internet to provide unauthenticated read access to statistical information that is updated daily. The company uses Amazon API Gateway and AWS Lambda to develop the APIs. The service has become popular, and the company wants to enhance the responsiveness of the APIs.  
Which action can help the company achieve this goal?

- A. Enable API caching in API Gateway.
- B. Configure API Gateway to use an interface VPC endpoint.
- C. Enable cross-origin resource sharing (CORS) for the APIs.
- D. Configure usage plans and API keys in API Gateway.

[Reveal Solution](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)    [Discussion   12](https://www.examtopics.com/exams/amazon/aws-certified-developer-associate-dva-c02/view/2/#)

## Question #20

A developer wants to store information about movies. Each movie has a title, release year, and genre. The movie information also can include additional properties about the cast and production crew. This additional information is inconsistent across movies. For example, one movie might have an assistant director, and another movie might have an animal trainer.  
The developer needs to implement a solution to support the following use cases:  
For a given title and release year, get all details about the movie that has that title and release year.  
For a given title, get all details about all movies that have that title.  
For a given genre, get all details about all movies in that genre.  
Which data store configuration will meet these requirements?

- A. Create an Amazon DynamoDB table. Configure the table with a primary key that consists of the title as the partition key and the release year as the sort key. Create a global secondary index that uses the genre as the partition key and the title as the sort key.
- B. Create an Amazon DynamoDB table. Configure the table with a primary key that consists of the genre as the partition key and the release year as the sort key. Create a global secondary index that uses the title as the partition key.
- C. On an Amazon RDS DB instance, create a table that contains columns for title, release year, and genre. Configure the title as the primary key.
- D. On an Amazon RDS DB instance, create a table where the primary key is the title and all other data is encoded into JSON format as one additional column.