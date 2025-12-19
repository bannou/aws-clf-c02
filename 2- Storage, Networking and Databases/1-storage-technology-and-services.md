# EC2 storage

## Amazon EBS (Elastic Block System)

- block level storage
- durable storage spaces
- directly attached to EC2

Key features:
- persistent storage
- highly available <> automatically replicated on its AZ
- scalable file systems
- Encrypted
- Snapshots

incremental snapshots

### Types of EBS

#### SSD (Solid State Drive)

Used for high IOPS

##### General SSD

- gp3, gp2
- muti-attached not supported

##### Provisioned IOPS SSD

- io2, io1, io2 block express
- muti-attached supported

#### HDD

Used for high Throughput

##### Throughput optimized

Useful for big data

##### Cold HDD

Lowest storage cost

### Snapshots

Capturing the perfect state of a volume

- incremental: saves only the changes from last snapshot
- cross-region Replication
- share or sell with other accounts

## Amazon EFS (Elastic File System)

Is scalable File Storage solution for EC2 (and other AWS solutions)

- fully managed
- scalable file systems
- maintain concurrency (access from many EC2)

## Amazon Instance stores (<> RAM)

Are temporary storage blocks directly attached to the EC2

- high I/O performance
- volatile storage spaces
- at no additional cost ! (included in the EC2 pricing)

# Amazon S3 (Simple Storage Service)

Composed of container/buckets containing objects = data + metadata

- durable
- scalable
- security (bucket policies & ACL on buckets)
- versatility (not only stores documents, can store images, videos, backups, ...)

## Amazon S3 Storage Classes

Storage classes are options of how to store the data in S3

### S3 Standard

Usefully for frequently accessed data

- high throughput
- low latency

### S3 Intelligent-tiering

Perfect with impredictable access frequency

- moves data automatically between access tiers 
- savings in cost without performance impact

### S3 Standard-Infrequent access

Usefully for less frequent accessed data, but still needs to be rapid when needed

### S3 One Zone-Infrequent access

Stores data in one AZ only
- less durable than multi AZs classes
- less expensive 

> Ideal for secondary backups & data can be reconstituable

### S3 Glacier Instant Retrieval

Archive storage for non frequently used data with rapid access

> Fastest archive data

### S3 Glacier flexible retrieval

Archive storage for data used 1 to 2 times the year with non immediate access.

### S3 Glacier Deep Archive

For long term storage (10 - 15 years) with very slow access time.

> Useful for regulatory needs of storing data up to 15 years



    S3 Buckets
    - aws bucket's name should be globally unique
    - by default, the buckets are closed to public
    - versions help recover a lost previous version

## Amazon FSx

Solution for specific storage needs for Windows systems.

## Amazon EDR (Elastic Disaster Recovery)

- ensures business continues
- minimize downtime and data loss
- offers swift recovery times

## AWS Storage Gateway

Allows data to be transported from the premises to AWS.

AWS storage gateway helps in:
- data backup
- disaster Recovery (from AWS to on-premise)
- data processing in AWS

Multiple types of Gateways exist.

### S3 File Gateway

Keep the data in cloud-native formats.

### Volume Gateway

Provides block storage volumes:
- stored volumes (entier datasets)
- cached Volumes (frequently accessed)

### Tape Gateway

Ideal for archiving storage.

### FSx File Gateway

Designed to extend on-premise Windows FS.

# AWS Backup

Service that centrally manages backup in AWS.

It allows to store items like:
- Elastic compute cloud instances
- Elastic block store volumes
- Relational DB services
- DynamoDB tables
- Elastic File System File Systems
- FSx File Systems
- Storage Gateway volumes

Key features:
+ Centralized backup management
+ Automated backups
+ Encryption & Data
+ Available cross-regions and cross-accounts