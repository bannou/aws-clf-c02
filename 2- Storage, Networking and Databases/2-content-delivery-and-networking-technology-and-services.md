# AWS Global accelerator

It's like the express line crossing path all edge the known ways.

It uses edge location to get the best path to the original source.

Key features:

+ performance and available by redirecting traffic through highway speed
+ multi-region apps
+ single entry point through a static IP address
+ security: DDOS resilient + automatic rerouting

# AWS VPC (Virtual Private Cloud)

Is the user's private space in the AWS Cloud.

Key features:
- public and private subnets with routing table configuration. 
- securite group control inbound and outbound flow & ACL.

## Public subnets

- can be accessible from internet.
- each subnet must be associate to a routing table.
- internet gateway is the single entry point from/to internet.
- route tables for directing flow.

## Private subnets

Aimed for traffic staying within the VPC (or routed to on-premise via VPN or DirectConnect)

> How to secure a VPC ?
>
> Security group:
> 
>   - stateful  
>   - make decision of who entry and leave
>   - allows to define protocol Ip ranges and ports
>
> Network ACL:
> 
>   - stateless
>   - operates at subnet level
>   - allow / deny traffic depending on ip, port, protocol

# AWS Route 53 (<> DNS)

Is the equivalent of DNS inside of AWS ecosystem.

- traffic routing (geolocation routing, latency-based routing, weighted round-robin routing)
- health checks
- dns fail over
- scalability
- domain name registration
- private DNS names for VPC

# Hybrid models

Allows to connect op-premise datacenter with AWS VPC.

## AWS Direct Connect

It's a private connection from on premise to AWS (not over public internet)

- high-speed transfer
- reduced bandwidth costs
- reliable and private connection

## AWS VPN

It's an encrypted over public internet road from AWS to on-premise

### Site-to-site VPN

From on-premise to AWS. 

### Client VPN 

AWS from any location (individual remote access)