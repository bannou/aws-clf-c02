# AWS Snow Family

    Data transfert solution = used to load data and physically transfert it to AWS

## Snowball

- a data transport box full of disks
- used to store 10 TB and more on it, and then being shipped to AWS

## Snowball Edge

- is the same as Snowball = physical device to be used when having 10 TB and more to migrate + a need of compute
  capabilities

## Snowmobile

- is a shipping container (dragged with a truck) full of disks used for 10 PB data or more

## Snowcone

- small and portable (under 5 lbs)
- military grade
- either 8 TB of HDD or 14 TB of SSD
- used migration with no reliable network

# Database migration tools

## AWS Database Migration Service (AWS DMS)

used to migrate database and analytics from to on-premise, EC2 or on RDS

## AWS Schema Conversion Tool (AWS SCT)

used to convert database schema to another type of database

    from Oracle to Aurora MySQL or from SQL Server to Aurora PostgrSQL

# AWS Transfer Family

- B2B file transfer solutions using protocols: SFTP, AS2 FTPS and FTP
- file can be stored (SFTP PUT) or loaded (SFTP GET) from S3 or EFS
- users can use existing tools like WinSCP, FileZilla, CyberDuck and OpenSSH

        DeepDive in Protocols

        | Protocol | Explaination                                |
        | -------  | ------------------------------------------- |
        |  SFTP    | Secure Shell uses SLL                       |
        |  AS2     | Applicable Statement uses  HTTP / HTTPS     |
        |  FTPS    | File Transfer Protocol over SSL             |
        |  FTP     | File Transfer Protocol (without encryption) |

# AWS DataSync

- is designed to securely transfer a large amount of data to S3, EFS and FSx.
- it enables High data throughput


    Use Cases:
  
    - migrate all data to AWS
    - data replication in AWS
    - Archive historical data in less expensive AWS Storage
    - support of hybrid or multi-cloud workflows

# AWS Application Discovery Service

It's a tool that discover an environment on-premise, gathers data and transfer it to AWS Migration Hub (tool to facilitate / track migration)

- for applications and databases, once ASD Agent installed on the server it does the job.
- for VMware, an agentless collector is installed as a virtual appliance.  

It collects:
  - Server inventory
  - Configuration Data
  - Operating system version 
  - Capacity utilization (CPU, RAM, Disk I/O, ...)
  - Inbound and Outbound network connections

# AWS Application Migration Service

It helps migration application from (physical server, virtual service running on VMware or Microsoft hyber-v)
- offers test running 
- automatic lift and shift migration approach (the application is taken as is)
- this service is free up to 90 days: you pay the target infrastructure, the application migration service free to use for 90 days.


    How to ?
      AWS replication agent needs to be installed on each application server, a continiuos replication happens, in secure way (encrypted), while tha application is still usable

# AWS Migration Hub

Is a central place to manage the migration of application and data to AWS

- is a central location to gather application and server inventory information
- helps you assess, plan and track migrations
- logically group servers together for migration
- can also suggest recommendation to remodel app, dockernize app to run in ECS
- can estimate cost of workload on EC2

  
    + is integrated with AWS Application Discovery Service
    + is integrated with AWS Application Migration Service
    + is integrated with AWS Database Migration Service