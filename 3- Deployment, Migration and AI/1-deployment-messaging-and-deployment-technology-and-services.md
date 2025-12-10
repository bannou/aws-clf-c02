
# AWS deployment tools

## AWS CodeCommit

- like a git repository
- source and versionning control

## AWS CodeBuild
- compile code
- runs tests
- package

## AWS CodeDeploy
- automates deployments

## AWS CodePipeline

- orchestrates pipelines


## AWS CloudShell and AWS CLI

AWS CloudShell is brower based shell with AWS CLI pre-installed

AWS CLI is a command tool used to manage AWS Services


    - aws s3 mb s3://mybucket-1212121212 (mb = make bucket)
    - aws s3 ls
    - aws s3 cp file.txt s3://mybucket-1212121212 (cp = copy)


## AWS  Could9

AWS Could9 is browser based cloud IDE with AWS CLI installed
JS, Python, C++ and Ruby

## Central Artifact Repository

AWS CodeArtifact is repository to make software packages available, both third-party and in-house

    artifact = documentation, compiled applications, deployable packages, libraries

# Decoupling application components

Tight coupling between components can bring the whole system down if one part fails

Decoupling components of an application are connected to each other but not dependent on each other

## AWS Simple Notification Service SNS

AWS SNS setup, operate and send notifications
- email
- sms


    - It's based on pub/sub publish and Subscribe methods through topics
    - A topic is an access point allowing subscribers to receive notifications

## Amazon Simple Queue Service SQS

- distributed message queuing systems
- enables decoupling between components
- messages are guaranteed to be processed at least once
- improves performance and scalability


    SQS is pull based - consumers pull from the topic

    - 2 implementations are offered STANDARD and FIFO queues
    - 2 Polling mechanisms offered SHORT and LONG pollings

### Standard Queues

- default type
- guarantee at least one copy is sent
- the order is best-effort wise

### FIFO Queues

- the order is guaranteed
- no duplicates

### Short polling

Short polling returns an immediate empty response (paid even empty)
 
### Long polling

Long pulling: the queue does not respond until a message is received (cost effective)


## AWS Simple Email Service SES

- a cloud based email service that allows sending richly formatted HTML
- send email in bulks
- track email opening

## Event Bridge

Configure event driven systems and define tasks run on predefined scheduled

- helps implement event-driven architecture
- setup rules based on EC2, CloudWatch or CloudTrail events
- rules launch actions
- the actions can target EC2, Lambda or SNS
- Scheduled events let us schedule an action on CRON bases

## Step functions

- used manage the logic of distributed workflow made of multiple small components
- build and run serverless applications as a series of steps
- the output of a step can the input of another step

## AWS CloudFormation

Deploying Infrastructure as code

- provision and manage infrastructure as code
- defines resources through Yaml/Json templates
- CloudFormation interprets the code and create the Cloudformation Stack
  - Free to use ! only the resources are to pay

      
    Demo: Create a CloudFormation resources file -> On CloudFormation, create new Stack -> upload the file -> and done 

## AWS Elastic BeanStalk

Deploys and scale web applications

- allows developers to focus on code only
- fastest way to deploy an app on AWS
- BeanStalk manages runtime environment (OS, patches, webapp platform, databases, S3, autoscaling groups, ..)
- supports tomcat, HTTP server / java, .NET, python, Ruby, NodeJs, go / tomcat, IIS, NGnix, Docker / monitoring / healthcheck ..


    Demo:
        1- Creates 2 custom roles associated with:
            - AWSElasticBeanstalkReadOnly 
            - AWSElasticBeanstalkEnhancedHealth & AWSElasticBeanstalkManagedUpdatesCustomerRolePolicy 
        2- On Elastic BeanStalk -> create application -> select PHP -> upload code -> done

## AWS X-ray to identify performance issues

- provides to end-to-end view of requests as they travel the application
- helps troubleshoot connectivity and performances issues