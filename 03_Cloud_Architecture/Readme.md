# CLOUD ARCHITECTURE

## TERMINOLOGIES

### What is a Solution Architect?

A role in a technical organization that architects a technincal solution using multiple systems via researching, documentation, experimentation.

A solutions architect needs to always considers the following business factors:
 - Security: How secure is the solution?
 - Cost: How much is this going to cost?

### What it a Cloud Architect?

A Solution Architect that is focused solely on architecting technical solutions using cloud services.

A cloud architect need to understand the following terms and factor them into their designed architectured based on the business requirements.
 - Availability: Your ability to ensure that services remains available, eg: Highly Availability (HA).
 - Scalability: Your ability to grow rapidly or unimpeded.
 - Elasticity: Your ability to shrink and grow to meet the demand.
 - Fault tolerance: Your ability to prevent a failure.
 - Disaster recovery: Your ability to recover from a failure, eg: Highly Durable (DR).

## HIGH AVAILABILITY

Your ability for your service to remain available by ensuring the is **no single point of failure** and/or ensure a certain level of perfomance.

Running your workload across multiple Availability Zones (AZ) ensures that if 1 or 2 AZs become unavailable your service / applications remains available.

### Elastic Load Balancer

A load balancer allows you to evenly distribute traffic to multiple servers in one or more datacenter. If a datacenter or server becomes unavailable (unhealthy) the load balancer will route the traffic to only available datacenters with servers.

## HIGH SCALABILITY

The ability to increase your capacity based on the increasing demand of traffic, memory and computing power.
 - **Vertical Scaling:** Scaling up, upgrade to a bigger server.
 - **Horizontal Scaling:** Scaling out, add more servers of the same size.

## HIGH ELASTICITY

The ability to **automatically** increase your capacity based on the increasing demand of traffic, memory and computing power.
 - **Horizontal Scaling:**
    - Scaling out: Add more servers of the same size.
    - Scaling in: Removing underutilized servers of the same size.

*Vertical scaling in generally hard for traditional architecture so you'll usually only see horizontal scaling describe with Elasticity*

### Auto Scaling Group (ASG)

Auto Scaling Group is a AWS feature that will automatically add or remove servers based on scaling rules you define based on metrics.

## HIGHLY FAULT TOLERANT

Your ability for your service to ensure that there in no single point of failure. Preventing the chance of failure.

Fail-over is when you have a plan to shift traffic to a redundant system in case the primary system fails.

A common example is having a copy (secondary) of your database where all ongoing changes are synced. The secondary system is not in use until a fail over occurs and it becomes the primary database.

### RDS Multi-AZ

RDS Multi-AZ is when you run a duplicated standby database in another Availability Zone in case your primary database fails.

## HIGH DURABILITY

Your ability to recover from a disaster and to prevent the loss of Data Solutions that recover from a disaster in known as Disaster Recovery (DR).
 - Do you have a back up?
 - How fast can you restore that backup?
 - Does your backup still works?
 - How do you unsure current live data is not corrupt?

### CloudEndure Disaster Recovery

Is a service that continously replicates your machine into low-cost staging area in your target aws account and preffered region, enabling fast and reliable recovery in case of IT data center failures.

### Business Continuity Plan (BCP)

A business continuity plan (BCP) is a document that outlines how a business will continue operating during an unplanned disruption in services.

**Recovery Point Objective (RPO)** is the maximun acceptable amount of data loss after an unplanned data-loss incident, expressed as an ammount of time. *How much data are you willing to lose?*

**Recovery Time Objective (RTO)** is the maximum amount of downtime your business can tolerate without incurring a financial significant loss. *How much data are you willing to go down?*

### Recovery Point Objective (RTO)

Recovery Time Objective (RTO) is the maximum acceptable delay between the interruption of service and restoration of service. This objective determines what is considered an acceptable time window when service is unavailable and is defined by the organization.

### Recovery Point Objective (RPO)

Recovery Point Objective (RPO) is the maximum acceptable amount of time since the last data recovery point. This objective determines what is considered an acceptable loss of data between the last recovery poing and the interruption of service and is defined by the organization.

### Disaster Recovery Options

The are multiple options for recovery that trade cost vs time to recover, going from slowest to fastest:
 - Backup & Restore *(RPO/RTO Hours)*: You backup your data and restore it to the new infrastructure.
    - Lower priority uses cases
    - Restore data after event
    - Deploy resources after event
    - Cost $
 - Pilot Light *(RPO/RTO 10 mins)*: Data is replicated to another region with the minimal services running
    - Less stringent RPO & RTO
    - Core services
    - Start & and scale resources after event
    - Cost $$
 - Warm Stanby *(RPO/RTO minutes)*: Scaled down copy of your infrastructure running ready to scale up
    - Business Critical Service
    - Scale resources after event
    - Cost $$$
 - Multi-site active/active *(RPO/RTO real-time)*: Scaled up copy of your infrastructure in another region
    - Zero downtime
    - Near zero loss
    - Mission critical services
    - Cost $$$$