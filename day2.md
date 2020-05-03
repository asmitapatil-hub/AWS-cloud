# What is Security group?

	A security group acts as a virtual firewall that controls the traffic for one or more instances. When you launch an instance, you can specify one or more security 
groups. otherwise, we use the default security group. You can add rules to each security group that allow traffic to or from its associated instances.


	AWS security groups (SGs) are associated with EC2 instances and provide security at the protocol and port access level. Each security group — working much the same 
way as a firewall — contains a set of rules that filter traffic coming into and out of an EC2 instance controlling both inbound and outbound traffic.


### How do security groups work?
	A security group acts as a virtual firewall for your instance to control inbound and outbound traffic.
For each security group, you add rules that control the inbound traffic to instances, and a separate set of rules that control the outbound traffic.


**Firewall**

- Monitors all incoming and outgoung traffic and accepts, rejests or drops the traffic based on predefined security rules.
- Designed to prevent unautorized access to or from a private network.
- It can be hardware or software based.
- Creates a barrier between private network and outside untrusted networks.


**AWS Firewall : Security Groups**

- 2 Sets of rules:
	1. Inbound	    - Controls incoming traffic
	2. Outbound  - Controls outgoing traffic 

- These rules can be used for open/close port while remotely accessing the system.
- We can create different security groups and can manage ports.
- We can use same security group for different instances if needed or can create new group for new instance.


---

**Service 2 - S3** 
S3 - Storage Secured Service
 
- We can store any type of data in form of object.
- Unlimited storage space available.
- **Bucket** needs to be created where we can store our data.
- **S3 does not require region separation**.
- Bucket name has to be unique across AWS.
- Bucket is like a folder, we can create folders inside it.
- We can upload or download files to or from these folders, but we cannot create a file here.
- **Guarantee of backup** from AWS.
- Can connect with EC2 also.
- We can host a website here.



