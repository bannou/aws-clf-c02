# Types of Cloud Services

## IaaS: Infrastructure as a Service

Businesses rent computing power storage

networking + storage + servers + virtualization

## PaaS: Platform as a Service

Removes from the user the need to manage service

networking + storage + servers + virtualization + OS + middleware + runtime

## SaaS: Software as a Service

User uses the app only !

networking + storage + servers + virtualization + OS + middleware + runtime + Application + Data

# Cloud Computing

- computing power
- storage: block storage, object storage, ..
- network : load balancing, DNS, connectivity, ..
- applications: web applications, 

> Access cloud computing without caring on physical matters

+ on-demand access
+ access from everywhere
+ shared resources
+ scalability
+ pay-as-you-use

# Shared responsibility model

The responsibility is shared between AWS and the user in terms of service and managements

The responsibility differ by the service

## EC2

User's perimeter                application + data
AWS's  perimeter                infrastructure, network, virtualization

## Database

User's perimeter                manage users passwords
AWS's  perimeter                patching the system, backing, ...

## Lamba

User's perimeter                write the code, configure the lambda
AWS's  perimeter                manages the scalability

# AZ and regions

## AZ
AZ is unit having the same cooling and electricity. 
Last counted, 114 AZs exists

> eu-west-3a
> eu-west-3b
> eu-west-3c

## Region
Region is composed of multiple AZs
Last counted, 36 regions exists

> eu-west-3 (Paris) 

    If AZ fails, the traffic is moved to other AZs. If region does, the traffic is moved to another one.

# Edge locations

Edge locations are located outside the regions.
They serve like a cache.
It's meant to deliver data from the nearest edge to avoid heavy buffering.

## CloudFront

- distributes content through a network of edge locations worldwide
- it caches frequently accessed data.
- enhance scalability and security.

## Global accelerator

- finds the best locations to fetch data from through the AWS global network
- provides static IP and rapid failover for resilient application delivery