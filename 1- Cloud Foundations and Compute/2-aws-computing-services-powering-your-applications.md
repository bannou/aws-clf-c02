# AWS Compute Services

- run applications without managing physical servers
- choose different types of computing power
- scale up and down easily

## Amazon EC2 (Elastic Computer Cloud)

Is IaaS AWS service to rent virtual machines on the cloud

### Different configs depending on the usage
- general purpose (balanced)
- compute optimized (more CPU) -> gaming servers
- memory optimized (more memory) -> big data
- storage optimized (more disk) -> databases
- accelerated computing (more GPU) -> machine learning, 3D rendering

### Different pricing models
- on-demand: pay what you use per hour/second with no commitment
- reserved instances: 75% discount for long-term commitment
- spot instances: cost effective maybe interrupted
- savings plans: flexible pricing with discounts

### Performance enhancing features
- autoscaling
- load balancing

> "Key pair" allows us to connect to the instance from local machine

## Amazon ECS (Elastic Container Service)

- allows running containerized apps
- works with EC2 and Fargate

## Amazon EKS (Elastic Kubernetes Service)

- allows running kubernetes apps
- automates scaling and deployments
- works with EC2 and Fargate

## Amazon Fargate

- no needs to manage any infrastructure (unlike EC2)
- cost efficient (pay per CPU usage)

## Amazon Lambda

- run code when events happens / triggered
- automatically scales depending on the demand
- supports many languages (go, nodejs, java)
- cost efficient (pay in milliseconds)