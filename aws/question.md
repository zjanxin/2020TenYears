## Which of the following statements regarding S3 storage classes is true?

A. The availability of S3 and S3-IA is the same.
B. The durability of S3 and S3-IA is the same.
C. The latency of S3 and Glacier is the same.
D. The latency of S3 is greater than that of Glacier.

Answer：B
This is a common question on AWS exams, and relates to your understanding of the various S3 classes. S3 and S3-IA have the same durability, but the availability of S3 is one 9 greater than S3-IA. S3 has 99.99 availability, while S3-IA has 99.9 availability. Glacier has much greater first-byte latency than S3, so both C and D are false.


## A Solutions Architect is designing a solution thatincludes a managed VPN connection. To monitor whether the VPN connection is upor down, the Architect should use:

A. an external service to ping the VPN endpoint from outsidethe VPC.

B. AWS CloudTrail to monitor the endpoint.

C. the CloudWatch TunnelState Metric.

D. an AWS Lambda function that parses the VPN connectionlogs.

Answer: C
https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/monitoring-cloudwatch-vpn.html


## 3) A company currently stores data for on-premises applications on local drives. The chief technology
officer wants to reduce hardware costs by storing the data in Amazon S3 but does not want to make
modifications to the applications. To minimize latency, frequently accessed data should be available
locally.
What is a reliable and durable solution for a solutions architect to implement that will reduce the cost of
local storage?
A) Deploy an SFTP client on a local server and transfer data to Amazon S3 using AWS Transfer for SFTP.
B) Deploy an AWS Storage Gateway volume gateway configured in cached volume mode.
C) Deploy an AWS DataSync agent on a local server and configure an S3 bucket as the destination.
D) Deploy an AWS Storage Gateway volume gateway configured in stored volume mode

## 4) A company runs a public-facing three-tier web application in a VPC across multiple Availability Zones.
Amazon EC2 instances for the application tier running in private subnets need to download software
patches from the internet. However, the instances cannot be directly accessible from the internet.
Which actions should be taken to allow the instances to download the needed patches? (Select TWO.)
A) Configure a NAT gateway in a public subnet.
B) Define a custom route table with a route to the NAT gateway for internet traffic and associate it with the
private subnets for the application tier.
C) Assign Elastic IP addresses to the application instances.
D) Define a custom route table with a route to the internet gateway for internet traffic and associate it with
the private subnets for the application tier.
E) Configure a NAT instance in a private subnet.

## 5) A solutions architect wants to design a solution to save costs for Amazon EC2 instances that do not
need to run during a 2-week company shutdown. The applications running on the instances store data in
instance memory (RAM) that must be present when the instances resume operation.
Which approach should the solutions architect recommend to shut down and resume the instances?
A) Modify the application to store the data on instance store volumes. Reattach the volumes while restarting
them.
B) Snapshot the instances before stopping them. Restore the snapshot after restarting the instances.
C) Run the applications on instances enabled for hibernation. Hibernate the instances before the shutdown.
D) Note the Availability Zone for each instance before stopping it. Restart the instances in the same
Availability Zones after the shutdown

## 6) A company plans to run a monitoring application on an Amazon EC2 instance in a VPC. Connections
are made to the instance using its private IPv4 address. A solutions architect needs to design a solution
that will allow traffic to be quickly directed to a standby instance if the application fails and becomes
unreachable.
Which approach will meet these requirements?
A) Deploy an Application Load Balancer configured with a listener for the private IP address and register the
primary instance with the load balancer. Upon failure, de-register the instance and register the secondary
instance.
B) Configure a custom DHCP option set. Configure DHCP to assign the same private IP address to the
secondary instance when the primary instance fails.
C) Attach a secondary elastic network interface (ENI) to the instance configured with the private IP address.
Move the ENI to the standby instance if the primary instance becomes unreachable.
D) Associate an Elastic IP address with the network interface of the primary instance. Disassociate the
Elastic IP from the primary instance upon failure and associate it with a secondary instance.


3) B – An AWS Storage Gateway volume gateway connects on on-premises software application with cloudbacked storage volumes that can be mounted as Internet Small Computer System Interface (iSCSI) devices from
on-premises application servers. In cached volumes mode, all the data is stored in Amazon S3 and a copy of
frequently accessed data is stored locally.
4) A, B – A NAT gateway forwards traffic from the instances in the private subnet to the internet or other AWS
services, and then sends the response back to the instances. After a NAT gateway is created, the route tables for
private subnets must be updated to point internet traffic to the NAT gateway.
5) C – Hibernating an instance saves the contents of RAM to the Amazon EBS root volume. When the instance
restarts, the RAM contents are reloaded.
6) C – A secondary ENI can be added to an instance. While primary ENIs cannot be detached from an instance,
secondary ENIs can be detached and attached to a different instance. 


[xiao cha](https://iteablue.com/course/aws-saa-online-quiz/quizzes/saa-quiz-english-1/a-company-has-a-requirement-to-store-100tb-of-data-to-aws)

A company has a requirement to store 100TB of data to AWS.
This data will be exported using AWS Snowball and needs to then reside in a database layer. The database should have the facility to be queried from a business intelligence application. Each item is roughly 500KB in size. Which of the following is an ideal storage mechanism for the underlying data layer?
 AWS DynamoDB
 AWS Aurora
 AWS RDS
 AWS Redshift 

 Your company currently has a set of EC2 Instances hosted in AWS.
The states of these instances need to be monitored and each state change needs to be recorded. Which of the following can help fulfill this requirement? Choose 2 answers from the options given below.
 Use CloudWatch logs to store the state change of the instances.
 Use CloudWatch Events to monitor the state change of the events. 
 Use SQS to trigger a record to be added to a DynamoDB table.
 Use AWS Lambda to store a change record in a DynamoDB table. 

You have instances hosted in a private subnet in a VPC.
There is a need for the instances to download updates from the Internet. As an architect, what change would you suggest to the IT Operations team which would also be the most efficient and secure?
 Create a new public subnet and move the instance to that subnet.
 Create a new EC2 Instance to download the updates separately and then push them to therequired instance.
 Use a NAT Gateway to allow the instances in the private subnet to download theupdates. 
 Create a VPC link to the internet to allow the instances in the private subnet todownload the updates.

 Company planning on building and deploying a web application on AWS, needs to have a data store to store session data.
Which of the below services can be used to meet this requirement? Please select 2 correct options.
 AWS RDS
 AWS SQS
 DynamoDB 
 AWS ElastiCache 

 A Solutions Architect is designing an online shopping application running in a VPC on EC2 Instances behind an ELB Application Load Balancer.
The instances run in an Auto Scaling group across multiple Availability Zones. The application tier must read and write data to a customer managed database cluster. There should be no access to the database from the Internet, but the cluster must be able to obtain software patches from the Internet.
Which VPC design meets these requirements?
 Public subnets for both the application tier and the database cluster
 Public subnets for the application tier, and private subnets for the database cluster
 Public subnets for the application tier and NAT Gateway, and private subnets for the database cluster 
 Public subnets for the application tier, and private subnets for the database cluster and NAT Gateway

 You have an EC2 Instance placed inside a subnet.
You have created the VPC from scratch, and added the EC2 Instance to the subnet. It is required to ensure that this EC2 Instance has complete access to the Internet, since it will be used by users on the Internet.
Which of the following options would help accomplish this?
 Launch a NAT Gateway and add routes for 0.0.0.0/0
 Attach a VPC Endpoint and add routes for 0.0.0.0/0
 Attach an Internet Gateway and add routes for 0.0.0.0/0 
 Deploy NAT Instances in a public subnet and add routes for 0.0.0.0/0

 A company currently hosts a Redshift cluster in AWS.
For security reasons, it should be ensured that all traffic from and to the Redshift cluster does not go through the Internet.
Which of the following features can be used to fulfill this requirement in an efficient manner?
 Enable Amazon Redshift Enhanced VPC Routing. 
 Create a NAT Gateway to route the traffic.
 Create a NAT Instance to route the traffic.
 Create a VPN Connection to ensure traffic does not flow through the Internet.

 A company has a set of Hyper-V machines and VMware virtual machines.
They are now planning on migrating these instances to the AWS Cloud. Which of the following can be used to move these resources to the AWS Cloud?
 AWS Server Migration Service 
 Use AWS Migration Tools.
 Use AWS Config Tools.

 You are developing a new mobile application which is expected to be used by thousands of customers.
You are considering storing user preferences in AWS, and need a data store to save the same. Each data item is expected to be 20KB in size. The solution needs to be cost-effective, highly available, scalable and secure. How would you design the data layer?
 Create a new AWS MySQL RDS instance and store the user data there.
 Create a DynamoDB table with the required Read and Write capacity and use it as the data layer. 
 Use Amazon Glacier to store the user data.
 Use an Amazon Redshift Cluster for managing the user preferences.

 If a provisioned IOPS volume of 4iGB is created, what are the possible correct values for IOPS for the volume in order for it to be created?
A. 200
B. 300
C. 400
D. 500

A Security team reviewed their company’s VPC Flow Logs and found that traffic is being directed to the internet. The application in the VPC uses Amazon EC2 instances for compute and Amazon S3 for storage. The company’s goal is to eliminate internet access and allow the application to continue to function.What change should be made in the VPC before updating the route table?
A. Create a NAT gateway for Amazon S3 access
B. Create a VPC endpoint for Amazon S3 access
C. Create a VPC endpoint for Amazon EC2 access
D. Create a NAT gateway for Amazon EC2 access


A company has a Redshift Cluster defined in AWS.
The IT Operations team have ensured that both automated and manual snapshots are in place. Since the cluster is going to be run for a long duration of a couple of years, Reserved Instances have been purchased.
There has been a recent concern on the cost being incurred by the cluster. Which of the following steps can be carried out to minimize the costs being incurred by the cluster?
 Delete the manual snapshots . 
 Set the retention period of the automated snapshots to 35 days.
 Choose to use Spot Instances instead of Reserved Instances.
 Choose to use Instance store volumes to store the cluster data.

 company is planning on moving their PostgreSQL database to AWS.
They want to have the ability to have Replicas for the database and automated backup. Which of the following databases would be ideal for this scenario?
 Amazon Aurora 
 RDS for PostgreSQL
 AWS DynamoDB
 AWS Redshift

 Your company’s management team has asked you to devise a disaster recovery strategy for the current resources hosted in AWS.
They want to minimize costs, but be able to spin up the infrastructure when needed in another region. How could you accomplish this with the LEAST costs in mind?
 Create a duplicate of the entire infrastructure in another region.
 Create a Pilot Light infrastructure in another region.
 Use Elastic Beanstalk to create another copy of the infrastructure in anotherregion if a disaster occurs in the primary region.
 Use CloudFormation to spin up resources in another region if a disaster occurs inthe primary region. 

 You have a set of IIS Servers running on EC2 Instances.
You want to collect and process the log files generated from these IIS Servers. Which of the below services is ideal to run in this scenario?
 Amazon S3 for storing the log files and Amazon EMR for processing the log files. 
 Amazon S3 for storing the log files and EC2 Instances for processing the log file
 Amazon EC2 for storing and processing the log files.
 Amazon DynamoDB to store the logs and EC2 for running custom log analysis scripts.

 IOT sensors monitor the number of bags that are handled at an airport.
The data gets sent back to a Kinesis stream with default settings. Every alternate day, the data from the stream is sent to S3 for processing. But it is noticed that S3 is not receiving all of the data that is being sent to the Kinesis stream. What could be the reason for this?
 The sensors probably stopped working on somedays, hence data is not sent to the stream.
 S3 can only store data for a day.
 Data records are only accessible for a default of 24 hours from the time they areadded to a stream. 
 Kinesis streams are not meant to handle IoT related data.

 You have a requirement for deploying an existing Java based application to AWS.
There is a need for automatic scaling for the underlying environment. Which of the following can be used to deploy this environment in the quickest way possible?
 Deploy to an S3 bucket and enable web site hosting.
 Use the Elastic Beanstalk service to provision the environment. 
 Use EC2 with Auto Scaling for the environment.
 Use AMIs to build EC2 instances for deployment.

 You have been tasked with architecting an application in AWS.
The architecture would consist of EC2, the Classic Load Balancer, Auto Scaling and Route 53. There is a directive to ensure that Blue-Green deployments are possible in this architecture.
Which routing policy could you ideally use in Route 53 for achieving Blue-Green deployments?
 Simple
 Multi-answer
 Latency
 Weighted 

 A company is planning to deploy an application in AWS.
This application requires an EC2 Instance to continuously perform log processing activities requiring Max 500MiB/s of data throughput. Which of the following is the best storage option for this requirement?
 EBS IOPS
 EBS SSD
 EBS Throughput Optimized 
 EBS Cold Storage

 You have been given a business requirement to retain log files for your application for 10 years.
You need to regularly retrieve the most recent logs for troubleshooting. Your logging system must be cost-effective, given the large volume of logs. What technique should you use to meet these requirements?
 Store your log in Amazon CloudWatch Logs.
 Store your logs in Amazon Glacier.
 Store your logs in Amazon S3, and use Lifecycle Policies to archive to AmazonGlacier. 
 Store your logs on Amazon EBS, and use Amazon EBS Snapshots to archive them.

 A concern raised in your company is that developers could potentially delete production-based EC2 resources.
As a Cloud Admin, which of the below options would you choose to help alleviate this concern? Choose 2 options.
 Tag the production instances with production-identifying tag and add resource-level permissions to the developers with an explicit deny on the terminate API call to instances with the production tag. 
 Create a separate AWS account and add the developers to that account. 
 Modify the IAM policy on the developers to require MFA before deleting EC2 instances, and disable MFA access to the employee.
 Modify the IAM policy on the developers to require MFA before deleting EC2 instances.

 A company needs to monitor the read and write IOPS metrics for their AWS MySQL RDS instance and send real-time alerts to their Operations team.
Which AWS services can accomplish this? Choose 2 answers from the options given below.
 Amazon Simple Email Service
 Amazon CloudWatch 
 Amazon Simple Queue Service
 Amazon Route 53
 Amazon Simple Notification Service 

 A company’s business continuity department is worried about the EBS Volumes hosted in AWS and wants to ensure that redundancy is achieved for the same.
What must be done to achieve this in a cost-effective manner?
 Nothing, since by default, EBS Volumes are replicated within their Availability Zones. 
 Copy the data to S3 bucket for data redundancy.
 Create EBS Snapshots in another Availability Zone for data redundancy.
 Copy the data to a DynamoDB table for data redundancy.

 A mobile application hosted on AWS needs to access a Data Store in AWS.
With each item measuring around 10KB in size, the latency of data access must remain consistent despite very high application traffic. Which of the following would be an ideal Data Store for the application?
 AWS DynamoDB 
 AWS EBS Volumes
 AWS Glacier
 AWS Redshift

 A company is planning to design a Microservices architectured application that will be hosted in AWS.
This entire architecture needs to be decoupled whenever possible. Which of the following services can help achieve this? Please select 2 correct options.
 AWS SNS 
 AWS ELB
 AWS Auto Scaling
 AWS SQS 

 An organization planning to use AWS for their production roll out, wants to implement automation for deployment such that it will automatically create a LAMP stack,download the latest PHP installable from S3 and setup the ELB.
Which of the below mentioned AWS services meets the requirement for making an orderly deployment of the software?
 AWS Elastic Beanstalk 
 AWS CloudFront
 AWS CloudFormation
 AWS DevOps

 Your company is planning on using the API Gateway service to manage APIs for developers and users.
There is a need to segregate the access rights for both developers and users. How can this be accomplished?
 Use IAM permissions to control the access. 
 Use AWS Access keys to manage the access.
 Use AWS KMS service to manage the access.
 Use AWS Config Service to control the access.

 Your organization is building a collaboration platform for which they chose AWS EC2 for web and application servers and MySQL RDS instance as the database.
Due to the nature of the traffic to the application, they would like to increase the number of connections to RDS instance. How can this be achieved?
 Login to RDS instance and modify database config file under /etc/mysql/my.cnf
 Create a new parameter group, attach it to DB instance and change the setting . 
 Create a new option group, attach it to DB instance and change the setting.
 Modify setting in default options group attached to DB instance.

Your company needs to keep all system logs for audit purposes, and may rarely need to retrieve these logs for audit purposes and present them upon request within a week.
The logs are 10TB in size. Which option would be the most cost-effective one for storing all these system logs?
 Amazon Glacier 
 S3-Reduced Redundancy Storage
 EBS backed storage connected to EC2
 AWS CloudFront

You have configured an Auto-scaling group for which the minimum running instance is 2 and maximum running instance is 10.
For the past 30 minutes, all five instances have been running at 100 CPU Utilization; however, the Auto Scaling group has not added any more instances to the group. What is the most likely cause for this? Choose 2 answers from the options given below.
 You already have 20 on-demand instances running. 
 The Auto Scaling group's MAX size is set at five.
 The Auto Scaling group's scale down policy is too high.
 The Auto Scaling group's scale up policy has not yet been reached. 

You have been instructed by your supervisor to devise a disaster recovery model for the resources in their AWS account.
The key requirement while devising the solution is to ensure that the cost is at a minimum. Which of the following disaster recovery mechanisms would you employ in such a scenario?
 Backup and Restore 
 Pilot Light
 Warm standby
 Multi-Site

Your company currently has a set of EC2 Instances running a web application which sits behind an Elastic Load Balancer.
You also have an Amazon RDS instance which is accessible from the web application. You have been asked to ensure that this architecture is self-healing in nature and cost-effective. Which of the following would fulfill this requirement? Choose 2 answers from the options given below.
 Use CloudWatch metrics to check the utilization of the web layer. Use Auto Scaling Group to scale the web instances accordingly based on the CloudWatch metrics. 
 Use CloudWatch metrics to check the utilization of the databases servers. Use Auto Scaling Group to scale the database instances accordingly based on the CloudWatch metrics.
 Utilize the Read Replica feature for the Amazon RDS layer.
 Utilize the Multi-AZ feature for the Amazon RDS layer. 

You have a requirement to get a snapshot of the current configuration of resources in your AWS Account.
Which of the following services can be used for this purpose?
 AWS CodeDeploy
 AWS Trusted Advisor
 AWS Config 
 AWS IAM

As an architect you have been told to construct the deployment design for an application.
You need to ensure that the application is fault tolerant. When using the following AWS services, which elements of the application needs more attention for deploying high availability solutions? Choose 2 answers from the options below.
 Amazon DynamoDB
 Amazon Elastic Compute Cloud (EC2 
 Amazon Elastic Load Balancing 
 Amazon Simple Storage Service (S3)

You have been designing a CloudFormation template that creates one elastic load balancer fronting two EC2 instances.
Which section of the template should you edit so that the DNS of the load balancer is returned upon creation of the stack?
 Resources
 Parameters
 Outputs 
 Mappings

A company has a set of VPC’s defined in AWS.
They need to connect this to their onpremises network. They need to ensure that all data is encrypted in transit. Which of the following would you use to connect the VPC’s to the on-premises networks?
 VPC Peering
 VPN connections 
 AWS Direct Connect
 Placement Groups

A company is planning on migrating their infrastructure to AWS.
For the data stores , the company does not want to manage the underlying infrastructure. Which of the following would be ideal for this scenario? Choose 2 answers from the options give below
 AWS S3 
 AWS EBS Volumes
 AWS DynamoDB 
 AWS EC2

Your company has a set of VPC’s.
There is now a requirement to establish communication across the Instances in the VPC’s. Your supervisor has asked you to implement the VPC peering connection. Which of the following considerations would you keep in mind for VPC peering. Choose 2 answers from the options below
 Ensuring that the VPC's don't have overlapping CIDR blocks 
 Ensuring that no on-premises communication is required via transitive routing 
 Ensuring that the VPC's only have public subnets for communication
 Ensuring that the VPC's are created in the same region

Your company wants to enable encryption of services such as S3 and EBS volumes so
They want to have complete control over the keys and the entire lifecycle around the keys. How can you accomplish this?
 Use the HSM Module 
 Use the KMS service
 Enable S3 server-side encryption
 Enable EBS Encryption with the deaf ult KMS

A company has setup some EC2 Instances in a VPC with the default Security group and NACL settings.
They want to ensure that IT admin staff can connect to the EC2 Instance via SSH. As an architect what would you ask the IT admin team to do to ensure that they can connect to the EC2 Instance from the Internet. Choose 2 answers from the options below
 Ensure that the Instance has a Public or Elastic IP 
 Ensure that the Instance has a Private IP
 Ensure to modify the Security groups 
 Ensure to modify the NACL rules

Your company has a set of EBS volumes and a set of adjoining EBS snapshots.
They want to minimize the costs for the underlying EBS snapshots. Which of the following approaches provides the lowest cost for Amazon Elastic Block Store snapshots while giving you the ability to fully restore data?
 Maintain two snapshots: the original snapshot and the latest incremental snapshot.
 Maintain a volume snapshot; subsequent snapshots will overwrite one another
 Maintain a single snapshot: the latest snapshot is both Incremental and complete. 
 Maintain the most current snapshot, archive the original and incremental to Amazon Glacier.

Your company has a set of AWS RDS Instances.
Your management has asked you to disable Automated backups to save on cost. When you disable automated backups for AWS RDS, what are you compromising on?
 Nothing,you are actually saving resources on aws
 You are disabling the point-in-time recovery. 
 Nothing really, you can still take manual backups.
 You cannot disable automated backups in RDS.

A customer is hosting their company website on a cluster of web servers that are behind a public-facing load balancer.
The customer also uses Amazon Route 53 to manage their public DNS. How should Route 53 be configured to ensure the custom domain is made to point to the load balancer? Choose 2 answers from the options below.
 Create an A record pointing to the IP address of the load balancer
 Create a CNAME record pointing to the load balancer DNS name.
 Create an alias for a CNAME record to the load balancer DNS name . 
 Ensure that a hosted zone is in place 