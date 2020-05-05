# SNS simple notification service
 
SNS managed message topics for pubs/subs and serverless applications.

Amazon SNS is a highly available, durable, secure, fully managed pub/sub messaging service that enables you to decouple microservices, distributed systems, and event-driven serverless applications. Amazon SNS provides topics for high-throughput, push-based, many-to-many messaging.

e.g ec2 create event--- get notify through email
    ec2 server down---- get notify through email


## Topic

A topic is a message channel. When you publish a message to a topic, it fans out the message to all subscribed endpoints

### How to create Topic

**Topic Name**

e.g.vita-demo-1

**Display name - optional**

To use this topic with SMS subscriptions, enter a display name.
e.g.vita

**Encryption - optional**

Amazon SNS provides in-transit encryption by default. Enabling server-side encryption adds at-rest encryption to your topic.

**Access policy - optional**

This policy defines who can access your topic. By default, only the topic owner can publish or subscribe to the topic.

Make sure it is published for **everyone.**

**Delivery retry policy (HTTP/S) - optional**

The policy defines how Amazon SNS retries failed deliveries to HTTP/S endpoints. To modify the default settings, expand this section.

**Delivery status logging - optional**

These settings configure the logging of message delivery status to CloudWatch Logs

you can also create IAM role and copy ARN from IAM roles



## Subscriptions

### How to create subscription

**Topic ARN**

select your topic ARN from topic.

**Protocol**

select  any one of them e.g. email

**Endpoint**

enter your protocol details so that you can receive notification from Amazon SNS.
e.g. <example123@gmail.com>

**Subscription filter policy - optional**

This policy filters the messages that a subscriber receives

**Redrive policy (dead-letter queue) - optional**

Send undeliverable messages to a dead-letter queue.


Your subscription is created successfully but status is pending.Bcoz of no confirmation from your side.

e.g I got confirmation mail from AWS notification. After click on confirmation my subscription confirmed then refresh your SNS page your status is **confirmed**.


### SNS models

**1.Pubs-Publisher**  

Pubs send messages thr topic
e.g.producer

**2.Subs-Subscriber**

Subs receive messages thr topic
 e.g. consumer




## How to select Publisher?

### s3 Bucket

scalable storage in the cloud

select your existing bucket e.g. vita-demo20

## properties

### Events

Receive notification when specific events occur in your bucket.

select *add notification*, click on *all object create events*,name- *vita-demo*,send to *SNS Topic*,SNS-e.g.*vita-demo-1* and save it.
Again if you upload any file then you get notification thr mail from Amazon s3.


**Back-Up Related terms:**

## Volumes

It is like Harddisk.

select any instance(min ram). goto actions. create snapshot

## Snapshot

**How to Create Snapshot**

Description-(Give name to your snapshot e.g. vita-snapshot-1-8gb)
create snapshot and check status is completed

your snapshot are stored in s3 bucket which is invisible.
When you create new snapshot then every time it is increament order it is compaired with last volume. e.g. git pull



select ec2-userData instance--go to actions--images--create image--name it--create image.
select AMIs in section. it is used when we launch instance.

**delete all snapshots and AMIs before logout.


## AMI verses Snapshots

1. Snapshots are associated with EBS while AMIs are associared with EC2 instances. 

2. Snapshots are the backup of the data on EBS volumes, whereas AMIs are bootable copy of the whole EC2 instances.

3. AMIs are used to store the current instance configuration.

4. Taking snapshots of non EBS backed instances are not possible but AMI of a non EBS backed instances can be created.


### Lambda

If we use any 3rd party library(Those libraries are also devolped by us only)


### Select Form in s3 bucket

Go to s3 bucket-any folder-upload any csv/json/parquet file.

With S3 Select you can extract records from a single CSV, JSON or Parquet file using SQL expressions. S3 Select supports GZIP and BZIP2 compressed files and server-side encrypted files. You can use the console to extract up to 40 MB of records from source files up to 128 MB; to work with larger files or more records, use the API.



## Properties in s3 bucket

### Versioning

keep multiple version of an object in the same bucket. You can enable it.

**Enable versioning**

latest version name, version ID, Last modified, size, Storage class

Also, use previous version, download it for backup file,critical file.


**Suspend versioning**

This suspends the creation of object versions for all operations but preserves any existing object versions.


### Server Access Loggging

set up access log records taht provide details about access request.

### Object-level logging

recoed object-level API activity using the CloudTrail data events feature(additional cost).

### Default encryption

Automatically encrypt objects when stored in Amazon s3 for security purpose.


### object lock

prevent objects from being deleted.

### Requester pays

The requester will pay for requests and data trasfer.



