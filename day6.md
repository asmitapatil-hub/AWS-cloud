# Day-6


### Create instance

select new instance:

**step1:choose an Amazon Machine Image(AMI)**
	
select 1st one i.e. Amazon Linux 2 AMI (HVM), SSD Volume Type - ami-0323c3dd2da7fb37d (64-bit x86) / ami-0ce2e5b7d27317779 (64-bit Arm)

**step2:Choose an instance type**
	
select 2nd one i.e. General pupose t2 micro 1 vCPU 1GiB memory

**step3:Configure instance details**
	
if you see i icon then it will show info about that.

In IAM role select your created IAM role or default given by aws or you can create your own

so here we select our previous created one e.g vita-demo.

Enable termination protection - enable(check mark)

*Advanced Details*

**user data**

If you are creating ec2 and you have to do some task in ec2 then you have to pass command of that task.

If i want to create ec2 of linux then you have to pass linux command.e.g you are creating directory then you have to pass mkdir/tmp/dac in the box.

**step4: Add Storage**
	
put as it is go to next

**step5: Add tags**

click on add tag

key-Name       Value- Ec2-UserData (your choice)

**step6: Configure Security Group**

Assign a security group: select an existing security group

SO i am selecting vita-demo-20

**Step7: Review Instance Launch**

put as it is and click on launch then i had key so markup i acknowledge and click on launch instances.

it will show you launch status go to view instances.


### EC2 Instances Monitoring

To monitor resources and application like CPU utilization,RAM utilization,errors etc.

### EC2 Instances Status Check

Check your running applicatin status i.e. internet,o.s,etc.

you will also set alarm for status check.

1.System Status Checks  - To check your network and inform you about it.

2.Instance Status Checks - To check your instance related issues.


# VPC-Virtual Private Cloud

**What VPC contains**

AWS contains VPC contains subnets contains route table, internet gateways, security groups...

**What is VPC ?**

A virtual private cloud (VPC) is a virtual network dedicated to your AWS account. It is logically isolated from other virtual networks in the AWS Cloud. You can launch your AWS resources, such as Amazon EC2 instances, into your VPC. You can specify an IP address range for the VPC, add subnets, associate security groups, and configure route tables.

**What is subnet ?**

A subnet is a range of IP addresses in your VPC. You can launch AWS resources into a specified subnet. Use a public subnet for resources that must be connected to the internet, and a private subnet for resources that won't be connected to the internet. For more information about public and private subnets, see VPC and subnet basics.

We can select subnet in configure instance details

To protect the AWS resources in each subnet, you can use multiple layers of security, including security groups and network access control lists (ACL). For more information, see Internetwork traffic privacy in Amazon VPC.

Note : 1. Internet is not inside AWS, AWS connects to internet. 2. We get IP address from CIDR block. 3. VPC and subnets are given to us by our company, we need to make our Security groups.


**ISP- Internet Service Provider** 

eg. reliance, airtel 


## Cloud Watch 

In aws cloudWatch is a service used to monitor resources and application like CPU utilization,RAM utilization,errors etc.

you can create dashboards, Alarms,billing info,Logs store(logs groups),log search(insights,run query)


## Cloud Trail

In aws when you are perform any action it is autoatically stored in cloud trail like CCTV.

In aws services you can search cloudtrail(Track user activity and API usage) it will show you your recent events

You can view all events in details like event time, user name, event name,resource type,resource name etc.

Also use can use filter.


## User Data

In case we want any application to download, we can add our commands at the time of creating an instance.

your commands, linux/windows in user data are execute as root user(admin)

you can pass any command or shell script depend on os.

you can not use those command which require feedback command

To install any server you will use user data section


## Lambda

Run code without thinking about servers

lambda as API-convert into Request and Responce mode.  For e.g webservices

**Event driven automation**

We can configure event in S3. For eg: When someone puts a file in my S3, I can trigger Lambda at that time. Whenever I put a file in Bucket, lambda function can read that file and print its data

