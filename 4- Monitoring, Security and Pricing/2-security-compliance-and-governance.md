#  Shared Responsibility Model

    AWS is responsible for securing infrastructure and software to manage it
            AWS => Security OF the cloud
  
    The customer is responsible for securing the resources he provision 
            Customer => Security IN the cloud

## Customer data

Lots a application data will flow through your apps. It's the customer responsibility to secure all that data. 

## Platform, Applications, Identity & Access Management IAM

- managing AWS users
- managing applicative users
- securing interconnections with other clouds or data center

## Operation System, Network and Firewall configuration

It's the user responsibility to make sure:  

- EC2 instances are up-to-date with OS
- VPC is well protected by firewalls
- users accessing the application have the needed authorizations only

## Encryption

Is a way scramble data, and you need a key to unscramble data

- Client-side before being sent
- Networking Traffic protection
- Server-side once stored


    Managed services can take off some responsabilities of the user

    => (EC2 + manually installed DB) vs RDS


# Principle of Least privileges

Designing Granular privileges is important in order to assign users ONLY the needed permissions 

## Identity & Access Management IAM

Helps to define who (users and applications) access what (resources)

### Root User

The only who creates / destroy AWS Account

### Multi-Factor Authentication MFA

Is a principle of validation the credentials using a device

### IAM Policies

Policies are used to describe a permission
- IAM Policy is applied to a user, or a group of users
- By default, an IAM user has no policies.


### IAM User Group

Is a group of IAM users

### IAM Role

Is an aggregation of policies and can be assumed by:
- IAM User
- IAM User Group
- Applications too


    IAM Role rotate automatically keys = NO LONG LIVING ACCESS KEYS BY DESIGN

## IAM Access Analyser

- identifies resources with external access to them
- validates IAM Policies
- helps generate IAM Policies to respect Principle of Least privileges

## IAM Policy Simulator

Test new IAM policies before granting them and putting them to work

# Keeping Secrets safe

## Encryption

Encryption allows to scramble data leaving it useless without key if intercepted

### Encryption at rest

Is one of the techniques to make data safe, we're going to focus on Encryption at rest

- S3 bucket: Let's consider Customer data stored on S3
    - S3 buckets content are Server-Side Encrypted by defaut (SSE-S3 Managed Keys)
    - Amazon Macie offers the possibility to scan S3 Bucket content for PII (Personal Identifiable Information)

- Elastic Block Store 
  - Encryption at rest is commonly used for EBS through keys from Key Management Service (KMS)

- RDS 
  - Encryption needs to be enabled on database creation.
  - In order to encrypt an existing database, a copy needs to be made with encryption enabled

### Encryption on transit

Encryption at transit secure data on the move.

- Amazon VPC 
  - Data transiting through VPC is by default encrypted.
- HTTPS / TLS 
  - Once on the internet, HTTPS needs to be used to benefit from Transport Layer Security (TLS)


    AWS Certificate Manager helps provistioning and deploying SSL/TLS certificates on private and public websites

## Parameter Store

Allows to keep secret and programmatically allows resources to access those credentials through IAM Role

## Secrets Manager

Like Parameter Store, allows to keep secret and programmatically allows resources to access those credentials through IAM Role.
Moreover, Secrets Manager guaranties <u>that the secrets are automatically rotated.</u>

# Network Security Service

## Network Access Control List (NACLs)

Provides a STATELESS access control applicable on VPC or Subnet level

    STATELESS means the rules are applied wether the traffic is from inside to outside or vice versa.

## Security Groups

Provides a STATEFUL access control applicable on VPC or Subnet level

    STATEFUL means the rules are applied for traffic initialed from outside to inside only.
    If the request is initiated from inside, the response is alwayas authorized.


## AWS Network Firewall

Allows defining complex rules to inspect traffic coming in the VPCs

## AWS Web Application Firewall (WAF)

AWS WAF allows to protect public endpoints (API Gateways / Application Load Balancer ALB) from common attacks (SQL injections, Cross-Site Scripting XSS, ...) 

## AWS Shield

Allows to particularly protect from Distributed Denial Of Service (DDOS) attacks.
- AWS Shield offers basic free protection against DDOS
- AWS Shield Advanced is a paid service giving access to 24/7 DDOS response team.


    AWS Firewall Manager centralizes access to the network protection service

    - Network Firewall
    - AWS Web Application Firewall (WAF)
    - AWS Shield

# Security HUB

Security is an High Order Component that gathers security finding from different services

- AWS Firewall Manager sends finding on unprotected resources or DDOS detection
- AWS GuardDuty tracks activity logs across AWS Account for malicious behaviour
- AWS Inspector inspects workloads for vulnerabilities and networks access
- AWS Macie scans S3 Bucket for sensitive information / PII
- AWS Systems Manager detects non compliant resources
- AWS Config detects non-compliant resources through detective guardrails
- AWS IAM Access analyser detects unprotected access and unused access
- AWS Health reports outages

# Responding to Security Events

These are some tools to be used regarding Security events

## AWS Trusted Advisor

Give advice and best practice suggestions.

## AWS GuardDuty

Collects logs and use ML to detect threats.

## AWS Detective

Helps to investigate security threats that already happening
- isolate the events
- helps evaluate damage

## AWS Inspector

Continuously scans workloads for software vulnerabilities and network exposure


## AWS Cloud Security

- latest security white papers
- guidance on security best practices

## AWS Cloud Blog

- stay up-to-date with innovation updates
- contextualize updates with thoughts from AWS Solution Architects and security experts

## AWS Marketplace

Find pre-build solutions from third party security vendors

# AWS Organizations

- service for governing Multiple Accounts
- can still consolidate costs and billing
- can use Config Rules to apply rules on an account or on organisation level (and thus inherited by all the accounts)
- can use Service Control Policies on an account or on organisation level (and thus inherited by all the accounts) 
  - in higher than IAM
  - can not be overridden
  - example: deny the use of EC2 in favor Serverless


    Creating multiple AWS accounts can ease organizing multiple team organisation

# AWS Control Tower

Helps automate multi-account management best practices config rules and Service Control Policies


# AWS Compliance

Depending on industry, sometimes compliance programs are required by the firm (like HIPAA, GDRP, FedRAMP, ...)

    AWS does the job on their end to implement these recommandations, but it does not mean that the customer solutions does

## AWS Artifact

Is a repository of compliance document that can be downloaded and communicated to the compliance artichiect or auditors

## Audit Manager

Automates assessments against frameworks to meet compliance standards

## Security Token Service

Helps to grant auditors temporary access to your resources


    NOT ALL AWS SERVICES ARE IN SCOPE FOR ALL COMPLIANCE PROGRAMS

    - KMS is not alligned with FIPS 140-2 level 3 -> CloudHSM doese (more expensive)
    - migrating data through public infra is not HIPAA compliante -> Snowball Edge is
