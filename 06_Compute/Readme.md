# COMPUTE

# COMPUTING SERVICES

**Elastic Compute Cloud (EC2) allows you to lauch Virtual Machines (VM)**

What is a Virtual Machine?
 - A VM is an emulation of a physical computer using software.
 - Server Virtualization allows you to easily create, copy, resize or migrate your server.
 - Multiple VMs can run on the same physical server so you can share the cost with other customers.
 - When a Virtual Machine is lauch its call *instance*

An Amazon Machine Image (AMI) is a predefined configuration for a Virtual Machine.

EC2 is highly configurable server when you can choose AMI that affect options such as:
 - The amount of CPUs
 - The amount of Memory (RAM)
 - The amount of network bandwidth 
 - The Operation System (OS) (eg: Amazon linux 2, ubuntu, microsoft)
 - Attach multiple virtual machine hard-drives for storage (eg: Elastic Blocks Store EBS)

EC2 is also considered the backbone of AWS because the majority of AWS services are using EC2 as their underlying (eg: S3, RDS, DynamoDB, Lambdas)

## VMs, CONTAINERS AND SERVERLESS

### Virtual Machine

An emulation of a physical computer using software
 - **AmazonLightSail**: Is the managed virtual server service. Is is the friendly version of EC2 Virtual Machines. *When you need to lauch a Linux or Windows server but you don't have much AWS knowledge*

### Containers

Virtualizing an Operation System (OS) to run multiple workloads on a single Operation System (OS) to run multiple workloads on a single OS instance. Containers are generally used in micro-services architecture.
 - **Elastic Container Registry (ECR)**: Is a repository for container images. In order to lauch a containers you need an image. An image just mean a saved copy. A repository just means a storage that has version control.
 - **Elastic Container Services (ECS)**: Is a container orchestation service that support Docker containers. Lauch a cluster of server(s) on EC2 instance with Docker installed. With ECS you have to keep a EC2 server running even if you have no container running. *When you need Docker as a Service, or you need to run containers*
 - **ECS Fargate**: Is serverless orchestation container service. It is the same as ECS except you pay-on-demand per running container. AWS manages the underlying server, so you don't have to scale or upgrade the EC2 server.
 - **Elastic Kubernetes Service (EKS)**: Is a fully managed Kubernetes service. Kubernetes (K8) is an open-source orchestation software that was created by Google and is generally the standard for managing microservices. *When you need Kubernetes as a Service*

### Serverless

When the underlying server is managed by AWS. You don't worry or configure servers.

 - **AWS Lambda**: Is a serverless functions service. You can run code without provisioning or managing servers. You upload small pieces of code, choose much memory and how long function is allowed to run before timing out. You are charged based on the runtime of the serverless funtion rounded to the nearest 100ms.

## HIGH PERFOMANCE COMPUTER (HPC)

What is High Performance Computer?
 - A cluster of hundreds of thousands of servers with fast connections between each of them with the purpose of boosting compute capacity.
 - When you need a supercomputer to perform computational problems to large to run on standards computers or would take to long.

The Nitro System is a combination of dedicated hardware and lightweight hypervisor enabling faster innovation and enhance security. All new EC2 instances types uses the Nytro System.
 - Nitro Cards: Specialized cards for VPC, EBS, instance storage and controlled card.
 - Nitro Security Chips: Integrated into motherboards. Protects hardware resources.
 - Nitro Hypervisor: Lightweight hypervisor Memory and CPU allocation Bare Metal-like performance.

**Bare Metal Instance** is a EC2 instance that have no hypervisor so you can run workloads directly on the hardware for maximum performance and control. The M5 and R5 EC2 instances run bare metal.

**Bottlerocket** is a Linux-based open-source operation system that is purpose-built by AWS for running containers on Virtual Machines or bare metal hosts.

**AWS ParallelCluster** is an AWS-supported open source cluster management tool that makes it easy for you to deploy and manage High Perfomance Computing (HPC) cluster on AWS.

## EDGE AND HYBRID SYSTEM

Edge Computing is when you push your computing workloads outside of your networks to run close to the destination location. (eg: pushing computing to run on phones, IoT devices, or external services not within your cloud network).

Hybrid Computing is when you are able to run workloads on both your on-premise datacenter and AWS Virtual Private Cloud (VPC)

Some services related to this are:
 - **AWS Outpost**: Is a physical rack of servers that you can put into your datacenter. AWS outpost allows you to use AWS API and Services such as EC2 right in your datacenter.
 - **AWS Wavelenght**: Allows you to build and lauch your application in a telecom datacenter. By doing this your applications have ultra-low latency since they will be pushed over the 5G Network and be closest as possible to the end user.
 - **VMWare Cloud on AWS**: Allows you to manage on-premise virtual machines using VMWare as EC2 instances. The data-center must being using VMWare for Virtualization.
 - **AWS Local Zones**: Are edge datacenters located outside of an AWS region so you can use AWS closer to end destination. *When you need faster computing, storage and databases in populated areas outside of an AWS Region*

## COST AND CAPACITY MANAGEMENT

Cost management is *How do we save money?* while Capacity Management is *How do we meet the demand of traffic and usages tbough adding or upgrading servers?*

Some services/options related to this are:
 - **EC2 Spot Instance, Reserved Instance and Saving Plans**: Ways to save on computing, by paying up in full or partially, by committing to yearly/multi-year contracts or by being flexible about availability and interruption to compute services.
 - **AWS Batch**: Plans, schedules and executes your batch computing workloads across the full range of AWS compute services, can utilize Spot Instances to save money.
 - **AWS Computer Optimizer**: Suggest how to reduce cost and improve perfomance by using machine learning to analyze your previous usage history.
 - **EC2 Autoscaling Groups (ASGs)**: Automatically adds or remove EC2 servers to meet the current demand of traffic. Will save you money and meet capacity since you only run the amount of servers you need.
 - **Elastic Load Balancer (ELB)**: Distribute traffic to multiple instance, can re-route traffic from unhealthy instances to healthy instances. Can route traffic to EC2 instances running in different Availability Zones.
 - **AWS Elastic Beanstalk (EB)**: Is for easily deploying web-applications without developers having to worry about setting up and understanding the underlying AWS Services (similar to Heroku).