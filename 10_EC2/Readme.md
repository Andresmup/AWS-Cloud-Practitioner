# EC2

Elastic Compute Cloud (EC2) is a highly configurable virtual server. EC2 is resizable compute capacity. It takes minutes to launch new instances. Anything and everything on AWS uses EC2 instances underneath.

Choose OS via Amazon Machine Image (AMI) -> Choose Instance Type -> Add Storage (EBS, EFS) -> Configure Service

## EC2 INSTANCE FAMILIES 

Instances families are different combinations of CPU, Memory, Storage and Networking capacity. 

Instances families allow you to choose the appropiate combination of capacity to meet your application's unique requirement.

Different instances families are different because of the varying hardware used to give them their unique propierties.

*Commonly "instances families" are called "instances types" but an instances type is the combination of family and size*

### General purpose

Balance of compute, memory and networking resources. Use case is web-servers and code repositories.

A1, T2, T3, T3a, T4g, M4, M5, M5a, M5n, M6zn, M6g, M6i, Mac

### Compute Optimized 

Ideal for compute bound applications that benefit from high performance processor. Use case is scientific modeling, dedicated gaming servers and ad servers engines.

C4, C5, Cba, C5n, C6g, C6gn

### Memory Optimized

Fast performance for workloads that process large dataset in memory. Use case is in-memory caches, in-memory databases, real-time big data analitycs.

R4, R5, R5a, R5b, X1, X1e, High Memory, Z1d

### Accelerated Optimized

Hardware accelerators and co-procesors. Use case is machine learning, computational finance, seismic analysis, speech recognition.

P2, P3, P4, G3, G4ad, G4dn, F1, Inf1, VT1

### Storage Optimized

High sequential read and right access to very large datasets on local storage. Use case is NoSQL, in memory or transactional databases, data warehouse.

I3, I3en, D2, D3, D3en, H1

## INSTANCE TYPE

A instance type is a particular instance family and size. Some common pattern is:
 - nano
 - micro
 - small
 - medium
 - large
 - xlarge
 - 2xlarge
 - 4xlarge
 - 8xlarge
 - ... (using power of 2)

There are exception to this pattern:
 - c6g.metal: is a bare metal machine
 - C5.9xlarge: is not a power of 2

EC2 instances usually double in price and key atributes from one type to the next.


## DEDICATED HOST 

Dedicated Host are single-tenant EC2 instances designed to let you Bring-Your-Own-License (BYOL) based on machine characteristics.

| Characteristic | Dedicated Instance | Dedicated Host |
| --- | --- | --- |
| Isolation | Instance isolation | Physical Server Isolation |
| Billing | Per instance billing (+2$ per region fee) | Per host billing |
| Visibility of physical characteristics | No visibles | **Sockets, cores host ID** |
| Affinity between a host and instance | No affinity | Consistency deploy to the same instances to the same physical server |
| Targeted instance placement | No control | Additional control over placement on physical server |
| Automatic instance placement | Yes | Yes |
| Add capacity using an allocation request | No | Yes |

## TENANCY

EC2 has three levels of tenancy.
 - **Dedicated host**: Your server lives "here" and you have control of the physical attributes. *The whole server*
 - **Dedicated instance**: Your server always lives "here". You server is on the same physicall machine as other customers but the actual slot is allways the same.
 - **Default**: Your instance live here until reboot. Every time it will be asignated to an avabilible slot on an available server.