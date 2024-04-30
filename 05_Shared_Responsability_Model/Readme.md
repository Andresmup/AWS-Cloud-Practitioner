# SHARED RESPONSABILITY MODEL

The Shared Responsability Model is a cloud security framework that defines the security obligations of the customer versa the Cloud Service Provider (CSP).

Each CSP has their own variant of the Shared Responsability Model but they are all generally the same.

The type of cloud deployment model and/or the scope of cloud service category can result in specialized Shared Responsability Models.

## AWS SHARED RESPONSABILITY MODEL

The customer is responsible of:
 - Configuration of Managed Services or Third-Party Sotfware (Platforms, Applications, Identity and Access Management (IAM))
 - Configuration of Virtual Infrastructure and Systems (Operating System, Network, Firewall)
 - Security Configuration of Data (Client-side Data Encryption, Server-side encryption, Networking Traffic Protection, Customer Data)

AWS is responsible of:
 - Software (Compute, Storage, Database, Networking)
 - Hardware/Global Infrastructure (Region, Availability Zones, Edge Locations, Physical Security)

In resume:
 - Customer are responsible for Security **in** the Cloud (Data, Configuration). If you can configure or store it then (the customers) are responsable for it.
 - AWS is responsible for Security **of** the Cloud (Hardware, Operation of Managed Services, Global Infrastructure). If you can not configure it the CSP is responsable for it.

## TYPES OF CLOUD COMPUTING RESPONSABILITY

| Characteristic | On-Premise | Infrastructure as a Service | Platform as a Service | Software as a Service |
| ----- | ----- | ----- | ----- | ----- |
| Applications | Customer | Customer | Customer | AWS |
| Data | Customer | Customer | Customer | AWS |
| Runtime | Customer | Customer | AWS | AWS |
| Middleware | Customer | Customer | AWS | AWS |
| OS | Customer | Customer | AWS | AWS |
| Virtualization | Customer | AWS | AWS | AWS |
| Servers | Customer | AWS | AWS | AWS |
| Storage | Customer | AWS | AWS | AWS |
| Networking | Customer | AWS | AWS | AWS |

## AWS SHARED RESPONSABILITY MODEL - COMPUTE

Leet take a look at compute as a comparison example of the Shared Responsability Model

### Infrastructure as a Service (IaaS)

**Bare Metal**: EC2 Bare Metal Instance
 - Customer:
    - Host OS
    - Hypervisor
 - AWS
    - Physical Machine

**Virtual Machine**: Elastic Cloud Computing (EC2)
 - Customer:
    - The guest OS configuration
    - Container runtime
 - AWS
    - Physical Machine
    - Hypervisor
    - Host OS

**Container**: Elastic Container Service (ECS)
 - Customer:
    - Configuration of containers
    - Deployment of containers
    - Storage of containers
 - AWS
    - Container runtime
    - Hypervisor
    - Host OS

### Platform as a Service (PaaS)

**Managed Platform**: AWS Elastic Beanstalk
 - Customer:
    - Uploading your code
    - Some configuration enviroment
    - Deployment strategies
    - Configuration of associated services
 - AWS
    - Servers
    - OS
    - Networking
    - Storage
    - Security

### Software as a Service (SaaS)

**Content Collaboration**: Amazon WorkDocs
 - Customer:
    - Contents of documents
    - Management of files
    - Configuration of sharing access controls
 - AWS
    - Servers
    - OS
    - Networking
    - Storage
    - Security

### Function as a Service (FaaS)

**Functions**: Amazon Lambda
 - Customer:
    - Upload your code
 - AWS
    - Everything