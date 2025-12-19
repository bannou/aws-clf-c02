# AWS databases

Different types of databases are available in AWS.

## Relation databases

Are relational databases
- Amazon RDS (Relational Database Service)

## NoSQL databases

Are K/V databases 
- Amazon DynamoDB

## In-Memory databases

In-Memory databases stores data in RAM
- Amazon ElastiCache 
- Amazon MemoryDB (for Redis)

## Graph databases

- Amazon Neptune
> Fraud detection

# AWS DMS (Database Migration Service)

AWS DMS helps moving data to AWS from on-premise or other cloud providers

- simple to use
- can handle various data sources
- minimal downtime (source DB stays up during transfer)
- reliable
- database consolidation (multiple databases into one)

# AWS Schema Conversion Tool (SCT)

SCT converts schemas from source db to AWS db compatible schema.
- it helps converting database code like stored procedures, views and functions.
- it handles incompatible datatypes as well as features

## Amazon DynamoDB

Is a K/V and Document Database

+ performance at scale (single digit millisecond response time)
+ fully managed
+ built-in security (data encrypted at-rest and in-transit)
+ backup and restore

## Amazon MemoryDB for Redis

Is a fully managed, memory db, fully compatible with Redis.

- it stores memory in RAM
- automatically replicated in different AZs
- high performance