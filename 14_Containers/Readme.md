# CONTAINERS

VMs do not make best use of space. Apps are not isolated which can cause config conficts, security problems and resource hogging.

Containers allow you to run multiple apps which are virtually isolated from each other. Lauch new containers and configure OS dependencies per container.

Monolithic Architecture is one app which is responsible for everyhing. Functionality is tightly couple.

Microservice Architecture consist in multiple apps which are each responsible for one thing. Functionality is isolated and stateless.

## KUBERNETES

Kubernetes (K8) is an open-source container orchestation system for automating deployment, scaling and management of containers. Originally created by Google and now maintained by the Cloud Native Computing Foundation (CNCF).

The advantage of Kubernetes over Docker is the ability to run containers distributed across multiple VMs.

A unique component of Kubernetes are Pods. A pod is a group of one or more containers with shared storage, network resources and other shared settings.

Kubernetes is ideally for microservice architecture where the company has ten to hundred of services they need to manage.

## DOCKER

Docker is a set of Platform as a Service (PaaS) products that use OS-level virtualization to deliver software in packages called containers:
 - **Docker CLI**: CLI commands to download, upload, build, run and debug containers
 - **Dockerfile**: A configuration file on how to provision a container
 - **Docker Compose**: Is a tool and configuration file when working with multiple containers
 - **Docker Swarm**: An orchestation tool for managing deployed multi-containers architectures
 - **DockerHub**: A public online repository for containers published by the community for download

The Open Container Initiative (OCI) is an open governance structure for creating open industry standars around container formats and runtime. Docker established the OCI and now is maintained by the Linux Foundation.

## PODMAN, BUILDAH, SKOPEO

Podman is a container engine that is OCI-compilant and is a drop-in replacement for Docker
 - Podman is daemon-less where Docker uses a containered daemon
 - Podman allows you to create pods like K8, Docker does not have pods
 - Podman only replaces one part of Docker, need to be used allongside Buildah and Skopeo
     - Buildah is a tool used to build OCI images
     - Skopeo is a tool for moving containers images between different types of container storages

## CONTAINER SERVICES

Primary services that run containers:
 - **Elastic Container Services (ECS)**: No cold starts, self managed EC2 (always paying for the resources even if the are not running)
 - **AWS Fargate**: It has a cold start (but its more robust than Lambda), AWS-Managed EC2 (can scale to zero cost)
 - **Elastic Kubernets Service (EKS)**: Open source and run kubernetes. Avoid vendor lock-in
 - **AWS Lambda**: It has a cold start, only think about the code ideal for short running tasks. Can deploy custom containers

Provisioning and Deployment containers:
 - **Elastic Beanstalk (EB)**: ECS on training wheels (deploy ECS containers for you), it's a platform as a service
 - **App Runner**: Platform as a Service specifically for containers, AWS-managed 
 - **AWS Copilot CLI**: Is for build, release and operate production ready containerized applications on AWS App Runner, ECS and Fargate

Supporting Services for containers:
 - **Elastic Container Registry (ECR)**: Repository for containers
 - **X-Ray**: Analyze and debug between microservices
 - **Step functions**: Stitch together Lambdas and ECS tasks