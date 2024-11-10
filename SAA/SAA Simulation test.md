# 1
A company wants to automate the process of creating multiple AWS resources for their production web-application environment. Which AWS service is capable of automating their infrastructure as code?

AWS CodeBuild

AWS Elastic Beanstalk

AWS Automate

AWS CloudFormation

D

---

# 2
A company security policy requires that all EBS Volumes are encrypted-at-rest. Which AWS service would help meet this requirement?

Server-Side Encryption AES-256

AWS Certificate Manager

Amazon GuardDuty

AWS KMS
D

---

# 3
An application has multiple EC2 instances within an Auto Scaling Group (ASG). The ASG also has a simple scaling policy to meet the demand for fluctuating traffic. The application is scaling up and down repeatedly within the timeframe of an hour. What configuration changes could be made to reduce the cost and the frequency of scaling?

(Choose 2)
Reduce the Desired Capacity

Reduce the Max Capacity

Increase the Cooldown timer

Increase the alarm period that triggers the scale down policy

Add Scheduled Scaling Actions

CD

---

# 4
A Solutions Architect is developing several important long-running applications hosted on Docker.
How should the Solutions Architect design a solution on AWS to meet the scalability and orchestration needs?

Use [[AWS OpsWorks]] to launch containers in new Amazon EC2 instances

Use Spot Instances to orchestrate and scale containers on existing Amazon EC2 instances.

Use Auto Scaling groups to launch containers on existing Amazon EC2 instances

Use Amazon ECS and Service Auto Scaling

D

---

# 5 
A web application running on EC2 instances managed by Auto Scaling Group and behind an Application Load Balancer generates thousands of PDFs weekly, which are stored in S3. These PDFs need to be accompanied by additional information in the form of metadata, which is 20 KB in size. This additional data needs to be stored and displayed in a flat list on the web application. Which solutions would be the most performant for displaying this list of metadata?

Store the metadata in RDS

Metadata can be applied directly to S3 Objects

Store the metadata in the root EBS volume

Store the metadata in a DynamoDB table

D

---

# 6
In a VPC network, access control lists (ACLs) act as a firewall for associated subnets, controlling both inbound and outbound traffic at the `___` level.

API Gateway

Private

EC2 instance

Subnet

D

[[Network ACL]]

---

# 7
An AWS Lamba function needs to access S3 in order to process photos into thumbnails. How can you securely pass credentials to the AWS Lambda?

Place the Access Key and Secret into Lambda function. It is not possible to assign roles or environment variables to AWS Lambda functions. So you must hard code the credentials

Pass the Access Key and Secret into environment variables within the AWS Lambda console. This will keep the credentials out of the code and secure.

Use AWS Secrets Manager to store the Access Key and Secret

Assign an IAM role to the AWS Lambda with permission to S3

D

> @ C or D ?

---

# 8
www.exampro.com is a popular photo and video hosting service with millions of users.

Which of the following is the best solution for storing large data objects while lowering costs, scaling to meet demand, and speeding up innovation?

Amazon S3 Glacier

Amazon Elastic File System

AWS Redshift

Amazon S3 Standard
D

---
# 9
An application is backed by DynamoDB. The DynamoDB table has a provisioned throughput of 100 reads and writes per second. During peak hours the number of writes can reach 500 per second and as a result, the excess writes are being dropped. What cost-effective solution could be architected to handle the non-uniform increase in writes?

Turn on Auto Scaling write for write capacity

Use Kinesis Data Streams as a buffer.

Change Read/write capacity mode to On-demand

Use SQS as a buffer.

D

- SQS first 1 million Amazon SQS requests per month are free and $0.40 for 1 million requests thereafter. SQS would result in zero to no charges.
- SQS will cause delay but in this question we don't need to concern

---

# 10
A cloud engineer needs to use CloudFront to distribute the content they need to create a distribution. They are required to specify the configuration settings.
Which of the following configuration settings should be specified?

You specify the number of objects you can serve per distribution.

You configure the environment variables.

You specify if you want everyone to have access to the files or a select number of users.

You specify your origin Amazon S3 bucket or HTTP server.

D

---

# 11
A company has an application running in us-east-1a. In the case of Availability Zone failure, the company needs to recover the volume and launch another instance in another Availability Zone such as us-east-1b. The company is not concerned with downtime and trying to save costs by running in a single AZ. How can the company ensure that it can recover from such a failure?

Backup the contents of the EBS volumes to S3 with Sync command
> You can do this, however ensuring all of the volume is copied could be error-prone. Since when you create an EBS Snapshot it is already going to S3 and Snapshot does a better job of backing up to S3 you're better off taking a snapshot. If you just needed to copy some core files then maybe this method would be desirable.

Continuously create Snapshots and copy Snapshots to another Region
> This company only needs to restore within the same AZ. If the whole region then this would allow them to recover, so ideally yes you'd want to store your Snapshot in another region but for the sake of the scenario, it's not necessary.

Continuously create Snapshots and copy Snapshots to another AZ
> When you create a snapshot it's stored on S3. S3 already will replicate this across at least 3 AZs. There is no option to change AZs for a Snapshot on a copy.

- Continuously create Snapshots
> When you create a snapshot it stored in S3 which will replicate across at least 3 AZs.

Use EFS since it is already highly available
> EFS is already highly available. This company wants to save money and EFS is going to cost more than EBS. EFS is suited when you have multiple EC2 instances that have the need to share a single mounted volume


---

# 12

As a Solution Architect, you need to build a CloudFormation template that will provision a highly available architecture. After the stack has been created you need to a convenient way to return the DNS hostname of the load balancer. Which template section would provide the DNS hostname after stack creation?

Mappings
> A lookup table. Maps keys to values so you change your values to something else

Parameters
> Values to pass to your template at runtime

Resources
> A resource you want to create eg. IAM Role, EC2 Instance, Lambda, RDS

Outputs
> Values that returned eg. an ip-address of new server created.

Variables
> This is not a template section

---

# 13
A company has an application running on EC2 instance which needs to store multiple documents which are uploaded via users. User's frequently uploads changes to their documents but with the same name. The company wants to allows users to roll back to previous documents. Which storage solution would best meet their needs?

EFS

EBS

AWS Elastic Beanstalk

S3

D

---

# 14
A company has a requirement that does not allow them to use DocumentDB and so they must provision an EC2 instance with MongoDB. Their current requirements are they need at most 10,000 IOPS Which storage solution would meet their needs?

EBS Provisioned IOPS SSD
> Large databases such as MongoDB require a higher amount of IOPS and Provisioned IOPS SSD is recommended for large databases. Provisioned IOPS SSD is recommended when going above16,000 IOPS which is yet to be a requirement reached by this company

EBS Throughput Optimized ==HDD==
> HDD have very low IOPS with Throughput Optimized being at 500 MiB

EBS Cold HDD
HDD have very low IOPS with Throughput Optimized being at 250 MiB

EBS General Purpose SSD
Large databases such as MongoDB requirer a higher amount of IOPS. General Purpose has a maximum of 16,000 IOPS. When that limit is reached then they should use Provisioned IOPS SSD but for now, they can use General Purpose.

---

# 15
A developer is building an automated transcription service in which "Amazon EC2 worker" instances process an audio file and convert it to a text file. They need to store both of these files in the same secure storage until the text file is retrieved, but they don't know how much space they'll need.
Which of the following storage options is both cost-efficient and scalable?

Multiple instance stores

A single Amazon Glacier Vault

Multiple Amazon EBS volume with snapshots

A single Amazon S3 bucket

D

---

# 16 
A Solution Architect needs to investigate which database solution would be the best fit for a new web application. The data being stored must remain highly available by default. Access to this data should have a guarantee of reads at any scale and the data being stored JSON like data. Which database solution would meet their needs?

RDS

Amazon Redshift

DocumentDB

- **DynamoDB**

Aurora



---

# 17

Which of the following should be referred to if you want to map Amazon Elastic Block Store to an Amazon EC2 instance for AWS CloudFormation resources?

Reference the physical IDs of the instance

The logical IDs of the instance

Reference the physical IDs of both the block stores and the instance

- Reference the logical IDs of both the block stores and the instance

The logical ID must be alphanumeric (A-Za-z0-9) and unique within the template. Use the logical name to reference the resource ==in other parts of the template==. For example, if you want to **map an Amazon Elastic Block Store volume to an Amazon EC2 instance, you reference the logical IDs to associate the block stores with the instance**.

You must create the JSON with all of the essential attributes as part of the CloudFormation template. In the resource section, you must refer to the logical IDs of both the block stores and the instances and configure them according to your needs.

---

# 18

A company wants to back up their on-premise storage volumes to AWS. What solution would meet their needs?

Use S3

Connect your on-premise with AWS VPN. Create EBS Snapshots

Connect your on-premise with Direct Connect. Create [[EBS]] Snapshots
> You cannot use EBS Snapshots on anything other than EBS Volumes. Your local storage volumes will not be EBS Volumes

- Use Storage Volume Gateway
> Storage Gateway Volume gateway is for backing up your off-cloud storage volumes on S3.

Connect your on-premise with AWS VPN. Use EFS
> EFS can only be mounted to EC2 instances within the same VPC. Your on-premise network is the not the same network so you won't be able to mount it.




---

# 19
A Solution Architect is designing an application with a relational database that runs on an EC2 instance. This database will be used infrequently once or twice a day. The database is also 100 GB in size. Which [[EBS]] volume type is the most cost-effective option?

EBS Throughput Optimized HDD

EBS Provisioned IOPS SSD

EBS General Purpose SSD

- EBS Cold HDD

---

# 20
A Solution Architect needs to choose a database which can perform joins between multiple tables and utilize an ==open-source service==. Which database solution would be best suited for this use case?

Aurora

DynamoDB
> DynamoDB can not perform joins and is not open-source.

Redshift

- RDS
RDS has multiple relational engines. Postgres, MySQL and MariaDB are all open-source. A relational database can join multiple tables together.

---

# 21
A company has a two-tier application which has a web application layer utilizing a single EC2 instance and a database layer utilizing an RDS MySQL instance. From a security standpoint which subnets should each layer be launched within?

private subnet for the web application layer
private subnet for the database layer

public subnet for the web application layer
public subnet for the database layer

public subnet for the database layer
private subnet for the web application layer

- public subnet for the web application layer
- private subnet for the database layer

---

# 22
A company has an application running on an EC2 instance behind an [[ELB - Elastic Load Balancer]]. Whenever a user signs up the product manager wants to receive an email. Which solution would meet their needs?

Use the AWS SDK to trigger a Lambda. Have that Lambda publish an event to an SNS topic. Have a subscription to the SNS topic to receive that email

- Use the AWS SDK to push a message onto an SQS queue. Have SES pull the queue to then send the email

Use the AWS SDK to trigger a Lambda. Have that Lambda push a message onto an SQS queue. Have SES pull the queue to then send the email

Use the AWS SDK to publish the event to an SNS topic. Have a subscription to the SNS topic to receive that email

> AWS SDK can be used to push a message on to an SQS queue SES cannot pull directly from SQS, It would need a Lambda or an EC2 instance to do so using the AWS SDK
> Even if you could push to SES you are better off using SNS to send the email. SES is generally for emails which are for consumer sending emails from a custom domain and a pretty HTML email. Since this is being sent to the product manager and it's an internal email SNS is the practical solution.
> 
> AWS SDK can be used to publish an event to an SNS Topic. A Subscription can be made to an SNS topic so the product manager can receive an email.
> This is the ideal solution over SES because ==SNS is a plain text email== and since this is internal notifications we don't care on the aesthetic of the email. Additionally, we would also be able to easily add an SNS text message so we have more future flexibility of notification methods.

---

# 23
A company has an on-premise MySQL database. The database in question is 15TB in size and is likely double within two calendar quarters. Due to the size of the database replicas are required. Replication lag should be in the milliseconds to guarantee excellent performance. Which RDS engine will be meet these performance requirements?

Microsoft SQL Server

MySQL

Maria DB (和MySQL没有太大区别)

- Amazon Aurora

---

# 24
A Solution Architect is tasked with designing a web application running behind an Application Load Balancer (ALB). The web application needs to access objects from S3 without exposing said objects from S3 directly to the Internet. Which solution would meet these requirements?

Apply an ACM SSL Certificate to the Application Load Balancer

Use Server-Side Encryption on the S3 Bucket

Turn off the Internet Gateway to the S3 Bucket

- Use a VPC Endpoint

[[S3#Gateway endpoints]]

---

# 25
Which of the following payment options are associated with Reserved Instances? (Choose 3)

(Choose 3)
Annual Upfront

- All Upfront

- No Upfront

- Partial Upfront

Monthly Upfront

Amazon EC2 Reserved Instances allow you to reserve Amazon EC2 computing capacity for 1 or 3 years, in exchange for a significant discount (up to 75%) compared to On-Demand instance pricing.

AWS Reserved Instances are available in three payment options:
- **All Upfront**: Pay the full amount at the start of the term  
- **Partial Upfront**: Make a small upfront payment and then pay a discounted hourly rate for the remainder of the term  
- **No Upfront**: Pay no upfront amount and pay a discounted hourly rate for the remainder of the term


---

# 26
An application running on an EC2 instance managed by an Auto Scaling Group and which backed by an RDS Postgres database is gaining in popularity the database cannot keep up with the number of queries being request. What solution would improve the performance of this architecture?

Application Load Balancer in front of the web-application

CloudFront in front of the web-application

ElastiCache in front of the web application

- ElastiCache in front of the database

---

# 27
A web application needs to frequently read per second data from the S3 bucket using Standard Access. How can the S3 bucket be configured to maximize its read performance?

Turn on S3 Accelerated Transfer 
> Incorrect. S3 Transfer Acceleration speeds up data transfers by routing them through Amazon's global edge locations, improving upload and download speeds over long distances. However, it primarily benefits scenarios where data is being transferred to or from the bucket across regions. It does not significantly impact performance for frequent reads within the same region, which is the case for this scenario, making it incorrect.

Use Intelligent-Tiering Storage

- Prefix naming with hashed characters to optimize performance for frequent data retrievals
> Correct. S3 optimizes performance by distributing object data across multiple partitions based on the object's key prefix. If objects have similar prefixes (e.g., all start with "2023/07/"), they are likely to end up in the same partition, which can create a bottleneck. By using hashed prefixes, you spread the objects across different partitions, reducing the risk of hot spots and improving performance for high-frequency read operations.

No changes are necessary

Prefix naming with Unix timestamp to optimize performance for frequent data retrievals
> Incorrect. While this option would create unique prefixes, using a Unix timestamp as a prefix could still result in performance bottlenecks. This is because the timestamps would likely be sequential, potentially leading to similar prefix patterns and creating hot spots. Hashing the prefix distributes the requests more evenly across partitions, which is why timestamp-based prefixes are not ideal for this scenario.



---

# 28
A company has multiple AWS accounts with resources operating in multiple regions. The company wants to have an audit trail of which services have been accessed via the AWS API. How can CloudTrail be configured to meet these requirements?

Logging across accounts is not possible. Create a trail in each AWS account with logging across all regions. Delivery the logs to a bucket within the master account to centralize all the logs.

Do not create a trail in the master account since this would not be secure. Use another account other than master and create a single trail. Ensure to turn on logging across all AWS accounts within an Organization and to log all regions.

Logging must be turned on per region and AWS account. Turn on AWS Config in each AWS account which will automatically create a trail for each region.

- Create a single trail in the master account. Ensure to turn on logging across all AWS accounts within an Organization and to log all regions.

#useful 

---

# 29
A company has thousands of applications which needs to deliver JSON logs to S3 so they can be analyzed in Athena. These files need to be archived, encrypted as well as converted to ==parquet format.== ( @ Apache Parquet is an open source, column-oriented data file format designed for efficient data storage and retrieval ) Logs are being sent every minute and the company wants to be able to analyze them as soon as possible. What solution can be used to prepare the log files?

Use CloudWatch Logs
CloudWatch can accept JSON logs if the CloudWatch Agent is installed and configured on the EC2 instances. Since these requirements wants to use Athena the destination needs to be S3 and we will have no easy means of moving logs from CloudWatch Logs to S3.

Use Kinesis Data Streams
Kinesis Data Streams could be accomplish the same a Kinesis Firehose but you'd ==have to write your own consumer==. Data Streams can persist data but we have no need to keep these logs around within the stream.

Use SQS
SQS Standard can handle the number of messages being delivered but it would require building a fleet of instances behind an ELB which would process the logs. SQS would be too cumbersome for this use case.

Use Kinesis Firehose
Kinesis Firehose has the ability to archive, encrypt as well as transform JSON to parquet. Kinesis Firehose allows you to choose from a limited option of consumers. One being S3 which is where we need these files to be.

AWS Glue
AWS Glue is an ELT and it could be used to define the Athena table by crawling the JSON logs to determine the table schema. You can perform operations on the data. Using Glue you can also convert JSON to parquet.
==Due to the frequency of the files needing to be processed Kinesis is a better choice where Glue can be more suited for large batches periodically.==

---

# 30
What are two services that you may use to build rich and flexible payment apps for your own business? (Choose 2)

(Choose 2)
PayPal Payment service

- [[Amazon Flexible Payment Service]]

Azure Payment service

- [[Amazon DevPay]]



---

# 31
A company needs to ensure its production application remains highly available and fault-tolerant. The application needs 6 instances running at any given time to stay operational and cannot afford downtime. The application operations in us-east-2 (Ohio) which only has 3 Availability Zones. How many EC2 instances do they need within each AZ to ensure the resiliency of their application in the case of single AZ failure?

> 三个方式是独立的方案 他妈的

(Choose 3)
Create an Auto Scaling Group configured to run in all AZs. Set Min Capacity Setting to 6
```
An ASG will automatically launch instances evenly across all AZs.
2 us-east-2a
2 us-east-2b
2 us-east-2c
The failure of a single AZ would result in 4 instances remaining. The ASG would launch more instances in the two remaining AZs but downtime would occur because for some time we would short 2 instances to remain operational which is not acceptable for this scenario.
```

- Create an Auto Scaling Group configured to run in all AZs. Set Min Capacity Setting to 9


3 Instances in us-east-2a, 3 in us-east-2b

- 6 Instances in us-east-2a, and 6 in us-east-2b.

3 Instances in us-east-2a, 3 in us-east-2b, and 3 in us-east-2c

2 Instances in us-east-2a, 2 in us-east-2b, and 2 in us-east-2c

---

# 32
A company needs 8 m5.large EC2 instanced backed by Application Load Balancer running in us-east-1 region and can tolerate the loss of a single Availability Zone. What distribution of instances across Availability Zones will result in the lowest cost possible?

8 instances in Availability Zones a through b
> This option concentrates all 8 instances in just 2 AZs (a and b). While this might seem cost-effective due to the use of fewer AZs, it poses a risk. If one AZ fails, it results in the loss of half the instances, which could significantly impact the application's performance or availability. This setup does not adequately meet the resilience requirement.

3 instances in Availability Zones a through d
> Placing 3 instances in each of 4 AZs (a-d) also offers high resilience. However, similar to the first option, this setup uses more AZs than necessary, potentially increasing costs without significant additional benefits. It's more resilient than needed for the requirement of tolerating the loss of one AZ.


4 EC2 instances in Availability Zones a through c
> Allocating 4 instances in each of 3 AZs (a-c) strikes a balance between cost and resilience. This setup provides sufficient redundancy to handle the failure of one AZ without incurring excessive costs associated with using more AZs than necessary. It meets the requirement of tolerating the loss of one AZ effectively and is likely the most cost-efficient option among those provided.

- 2 instances in Availability Zones a through e

> Distributing 2 instances across 5 AZs (a-e) increases resilience but may not be cost-effective. More AZs can lead to higher inter-zone data transfer costs. While this setup provides high fault tolerance, it exceeds the requirement of tolerating the loss of just one AZ, leading to unnecessary additional costs.

> 找到AZ数量和EC2数量的平衡点

---

# 33
Which of the following are caching solutions on AWS?
(Choose 3)

 AWS Cachezilla
 > not exist

EC2
> EC2 instances could be used to setup up open-source caching instance with an instance Type with high amount of memory. EC2 any kind of computing so you can do anything you like as long as you're willing to maintain the instances yourself.

- ElastiCache

- CloudFront

CacheDeploy
> not exist


---
# 34
A web application which consists of a single EC2 instance that has an Elastic IP (EIP) is accessed by employees from remote locations. How can the IP addreses from the inbound traffic be audited to determine if they are company approved IP addresses?

[[CloudWatch]] Logs

EC2 Metadata
> EC2 Metadata is a special HTTP URL which you can query within your EC2 environment to get metadata information about the EC2 host such as the IP address of the current instance. It would not provide you with IP addresses of inbound traffic.

- CloudTrail
> AWS CloudTrail monitors the interactions between AWS Services and API calls. CloudTrail logs do contain the source IP for an event. Since the remote employees are accessing the web-application through a web-browser instead of the CLI or SDK, CloudTrail is not going to log these network requests.


 VPC Flow Logs
 > Turning on VPC Flow Logs within your VPC will ==capture inbound traffic from the internet into your VPC.== Within these logs contains the IP address of the source of the incoming request. VPC Flow Logs can be stored in CloudWatch Logs or S3 where you can analyze them further.
 


---

# 35
A serverless application is composed of multiple AWS Lambda functions that are invoked by API Gateway endpoints. A user needs to investigate the failure of specific AWS Lambdas. Which AWS service will give them visibility into the cause of the failures?

(Choose 2)
[[Inspector]]

[[X-Ray]]
> AWS X-Ray helps developers analyze and debug production, distributed applications, such as those built using a microservices architecture. X-Ray is useful for finding where a problem has occurred when a request is passed along multiple Lambdas but not necessarily what the problem has occurred.
> In order to determine what, logging must be inserted into the code of the Lambda which will then be tracked via CloudWatch Logs.

[[CloudTrail]]
> CloudTrail is for governance and auditing about who has accessed what services. If you need to know who to blame then CloudTrail is a good fit to determine the culprit. CloudTrail will not provide clear insight into the failure of an instance.

- [[CloudWatch Logs]]
> Within the code for your Lambda functions, you can insert logging which will then be streamed to CloudWatch logs so you can determine what has occurred with your Lamda function.

---

# 36
A web application has around 100 background ==job== requests per second. Another EC2 instance is set up to process the jobs. How can these applications be ==integrated together== to meet the demand of requests ==without batching==?
> job => order matters

AWS SNS
> Incorrect. AWS SNS is designed for a pub/sub (publish-subscribe) model, where messages are sent to multiple subscribers. This is more suitable for broadcasting messages to a number of endpoints such as email, SMS, or other AWS services like Lambda or HTTP endpoints. SNS is not ideal for direct job processing, as it doesn’t have built-in support for queueing jobs or handling background tasks. Therefore, it wouldn’t be a good fit for handling job requests that need to be processed asynchronously by another EC2 instance. SNS could be used to trigger an SQS queue in certain architectures, but on its own, it is not a solution for background job processing.

AWS SQS FIFO
> FIFO queues are limited in terms of throughput compared to Standard queues, making them less ideal for high-traffic workloads like 100 job requests per second. FIFO queues can process up to 300 messages per second with batching, or up to 3,000 messages per second with ==batching== if you are using message groups. Therefore, while FIFO queues ensure order, their lower throughput could become a bottleneck in your case.

AWS ASG

- AWS SQS Standard

> Correct. AWS SQS Standard Queue is an excellent choice because it is designed to handle high-throughput workloads, making it ideal for situations like yours where a large number of background job requests need to be processed quickly and efficiently. It can handle an almost unlimited number of messages per second. SQS Standard provides at-least-once delivery, which ensures that each job will be processed, though it doesn't guarantee the exact order of messages. This works well for background jobs where order doesn't necessarily matter but speed and scalability are critical. SQS Standard also decouples your application, ensuring that the background job processing can continue regardless of the state of the sender or the receiver.

---

# 37
A software development team must restructure their SaaS solution's application layer so that, regardless of the request volume necessary at any given time, the solution will scale automatically to meet the application's exact needs. The team has made the decision to become serverless.
Which of the following services would be the most appropriate for their needs?

Amazon DynamoDB and AWS Code Deploy

Amazon Cognito and Amazon DynamoDB

Amazon Elastic Beanstalk and an Application Load Balancer

- Amazon API Gateway and AWS Lambda

---

# 38
A web-application running on an EC2 instance generates multiples pdfs which then need to be publically served. Currently, these files reside on the EBS Volume and are served via the web-application. These pdfs are downloading files quite frequently which are slowing down the application, as well as users from other regions of the world, are complaining about slow download speeds. What could be done to address these performance issues?

Store the PDF files as a [[BLOB]] in the database

Cache the PDFs on ElastiCache

Store and Serve the S3 files in an S3 Bucket with Public Access
> Serving the files from S3 would reduce the burden to the web-application but download would still be slow for users who are far from the S3 Bucket region.

- Cache the PDFs on CloudFront

---
# 39

A company needs to store application logs for a security application that monitor their production application. They are planning to encrypt and store these files within S3. They want to ensure that in the event a malicious actor gains access to their AWS account they cannot cover their tracks by simply deleting these logs. How can ensure these logs are not easily deleted?

(Choose 3)
Turn on cross-region replication

Create a Bucket Policy to not allow deletes

- Enable MFA Delete on the bucket.

- Enable Versioning on the bucket

- Enable S3 Object Lock

---

# 40
A Solution Architect is designing a disaster recovery plan for a company's production web-application that is backed by RDS which is also behind an Application Load Balancer and Auto Scaling Group. Their RDS Snapshots are automatically replicated cross-region in case of a regional disaster. The solution must be able to replicate the infrastructure in another region in the case of regional failure. What is the most cost-effective solution?

Create an exact duplicate of the infrastructure in another region with Snapshot restored regularly. There is no cost-effective solution to avoid downtime.

Create a duplicate of the infrastructure in another region. Have the Auto Scaling Group set to a minimum capacity of 0 instances. Turn minimum capacity to production requirements when needed. Restore the RDS Snapshot.

Duplicate infrastructure in Elastic Beanstalk in another region. Restore the RDS Snapshot.

- Create a CloudFormation template defining all the AWS resources. Launch the CloudFormation template in another region when needed. Restore the RDS Snapshot.

---

# 41
Which IAM policy condition key should be used if you want to check whether the request was sent using SSL?

AWS: source IP

AWS: secure SSL

AWS: user requests

AWS: secure transport

To determine HTTP or HTTPS requests in a bucket policy, use a condition that checks for the key "aws:SecureTransport". When this key is true, then request is sent through HTTPS. To comply with the s3-bucket-ssl-requests-only rule, create a bucket policy that explicitly denies access when the request meets the condition "aws:SecureTransport": "false". This policy explicitly denies access to HTTP requests.

---

# 42
An application running on an EC2 instance has a scoreboard. The top ten scores rarely change but have high reads. The scores after the top change more frequently and are not as read as often. It is important that the time to read and write has a guarantee of speed. Which two AWS services would meet these performance requirements?

(Choose 2)
[[Redshift]]

RDS

- [[DynamoDB]]
> DynamoDB can handle both low and high-frequency updates

- [[ElastiCache]]

[[Macie]]

---

# 43
A company has popular web-application behind an Auto Scaling Group that has seasonal traffic. In the summer traffic rapidly grows and each year the number of traffic doubles. The rate at which the traffic grows is not predictable. Summer is approaching and the company needs to implement a solution which will meet the performance demands. What configuration change to Auto Scaling Group will help them meet the demand?

Step scaling

Simple scaling

Schedule Actions

- Target tracking scaling policy
> track request num

---

# 44 
A Solutions Architect needs to design a storage solution to archive rarely accessed financial documents. In the case of an audit, files must be retrieved within 3-5 hours. Which Glacier retrieval option would be the most cost-effective and meet the time requirement?

Expedited retrieval

Express retrieval
> There is no retrieval option called Express.

Bulk retrieval

- Standard retrieval

[[S3#Storage class#Glacier]]

---

# 45
	A company has sensitive documents that they need to hold onto for 7 years in case of a surprise audit, and it's essential they store them in a highly resilient storage solution. The company has chosen to use S3 Glacier due to its low cost and resiliency. However, since an on-site audit can occur at random, documents from S3 Glacier need to be retrieved within minutes. Which retrieval option would meet their needs?

Standard retrieval

Bulk retrieval

Express retrieval

- Expedited retrieval

Accelerated retrieval
> This retrieval method does not exist

[[S3#Storage class#Glacier]]

---

# 46
A company is using DynamoDB as its primary production database. The company's security policy requires that all data be encrypted at rest. How can DynamoDB data be encrypted?
(Choose 2)

Turn on [[DynamoDB]] Accelerated Encryption (DAX) 
>  DAX is a caching service for DynamoDB that improves read performance

Turn on Enhanced VPC Routing

- Use Customer Managed Keys with AWS KMS

- Use the AWS managed Customer Master Key 

Use the IAM Password Policy

---

# 47
A company needs to provide its thousands of remote employees a storage solution to backup various files. Files need to be generally retrieval immediately but are not accessed often. What is the most cost-effective storage option?

EBS Cold HDD

Glacier with Expedited Retrievals

S3 Standard

- S3 Standard-IA

---

# 48
A company has critical and non-critical workloads which have been containerized. Which of the following is the most cost-effective batch processing solution?

ECS with Reserved Instances. Spot Instances are not available on ECS

Fargate with Reserved Instances for critical workloads and Spot Instances for non-critical workloads
> Fargate pricing is based on the vCPU and memory resources consumed. Fargate cannot make use of EC2 Pricing such as Spot or Reserved Instance

AWS Lambda with Reserved Instances for critical workloads and Spot Instances for non-critical workloads
> AWS Lambda pricing is based on the duration the number of requests and the memory utilized. Lambda cannot make use of EC2 Pricing such as Spot or Reserved Instance

ECS with Reserved Instances for critical workloads and Spot Instances for non-critical workloads
> Elastic Container Service (ESC) can utilize both Reserved Instances (RI) and Spot Instances.
> 
> Reserved Instances can save up to 75% compared to On-Demand and is intended for critical workloads which cannot be interrupted
> Spot Instances can save up to 90% compared to On-Demand and is intended for non-critical workloads which can be interrupted
> 
> The Elastic Container service from AWS can be used for container orchestration. 

---

# 49
A company needs to perform long and complex queries petabytes worth of data to generate out Business Intelligence reports. Which service would best need the performance needs?

ElastiCache

Amazon RDS

DynamoDB

- Amazon Redshift

---

# 50
A website for internal company use is hosted on S3 Static Website Hosting and has a CloudFront distribution in front of it to only allow authenticated users to access the website. The S3 website URL endpoint provided by default for AWS is still accessible and users outside the company are able to access the website. How can access be forced only through CloudFront?
(Choose 2)

Turn on Versioning

Block All Public Access 
> this will cause OAI policies cannot be set

- Update Bucket Policy to ensure public access is not granted

- Create an Origin Access Identity

S3 Presigned URLs

---

# 51
A company has a web application and they want to capture real-time clickstream data from user activities for subsequent analysis. Which AWS service is most suitable for collecting and streaming this data in real-time?

Kinesis Data Analytics

Kinesis Firehose

Amazon MFK

- Kinesis Data Streams
[[Kinesis]]

---

# 52
A company has created a CloudTrail log to track API calls to AWS services across all regions within an AWS account and the logs are to be delivered to an S3 bucket. A security policy requires these logs to be encrypted at rest.
How can this be achieved?

Enable SSE-S3
> Encryption is turned on by default which CloudTrail logs are delivered to S3 and specifically uses SSE-S3. So there is nothing for you to do.

Enable SSE-KMS

Enable SSE-AES
> SSE-S3 is using AES encryption so SSE-AES is just an alternative way of saying SSE-S3. 

The logs will be encrypted by default
> When you create a log you must specify a destination bucket. When logs are delivered to S3 they by default SSE-S3 (Server Side Encryption) will be applied. If you were to upload data directly to S3 you would have to turn on SSE-S3, so this is the case that CloudTrail automatically turns if on for you.

[[S3#Encrypt]]

---

# 53
A business wants to migrate a three-tier web application to AWS. For licensing considerations, the company needs to be able to control where the instances are placed and have visibility into the underlying sockets and cores.
Which compute model should be used to accomplish this task?

EC2 Spot Instances

EC2 Reserved Instances

EC2 Placement Groups

- EC2 Dedicated Hosts

#useful 
license只存在于一个主机的情况下就需要将instance永久的放在该主机上

---

# 54
A company has customer data hosted in an S3 bucket. They need to provide a backup to the customer’s AWS account. How can a copy of this data be delivered periodically to their customer?

Create an S3 Snapshot. Make the S3 Snapshot Public (@ 有这种东西?)

Create a bucket for that customer. Enable Cross-Region Replication. Create a Cross-Account role so that customer can access the bucket containing the copy

Use Snowball to transport the contents of the bucket to the customer AWS account

- Enable Cross-Region Replication with the Destination Bucket in the Customer S3 Bucket.

---

# 55
A company has documents which it must frequently access that will remain ==highly available== and after 30 days the files can be deleted. Which storage solution will meet those needs?

Glacier

[[EBS]]
> Elastic Block Store is not highly available since it would be attached to a single EC2 instance you would need to run multiple EC2 instances and a method of replicating the data to those other instances running in different AZs.


[[EFS]]
> EFS is a highly available storage solution. It is suited for when you have multiple EC2 instances which want common access to a single mounted volume 


- S3
> S3 by default replicates yout data across at least 3 AZs making it highly available. Lifecycle policies can delete files after creation based on the amounts of days defined by the user.

---

# 56
A Solution Architect must choose a storage solution that is suited for continuously processing a large amount of data, and that can write to disk with a throughput of 500 MiB per second. Which storage solution would meet these performance requirements?

EBS General Purpose

EBS Cold HDD

EBS IOPS SSD

- EBS Throughput Optimized HDD

---

# 57
A company has web-application which allows users to create dating profiles and request dates of other members after reviewing their profile. Users are able to upload a main profile photo. It is very common for users to change their profile photos and sometimes users will want to revert back to an older photo. What would ensure previous photos were not lost and could be easily recovered?

S3 with cross-region replication

S3 with a Bucket Policy

S3 with Transfer Accelerator

- S3 with Versioning Turned on

#useful 

---

# 58
A company has developed a product in the form of an application, which they've containerized. This product has been purchased by multiple customers who use it for data analysis. The containers are hosted on AWS Elastic Container Service (ECS) within a single cluster managed by the company. It's crucial to ensure that each customer's container is isolated from others to maintain virtual privacy. What is the best way to achieve this isolation in ECS?

- Security Group between containers
> Security groups in AWS act as virtual firewalls that control both inbound and outbound network traffic at the instance level. In the context of ECS, you can assign security groups to task definitions or directly to ECS services. By configuring these security groups properly, you can enforce network isolation between containers. This ensures that containers serving different customers cannot access each other, thereby maintaining the necessary isolation and privacy
> 
> Ideal for scenarios where containers need to be isolated at the network level to prevent cross-communication or data leaks between containers belonging to different customers.
> 
> Container 本身也可以看作是一个简化版的机器,加个SG合理

IAM roles for ECS

IAM role for services
> an IAM role for services provides the ECS service with the necessary permissions to make API calls to other AWS services on behalf of the user. This does not involve the networking aspect or the isolation of containers at the network level.

IAM roles for tasks

---
# 59
A company has a High-Performance Computing (HPC) application which requires lowest latency possible between multiple EC2 instances. Which EC2 Placement Group offers the best performance this type of application?

Packed Placement

Partition Placement

Spread Placement

- Cluster Placement

Performance Placement

---

# 60
An application requires access to files being generated from thousands of EC2 instances running within the same VPC. The application needs to easily read these generated files some which can be greater than 5 TB in size. What would be a convenient way to share the files across multiple EC2 instances as a common store?

Amazon S3

[[EBS]]

Storage Gateway

- [[EFS]]

---

# 61
A company operates a [[Redshift]] cluster and needs to securely import petabytes of sensitive financial data from Amazon S3. Both S3 and Redshift are located in the same AWS region. What are the best practices to securely transfer the data from S3 to Redshift?
(Choose 2)

Configure a VPC Interface Endpoint for S3 to ensure secure access.

Use AWS Snowball to physically transfer the data to Redshift.

- Enable Amazon Redshift Enhanced VPC Routing to route traffic through the VPC.
> Amazon Redshift Enhanced VPC Routing ensures that all data traffic between the Redshift cluster and other services (such as S3) within the same VPC uses the private network. This eliminates the risk of data traveling over the public internet, providing an extra layer of security. 

- Set up a VPC Gateway Endpoint for S3 to ensure secure data transfer.

Enable AWS Key Management Service (KMS) for encryption on both S3 and Redshift.
>  not directly address the security of data in transit between the two services

---

# 62
A marketing company's application requires the use of a NoSQL database. The IT department does not want to be in the management of the NoSQL servers.
Which Amazon service offers a NoSQL service that is fully managed and highly available?

Amazon RDS

Amazon Aurora

Simple DB 
> https://aws.amazon.com/jp/simpledb/ 
> 不是 fully managed

- Amazon DynamoDB

---

# 63
An application is running within a private subnet of an Amazon VPC and needs to establish an outbound connection to the internet to fetch package updates. The private subnet is using IPv4. Which solution will allow the instance in the private subnet to connect to the internet?

Create a VPN connection by launching a Virtual Private Gateway (VPG) in the public subnet and a Customer Gateway in the private subnet. Create a route in the private subnet's route table for 0.0.0.0/0 pointing to the VPG.

Create an [[IGW - Internet Gateway]] and create a route in the private subnet's route table for 0.0.0.0/0 pointing to the IGW.

Add an outbound ALLOW rule to both the NACL and Security Group for 0.0.0.0/0 to allow internet access for the application.

- Launch a NAT Gateway in a public subnet and create a route in the private subnet's route table for 0.0.0.0/0 pointing to the NAT Gateway.

---

# 64
A company has a web-application running in a single region and to be cost-effective they are not running any standby servers in another region in case of region failure. But in the case of such a disaster, they want to inform users of the interruption of service instead of the web-application being unresponsive and not resolving. What solution could they implement?

Route53 failover policy cannot failover to S3 Static Website Hosting. Instead, use Route53 Health Check which will trigger a CloudWatch Alarm which in turn trigger a Lambda to send emails via SES to all users about the downtime.

Route53 failover policy cannot failover to S3 Static Website Hosting. Instead, use Route53 Health Check which will trigger a CloudWatch Alarm which in turn can trigger an EC2 Instance action to turn on an EC2 instance in another region running a static website. In the UserData script use the AWS SDK to update Route53 domain to point to this EC2 instance.

Route53 failover policy cannot failover to S3 Static Website Hosting unless it is in front of a CloudFront distribution. Host a website on S3 Static Website Hosting place it in front of CloudFront. Use Route53 to failover to the CloudFront Distribution which operates in global region

- Use Route53 to failover to a website hosted on S3 Static Website Hosting in another region.

#useful 
> just like Nginx serve static HTML page when server broke

---

# 65
A company has an on-premise Cassandra database with an existing large workload which they are migrating to AWS to an EC2 Which EBS Volume Type would be most the most performance their use case?

EBS Throughput Optimized HDD

EBS General Purpose SSD

EBS Cold HDD

- EBS Provisioned IOPS SSD

> workload: **the amount of work to be done, especially by a particular person or machine in a period of time**

