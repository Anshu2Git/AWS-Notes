# AWS-Notes

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
# IAM
**AWS IAM (Identity and Access Management)** is a service provided by Amazon Web Services (AWS) that helps you manage access to your AWS resources. It's like a security system for your AWS account.

IAM allows you to create and manage users, groups, and roles. Users represent individual people or entities who need access to your AWS resources. Groups are collections of users with similar access requirements, making it easier to manage permissions. Roles are used to grant temporary access to external entities or services.

With IAM, you can control and define permissions through policies. Policies are written in JSON format and specify what actions are allowed or denied on specific AWS resources. These policies can be attached to IAM entities (users, groups, or roles) to grant or restrict access to AWS services and resources.

IAM follows the principle of least privilege, meaning users and entities are given only the necessary permissions required for their tasks, minimizing potential security risks. IAM also provides features like multi-factor authentication (MFA) for added security and an audit trail to track user activity and changes to permissions.

By using AWS IAM, you can effectively manage and secure access to your AWS resources, ensuring that only authorized individuals have appropriate permissions and actions are logged for accountability and compliance purposes.

Overall, IAM is an essential component of AWS security, providing granular control over access to your AWS account and resources, reducing the risk of unauthorized access and helping maintain a secure environment.

**Components of IAM**
**Users**: IAM users represent individual people or entities (such as applications or services) that interact with your AWS resources. Each user has a unique name and security credentials (password or access keys) used for authentication and access control.

**Groups**: IAM groups are collections of users with similar access requirements. Instead of managing permissions for each user individually, you can assign permissions to groups, making it easier to manage access control. Users can be added or removed from groups as needed.

**Roles**: IAM roles are used to grant temporary access to AWS resources. Roles are typically used by applications or services that need to access AWS resources on behalf of users or other services. Roles have associated policies that define the permissions and actions allowed for the role.

**Policies**: IAM policies are JSON documents that define permissions. Policies specify the actions that can be performed on AWS resources and the resources to which the actions apply. Policies can be attached to users, groups, or roles to control access. IAM provides both AWS managed policies (predefined policies maintained by AWS) and customer managed policies (policies created and managed by you).
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

# Introduction to EC2:
What is **EC2**, and why is it important?

- Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud.
- Access reliable, scalable infrastructure on demand. Scale capacity within minutes with SLA commitment of 99.99% availability.
- Provide secure compute for your applications. Security is built into the foundation of Amazon EC2 with the AWS Nitro System.
- Optimize performance and cost with flexible options like AWS Graviton-based instances, Amazon EC2 Spot instances, and AWS Savings Plans.
- 
**EC2 usecases**

Deliver secure, reliable, high-performance, and cost-effective compute infrastructure to meet demanding business needs.
Access the on-demand infrastructure and capacity you need to run HPC applications faster and cost-effectively.
Access environments in minutes, dynamically scale capacity as needed, and benefit from AWS’s pay-as-you-go pricing.
Deliver the broadest choice of compute, networking (up to 400 Gbps), and storage services purpose-built to optimize price performance for ML projects

**Managing EC2 Instances:**
Starting, stopping, and terminating instances.
Monitoring instance performance and utilization.
Basic troubleshooting and accessing instances using SSH (Secure Shell).

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
**VPC**
Imagine you want to set up a private, secure, and isolated area in the cloud where you can run your applications and store your data. This is where a VPC comes into play.

A VPC is a virtual network that you create in the cloud. It allows you to have your own private section of the internet, just like having your own network within a larger network. Within this VPC, you can create and manage various resources, such as servers, databases, and storage.

Think of it as having your own little "internet" within the bigger internet. This virtual network is completely isolated from other users' networks, so your data and applications are secure and protected.

Just like a physical network, a VPC has its own set of rules and configurations. You can define the IP address range for your VPC and create smaller subnetworks within it called subnets. These subnets help you organize your resources and control how they communicate with each other.

To connect your VPC to the internet or other networks, you can set up gateways or routers. These act as entry and exit points for traffic going in and out of your VPC. You can control the flow of traffic and set up security measures to protect your resources from unauthorized access.

With a VPC, you have control over your network environment. You can define access rules, set up firewalls, and configure security groups to regulate who can access your resources and how they can communicate.

**Virtual private clouds (VPC) :- A VPC is a virtual network that closely resembles a traditional network that you'd operate in your own data center. After you create a VPC, you can add subnets.
Subnets :- A subnet is a range of IP addresses in your VPC. A subnet must reside in a single Availability Zone. After you add subnets, you can deploy AWS resources in your VPC.
IP addressing :- You can assign IP addresses, both IPv4 and IPv6, to your VPCs and subnets. You can also bring your public IPv4 and IPv6 GUA addresses to AWS and allocate them to resources in your VPC, such as EC2 instances, NAT gateways, and Network Load Balancers.
Network Access Control List (NACL) :- A Network Access Control List is a stateless firewall that controls inbound and outbound traffic at the subnet level. It operates at the IP address level and can allow or deny traffic based on rules that you define. NACLs provide an additional layer of network security for your VPC.
Security Group :- A security group acts as a virtual firewall for instances (EC2 instances or other resources) within a VPC. It controls inbound and outbound traffic at the instance level. Security groups allow you to define rules that permit or restrict traffic based on protocols, ports, and IP addresses.  
Routing :- Use route tables to determine where network traffic from your subnet or gateway is directed.
Gateways and endpoints :- A gateway connects your VPC to another network. For example, use an internet gateway to connect your VPC to the internet. Use a VPC endpoint to connect to AWS services privately, without the use of an internet gateway or NAT device.
Peering connections :- Use a VPC peering connection to route traffic between the resources in two VPCs.
Traffic Mirroring :- Copy network traffic from network interfaces and send it to security and monitoring appliances for deep packet inspection.
Transit gateways :- Use a transit gateway, which acts as a central hub, to route traffic between your VPCs, VPN connections, and AWS Direct Connect connections.
VPC Flow Logs :- A flow log captures information about the IP traffic going to and from network interfaces in your VPC
VPN connections** :- Connect your VPCs to your on-premises networks using AWS Virtual Private Network (AWS VPN).

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
**AWS Security using Security Groups and NACL**
**Security Groups:**
    Security Groups act as virtual firewalls for Amazon EC2 instances (virtual servers) at the instance level. They control inbound and outbound traffic by allowing or denying specific protocols, ports, and IP addresses.
    Each EC2 instance can be associated with one or more security groups, and each security group consists of inbound and outbound rules.
    Inbound rules determine the traffic that is allowed to reach the EC2 instance, whereas outbound rules control the traffic leaving the instance.
    Security Groups can be configured using IP addresses, CIDR blocks, security group IDs, or DNS names to specify the source or destination of the traffic.
    They operate at the instance level and evaluate the rules before allowing traffic to reach the instance.
    Security Groups are stateful, meaning that if an inbound rule allows traffic, the corresponding outbound traffic is automatically allowed, and vice versa.
    Changes made to security group rules take effect immediately.

**Network Access Control Lists (NACLs):**
    NACLs are an additional layer of security that operates at the subnet level. They act as stateless traffic filters for inbound and outbound traffic at the subnet boundary.
    Unlike Security Groups, NACLs are associated with subnets, and each subnet can have only one NACL. However, multiple subnets can share the same NACL.
    NACLs consist of a numbered list of rules (numbered in ascending order) that are evaluated in order from lowest to highest.
    Each rule in the NACL includes a rule number, protocol, rule action (allow or deny), source or destination IP address range, port range, and ICMP (Internet Control Message Protocol) type.
    NACL rules can be configured to allow or deny specific types of traffic based on the defined criteria.
    They are stateless, which means that if an inbound rule allows traffic, the corresponding outbound traffic must be explicitly allowed using a separate outbound rule.
    Changes made to NACL rules may take some time to propagate to all the resources using the associated subnet.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

**AWS S3**
About
What is Amazon S3?

Simple Storage Service is a scalable and secure cloud storage service provided by Amazon Web Services (AWS). It allows you to store and retrieve any amount of data from anywhere on the web.

**What are S3 buckets?**

S3 buckets are containers for storing objects (files) in Amazon S3. Each bucket has a unique name globally across all of AWS. You can think of an S3 bucket as a top-level folder that holds your data.

Why use S3 buckets?

S3 buckets provide a reliable and highly scalable storage solution for various use cases. They are commonly used for backup and restore, data archiving, content storage for websites, and as a data source for big data analytics.

**Key benefits of S3 buckets**

S3 buckets offer several advantages, including:

Durability and availability: S3 provides high durability and availability for your data.
Scalability: You can store and retrieve any amount of data without worrying about capacity constraints.
Security: S3 offers multiple security features such as encryption, access control, and audit logging.
Performance: S3 is designed to deliver high performance for data retrieval and storage operations.
Cost-effective: S3 offers cost-effective storage options and pricing models based on your usage patterns.
Creating and Configuring S3 Buckets
Creating an S3 bucket

To create an S3 bucket, you can use the AWS Management Console, AWS CLI (Command Line Interface), or AWS SDKs (Software Development Kits). You need to specify a globally unique bucket name and select the region where you want to create the bucket.

Choosing a bucket name and region

The bucket name must be unique across all existing bucket names in Amazon S3. It should follow DNS naming conventions, be 3-63 characters long, and contain only lowercase letters, numbers, periods, and hyphens. The region selection affects data latency and compliance with specific regulations.

**Bucket properties and configurations**

Versioning: Versioning allows you to keep multiple versions of an object in the bucket. It helps protect against accidental deletions or overwrites.
Bucket-level permissions and policies

Bucket-level permissions and policies define who can access and perform actions on the bucket. You can grant permissions using IAM (Identity and Access Management) policies, which allow fine-grained control over user access to the bucket and its objects.

Uploading and Managing Objects in S3 Buckets
Uploading objects to S3 buckets

You can upload objects to an S3 bucket using various methods, including the AWS Management Console, AWS CLI, SDKs, and direct HTTP uploads. Each object is assigned a unique key (name) within the bucket to retrieve it later.

Object metadata and properties

Object metadata contains additional information abouteach object in an S3 bucket. It includes attributes like content type, cache control, encryption settings, and custom metadata. These properties help in managing and organizing objects within the bucket.

File formats and object encryption

S3 supports various file formats, including text files, images, videos, and more. You can encrypt objects stored in S3 using server-side encryption (SSE). SSE options include SSE-S3 (Amazon-managed keys), SSE-KMS (AWS Key Management Service), and SSE-C (customer-provided keys).

Lifecycle management

Lifecycle management allows you to define rules for transitioning objects between different storage classes or deleting them automatically based on predefined criteria. For example, you can move infrequently accessed data to a lower-cost storage class after a specified time or delete objects after a certain retention period.

Multipart uploads

Multipart uploads provide a mechanism for uploading large objects in parts, which improves performance and resiliency. You can upload each part in parallel and then combine them to create the complete object. Multipart uploads also enable resumable uploads in case of failures.

Managing large datasets with S3 Batch Operations

S3 Batch Operations is a feature that allows you to perform bulk operations on large numbers of objects in an S3 bucket. It provides an efficient way to automate tasks such as copying objects, tagging, and restoring archived data.

Advanced S3 Bucket Features
S3 Storage Classes

S3 offers multiple storage classes, each designed for different use cases and performance requirements:

S3 Replication

S3 replication enables automatic and asynchronous replication of objects between S3 buckets in different regions or within the same region. Cross-Region Replication (CRR) provides disaster recovery and compliance benefits, while Same-Region Replication (SRR) can be used for data resilience and low-latency access.

S3 Event Notifications and Triggers

S3 event notifications allow you to configure actions when specific events occur in an S3 bucket. For example, you can trigger AWS Lambda functions, send messages to Amazon Simple Queue Service (SQS), or invoke other services using Amazon SNS when an object is created or deleted.

S3 Batch Operations

S3 Batch Operations allow you to perform large-scale batch operations on objects, such as copying, tagging, or deleting, across multiple buckets. It simplifies managing large datasets and automates tasks that would otherwise be time-consuming.

Security and Compliance in S3 Buckets
S3 bucket security considerations

Ensure that S3 bucket policies, access control, and encryption settings are appropriately configured. Regularly monitor and audit access logs for unauthorized activities.

Data encryption at rest and in transit

Encrypt data at rest using server-side encryption options provided by S3. Additionally, enable encryption in transit by using SSL/TLS for data transfers.

Access logging and monitoring

Enable access logging to capture detailed records of requests made to your S3 bucket. Monitor access logs and configure alerts to detect any suspicious activities or unauthorized access attempts.

S3 Bucket Management and Administration
S3 bucket policies

Create and manage bucket policies to control access to your S3 buckets. Bucket policies are written in JSON and define permissions for various actions and resources.

S3 access control and IAM roles

Use IAM roles and policies to manage access to S3 buckets. IAM roles provide temporary credentials and fine-grained access control to AWS resources.

S3 APIs and SDKs

Interact with S3 programmatically using AWS SDKs or APIs. These provide libraries and methods for performing various operations on S3 buckets and objects.

Monitoring and logging with CloudWatch

Utilize Amazon CloudWatch to monitor S3 metrics, set up alarms for specific events, and collect and analyze logs for troubleshooting and performance optimization.

S3 management tools

AWS provides multiple management tools, such as the AWS Management Console, AWS CLI, and third-party tools, to manage S3 buckets efficiently and perform operations like uploads, downloads, and bucket configurations.

**Troubleshooting and Error Handling**
Common S3 error messages and their resolutions

Understand common S3 error messages like access denied, bucket not found, and exceeded bucket quota. Troubleshoot and resolve these errors by checking permissions, bucket configurations, and network connectivity.

Debugging S3 bucket access issues

Investigate and resolve issues related to access permissions, IAM roles, and bucket policies. Use tools like AWS CloudTrail and S3 access logs to identify and troubleshoot access problems.

Data consistency and durability considerations

Ensure data consistency and durability by understanding S3's data replication and storage mechanisms. Verify that data is correctly uploaded, retrieve objects using proper methods, and address any data integrity issues.

Recovering deleted objects

If an object is accidentally deleted, you can often recover it using versioning or S3 event notifications. Additionally, consider enabling Cross-Region Replication (CRR) for disaster recovery scenarios.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
**AWS Continuous Integration Demo
Set Up GitHub Repository**
The first step in our CI journey is to set up a GitHub repository to store our Python application's source code. If you already have a repository, feel free to skip this step. Otherwise, let's create a new repository on GitHub by following these steps:

Go to github.com and sign in to your account.
Click on the "+" button in the top-right corner and select "New repository."
Give your repository a name and an optional description.
Choose the appropriate visibility option based on your needs.
Initialize the repository with a README file.
Click on the "Create repository" button to create your new GitHub repository.
Great! Now that we have our repository set up, we can move on to the next step.

**Create an AWS CodePipeline**
In this step, we'll create an AWS CodePipeline to automate the continuous integration process for our Python application. AWS CodePipeline will orchestrate the flow of changes from our GitHub repository to the deployment of our application. Let's go ahead and set it up:

Go to the AWS Management Console and navigate to the AWS CodePipeline service.
Click on the "Create pipeline" button.
Provide a name for your pipeline and click on the "Next" button.
For the source stage, select "GitHub" as the source provider.
Connect your GitHub account to AWS CodePipeline and select your repository.
Choose the branch you want to use for your pipeline.
In the build stage, select "AWS CodeBuild" as the build provider.
Create a new CodeBuild project by clicking on the "Create project" button.
Configure the CodeBuild project with the necessary settings for your Python application, such as the build environment, build commands, and artifacts.
Save the CodeBuild project and go back to CodePipeline.
Continue configuring the pipeline stages, such as deploying your application using AWS Elastic Beanstalk or any other suitable deployment option.
Review the pipeline configuration and click on the "Create pipeline" button to create your AWS CodePipeline.
Awesome job! We now have our pipeline ready to roll. Let's move on to the next step to set up AWS CodeBuild.

**Configure AWS CodeBuild**
In this step, we'll configure AWS CodeBuild to build our Python application based on the specifications we define. CodeBuild will take care of building and packaging our application for deployment. Follow these steps:

In the AWS Management Console, navigate to the AWS CodeBuild service.
Click on the "Create build project" button.
Provide a name for your build project.
For the source provider, choose "AWS CodePipeline."
Select the pipeline you created in the previous step.
Configure the build environment, such as the operating system, runtime, and compute resources required for your Python application.
Specify the build commands, such as installing dependencies and running tests. Customize this based on your application's requirements.
Set up the artifacts configuration to generate the build output required for deployment.
Review the build project settings and click on the "Create build project" button to create your AWS CodeBuild project.
Fantastic! With AWS CodeBuild all set up, we're now ready to witness the magic of continuous integration in action.

**Trigger the CI Process**
In this final step, we'll trigger the CI process by making a change to our GitHub repository. Let's see how it works:

Go to your GitHub repository and make a change to your Python application's source code. It could be a bug fix, a new feature, or any other change you want to introduce.
Commit and push your changes to the branch configured in your AWS CodePipeline.
Head over to the AWS CodePipeline console and navigate to your pipeline.
You should see the pipeline automatically kick off as soon as it detects the changes in your repository.
Sit back and relax while AWS CodePipeline takes care of the rest. It will fetch the latest code, trigger the build process with AWS CodeBuild, and deploy the application if you configured the deployment stage.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
