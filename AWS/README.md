# AWS Interview Questions


What is AWS?
```
AWS stands for Amazon Web Services and is a platform that provides database storage, secure cloud 
services, offering to compute power, content delivery, and many other services to develop business levels.
```

Explain the key components of AWS?
```
• Route 53
• Simple E-mail serve
• Identity and Access Management
• Simple Storage Device (S3)
• Elastic Compute Cloud (EC2)
• Elastic Block Store (EBS)
• Cloud watch
```

What is AMI?
```
An Amazon Machine Image (AMI) is a special type of virtual appliance that is used to create a virtual 
machine within the Amazon Elastic Compute Cloud("EC2").
The AMI is a backup of the entire system or instance.
use an AMI to save instance configuration.
AMI (Amazon Machine Image) is a backup of Entire EC2 instance.
An AMI can be created using a snapshot.
AMI is a representation of system state at specific time. You can also boot from it.
```

what is snapshot?
```
A snapshot is of an EBS volume where you are able to save state and reboot with the same data at a certain point in time.
use EBS snapshots as backup solutions for a database volume.
EBS Snapshot very often represents a backup of specific EBS volume, it might be any volume (Root volume, data volume, etc.)
snapshots only capture data that has been written to your Amazon EBS volume at the time the snapshot command is issued
```

What is S3?
```
S3 stands for Simple Storage Service, which is an interface to store and retrieve any amount of 
data from anywhere and at any time on the web.”Pay as you go” is the payment model for S3.
```

what is vpc in aws?
```
Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual 
network that you've defined. This virtual network closely resembles a traditional network that 
you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS.
```

What can AWS Lambda be used for?
```
AWS Lambda is Amazon's serverless compute service. You can run your code on it without having 
to manage servers or even containers. It'll automatically scale depending on how much work you 
feed into it. You can use it in data pipelines or to respond to web requests or even to compose and send emails.
```

What is s3 in aws?
```
Amazon S3 is storage service. Amazon S3 a simple web services interface to store and retrieve 
any amount of data from anywhere on the web. With Amazon S3, you pay only for the storage you actually use.
```

what is redshift in AWS?
```
Amazon Redshift is a fully managed, petabyte-scale data warehouse service in the cloud.
Amazon Redshift offers fast query performance using the same SQL-based tools and business 
intelligence applications that you use today. Redshift is based on PostgreSQL 8.0.2.
it allows more queries to run in parallel, no single query can use all of the machine's resources.
```

Name The Several Layers Of Cloud Computing?
```
• PaaS – Platform as a Service
• IaaS – Infrastructure as a Service
• SaaS – Software as a Service
```

Amazon Simple Queue Service (SQS)
```
Amazon Simple Queue Service (SQS) is a fully managed message queuing service that 
enables you to decouple and scale microservices, distributed systems, 
and serverless applications.
```

Functionality of SQS
```
• Unlimited queues and messages
• Payload Size
• Batches
• Long polling
• Retain messages in queues for up to 14 days
• Send and read messages simultaneously
• Message locking
• Queue sharing
• Server-side encryption (SSE)
• Dead Letter Queues (DLQ)
```

What is the difference between SNS and SQS?
```
SNS is a distributed publish-subscribe system. Messages are pushed to subscribers 
as and when they are sent by publishers to SNS. SQS is distributed queuing system. 
Polling inherently introduces some latency in message delivery in SQS unlike SNS 
where messages are immediately pushed to subscribers.
```

How long can a lambda function run?
```
You can set your memory in 64MB increments from 128MB to 1.5GB. Q: How long can an 
AWS Lambda function execute? All calls made to AWS Lambda must complete execution 
within 300 seconds. The default timeout is 3 seconds, but you can set the 
timeout to any value between 1 and 300 seconds.
```