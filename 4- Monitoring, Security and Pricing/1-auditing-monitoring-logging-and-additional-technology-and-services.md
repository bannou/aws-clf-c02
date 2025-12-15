# Metrics, Logs and Configurations

## Metrics

AWS services and apps publish metrics
- monitor workload health
- inform design decisions
- view charts
- automate actions triggering
    

    - CPU usage
    - newtwork usage
    - disk usage

## Logs

Logs are produced by any AWS service
- track actions
- helps investigation
    

    - VPC flow logs
    - EC2 instances logs
    - account activity logs
    - application logs

## Configurations

Resources settings or standards
- can be standardized across AWS account
- setting the appropriate configuration can help secure the resources
- PREVENTING action + attacks DETECTION
- configuration automation helps managing configuration at scale

# Amazon CloudWatch and CloudTrail

## CloudWatch
- provides visibility to cloud resources and applications
- track metrics in dashboards
- stores logs from many sources
- trigger events with CouldWatch alarms
- watch all the AWS ecosystem resources

    
    For EC2 instances, CloudWatch agent needs to be installed in the instance to track metrics (free memory, disk usage, custom app metrics, ..) 

## CloudTrail
- provides accountability for actions taken in the AWS account
- centralizes activity logs across regions in S3 bucket
- tracks exclusively Rest API calls in AWS account
- creates a trail of breadcrumbs for any action taken in the account

# Managing Many resources on AWS

## Tag

a Tag is a K/V (env: prod for example)
- any AWS resource can be tagged

## Systems Manager

- groups resources on AWS, on premises or on other cloud platforms
- allows taking actions on those groups
- view aggregated operational data on resource groups

### Parameter Store

helps securely store sensitive data

# Amazon Health Dashboard

Review which services are healthy, which not

- can set alarms
- can set automatic actions

## AWS Health Dashboard

view health check data in the screen

## AWS Health API

access programmatically the same data through Rest API

# Auditing on AWS

is the continuous act of monitoring passive configuration for security and best practices

What to audit ?
 
- data encryption
- public access
- secure CloudTrail
- protect credentials
- network security
- resource provisioning
 

    AWS Config is the main provider for all auditing services: 

    - contains a pre-defined list of recommendations or create custom rules.
    - detects non-compliant resources and alerts about it

## AWS Trusted Advisor

monitor best practices through a set of rules

- scans continuously all AWS ecosystem
- advise on performance, cost optimization, security, fault tolerance, ...
- free, paid for Business or Enterprise plans

## AWS Audit Manager

- centralize audit data from AWS Config and security services
- helps find the root cause of non-compliance
- provide pre-build auditing frameworks to meet standards like HIPAA, NIST Cyber-security, AWS Operational best practices
- generates reports

## AWS Well-Architected tool

- assess your workflows
- learn about best practices
- generate action plans.

# Amazon Connect

allows to create cloud based call center   

# Amazon Workspace

helps provisioning distance desktops for remote employees

# Amazon AppStream

converts applications to SaaS