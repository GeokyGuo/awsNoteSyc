s3 rds 邦迪az还是region
是否是高可用
遇见关键字tolet failure 选 spot instance

CloudFront – S3 as an Origin 这一块需要再看一下视频？？？

Aws local zone vs Edge locations
Is it okay to say local zones are an extension of edge locations as they both focus on bringing services closer to the end-user. With local zones allowing more services such ec2 instances and edge locations focusing on CDN and route53


Other Compute - Summary
• Docker: container technology to run applications
• ECS: run Docker containers on EC2 instances
• Fargate:
• Run Docker containers without provisioning the infrastructure
• Serverless offering (no EC2 instances)
• ECR: Private Docker Images Repository
• Lightsail: predictable & low pricing for simple application & DB stacks

• Batch: run batch jobs on AWS across managed EC2 instances（可以是spot instance）

Lambda Summary
• Lambda is Serverless, Function as a Service, seamless scaling, reactive
• Lambda Billing:
   By the time run x by the RAM provisioned
   By the number of invocations
• Language Support: many programming languages except (arbitrary) Docker
• Invocation time: up to 15 minutes
• Use cases:
    Create Thumbnails for images uploaded onto S3
    Run a Serverless cron job
• Amazon API Gateway：向外暴露的api，可以作为lambda的入口

 Serverless == FaaS (Function as a Service)
 s3 DynamoDB Fargate Lambda API Gateway


Deployment - Summary
• CloudFormation: (AWS only)
    Infrastructure as Code, works with almost all of AWS resources
    Repeat across Regions & Accounts
• Beanstalk: (AWS only)
    Platform as a Service (PaaS), limited to certain programming languages or Docker
    Deploy code consistently with a known architecture: ex, ALB + EC2 + RDS
• Systems Manager (hybrid): patch, configure and run commands at scale
    SSM Session Manager：一种可以登录ec2的方式
• OpsWorks (hybrid): managed Chef and Puppet in AWS（alternative to AWS SSM）

 Developer Services - Summary
• CodeCommit: Store code in private git repository (version controlled)
• CodeBuild: Build & test code in AWS（版本控制，build（测试、打包），deploy）
• CodeDeploy: (hybrid): deploy & upgrade any application onto servers
• CodePipeline: Orchestration of pipeline (from code to build to deploy)
• CodeArtifact: Store software packages / dependencies on AWS
• CodeStar: Unified view for allowing developers to do CICD and code
• Cloud9: Cloud IDE (Integrated Development Environment) with collab
• AWS CDK: Define your cloud infrastructure using a programming language（配合CloudFormation使用）

Global Applications in AWS - Summary
• Global DNS: Route 53
    Great to route users to the closest deployment with least latency
    Great for disaster recovery strategies
• Global Content Delivery Network (CDN): CloudFront
    Replicate part of your application to AWS Edge Locations – decrease latency
    Cache common requests – improved user experience and decreased latency
    与Shield和WAF集成在一起
• S3 Transfer Acceleration
    加速s3与【edge location】，需要再看一下
• AWS Global Accelerator
    客户到edge location走公网，【edge location】到其他服务走aws内网
• AWS Outposts
    Deploy Outposts Racks in your own Data Centers to extend AWS services
• AWS WaveLength
    Brings AWS services to the edge of the 5G networks
    Ultra-low latency applications
• AWS Local Zones
    Bring AWS resources (compute, database, storage, …) closer to your users
    Good for latency-sensitive applications
• Global Applications Architecture：
    Single Region, Single AZ
    Single Region, Multi AZ
    Multi Region, Active-Passive
    Multi Region, Active-Active

