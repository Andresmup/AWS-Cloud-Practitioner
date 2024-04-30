# CLOUD CONCEPTS

Amazon calls their cloud provider service **Amazon Web Services**, commonly referred to just **AWS**. It is the most used CPS.

## WHAT IS CLOUD COMPUTING?

Cloud computing is the practice of using a network of remote servers hosted on the Internet to store, manage, and process data, rather than a local server or a personal computer.

On premise you have the responsability to:
 - Own the servers
 - Hire the IT people
 - Pay or rent the real-state
 - Take all the risk

On Cloud Providers, the provider is resposable for:
 - Own the servers
 - Hire the IT people
 - Pay or rent the real-state
 - You only are responsable for configuring the cloud services and code

## CLOUD HOSTING EVOLUTION

Dedicated Server
 - One physical machine dedicated to single a business
 - Runs a single web-app/site
 - Very expensive
 - High maintenance
 - High security

Virtual Private Server
- One physical machine dedicated to a single business
- The physical machine is virtualized into sub-machines
- Runs multiple web-apps/sites
- Better utilization and isolation of resources

Shared Hosting
 - One physical machine shared by hundred of businesses
 - Relies on most tenants under-utilizing their resources
 - Very cheap
 - Limited functionality
 - Poor isolation

Cloud Hosting
 - Multiple physical machines that act as one system
 - The system is abstracted into multiple cloud services
 - Flexible
 - Scalable
 - Secure
 - Cost-Effective
 - High Configurability


## WHAT IS A CLOUD SERVICE PROVIDER (CSP)?

A cloud service provider (CSP) is a company which:
 - Provide multiple Cloud Services
 - Those Cloud Services can be chained together to create cloud arquitectures
 - Those Cloud Services are accesible via Single Unified API
 - Those Cloud Services utilized metered billing based on usage
 - Those Cloud Services have rich monitoring built in
 - Those Cloud Services have an Infrastucture as a Service (IaaS) offering
 - Those Cloud Services offer automation via Infrastucture as a Service (IaC)

## COMMON CLOUD SERVICES

A cloud service provider can have hundreds of cloud services that are grouped into various types of services. The four most common types of cloud services for Infrastructure as a Service (IaaS) whould be:

 - Compute: A virtual computer that can run application, programs and code
 - Networking: A virtual network defining internet connections or network isolations between services or outbound of the internet
 - Storage: A virtual hardrive that can store files
 - Databases: A virtual database for storing reporting data or a database for general purpose web-application

AWS has over 200+ cloud services, the term ***Cloud Computing*** can be used to refer all categories, even through it has compute in the name.


### COMPUTING OFFERING

Dedicated
 - A physical server wholly utilized by a single customers
 - You have to guess your capacity, which make that you'll overpay for an underutilized server
 - You can't vertical scale, you need a manual migration
 - Replacing a server is very difficult
 - You are limited by your Host Operating System
 - Multiple apps can result in conflicts in resource sharing
 - You have a guarantee of security, privacy, and fully utility of underlying resources

VMs
 - You can run multiples Virtual Machines on one machine
 - Hypervisor is the software layer that lets you run the VMs
 - A physical server shared by multiples customers
 - You pay for a fraction of the server
 - You'll overpay for an underutilized Virtual Machine
 - You are limited by your Guest Operating System
 - Multiple apps on a single Virtual Machine can result in conflicts in resource sharing
 - Easy to export or import images for migration
 - Easy to vertical or horizontaly scale

Containers
 - A Virtual Machine running multiple containers
 - Docker Daemon is the name of the software layers that lets you run multiple containers
 - You can maximize the utilize of available capacity which is more cost-effective
 - Your containers share the same underlying OS so containers are more efficient that multiple VMs
 - Multiples apps can run side by side without being limited to the same OS requirements and will not cause conflicts during resource sharing

Functions
 - Known as Serverless Compute
 - Are managed VMs running managed containers
 - You upload a piece of code, choose the amount of memory and duration
 - Only responsable for code and data, nothing else
 - Very cost-effective, only pay for the time code is running, VMs only runs when there is code to be executed
 - Cold Starts is a side-effect of this setup


## TYPES OF CLOUD COMPUTING

Software as a Service (SaaS)
 - Oriented to Customers
 - A product that runs and managed by the service provider
 - Don't worry about how the service is maintained, it's just works and remains available

Platform as a Service (PaaS)
 - Oriented to Developers
 - Focus on the deployment and management of your apps
 - Don't worry about provisioning, configuring or understanding the hardware or OS

Infrasture as a Service (IaaS)
 - Oriented to Admins
 - The basic building blocks for Cloud IT
 - Provide access to networking features, computers and data storage space
 - Don't worry about IT staff, data centers and hardware


## CLOUD COMPUTING DEPLOYMENT MODELS

Public Cloud
 - Everything is build on the Cloud Service Provider
 - Also known as Cloud Native or Cloud First
 - Companies that are starting out today or are small enough to make the leap from VPS to a CSP

Private Cloud
 - Everything is build on the company's datacenters
 - Also known as On-Premise
 - The cloud could be OpenStack
 - Deployig resources on-premise, using virtualization and resource management tools
 - Organizations that cannot run on cloud due to strict regulatory compilance or sheer size of their organization

Hybrid
 - Using both On-Premise and a Cloud Service Provider
 - Organizations that started with their own datacenter, can't fully move to the cloud due to effort of migration or security compliance

Cross Cloud
 - Using Multiple Cloud Providers
 - Also known as Multi-Cloud