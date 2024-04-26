# GLOBAL INFRASTUCTURE

## GLOBAL INFRASTUCTURE OVERVIEW

### What is the global infrastructure?

The AWS Global Infrastructure is **globally distributed hardware and datacenters** that are physically networked together to act as a one large resource for and end customer.

The AWS Global Infrastructure is made up of the following resources:
 - Lauched Regions
 - Availability Zones
 - Direct Connection Locations
 - Point of Presence
 - Local Zones
 - Warelenght Zones

## REGIONS

Regions are geographically distinct locations consisting of one or more Availability Zones.

Every region is physically isolated from and independent of every other region in terms of location, power, water supply.

*us-east-1 (Northern Virginia) is AWS First Region (2006)*

Each region generally has three Availability Zones (some new users are limited to two).

New services almost always become available first in US-EAST.

Not all AWS Services are available in all regions.

**All your billing information appears in US-EAST-1 (North Virginia).**

The cost of AWS Services vary per region.

When you choose a region the are four factors you need to consider:
 1. What Regulatory Compilance does your region meet?
 2. What is the cost of AWS Services in this region?
 3. What AWS Services are available in this region?
 4. What is the distance or latency to my ends-users?


## REGIONAL VS GLOBAL SERVICES

### Regional Services

AWS Scopes their AWS Management Console on a selected Region.

The will determine where an AWS service will be launched and what will be seen within an AWS Service's console.

You generally don't explicitly set the Region for a service at the time of creation.


### Global Services

Some AWS Services operate across multiple regions and the regions will be *fixed* to **Global** (Eg: Amazon S3, CloudFront, RouteS3, IAM)

For these services at the time of creation:
 - There is no concept of region (Eg: S3 IAM)
 - A single region must be explicitly chosen (Eg: S3Bucket)
 - A group of regions (geographic distribution) chosen (Eg: CloudFront Distribution)


### Availability Zones (AZs)

An Availability Zone (AZ) is a physical location made up of one or more datacenter.

A region will *generally* contain 3 or more Availability Zones (some cases only 2).

Datacenters within a region will be isolated from each other (different buildings). But they will be close enough to provide low-latency (10ms) using dedicated metro fiber fully redundant, they are within 100 km (60 miles). All traffic between AZs is encripted.

Its common practice to run workloads in at least 3 AZs to ensure services remain available in case one or two datacenters fail (**High Availability**).

AZs are represented by a Region Code, followed by a letter identifier (EG. us-east-1).

**A subnet is associated with an Availability Zone. You never choose the AZ when lauching resources, you choose the Subnet which is associated to the AZ.**

The us-east-1 region has 6 AZs (the most availability zones of any region).


## FAULT TOLERANCE

### What is a fault domain?

A fault domain is a section of network that is vulnerable to damage if a critical device or system fails. The purpose of a fault domain is that if a failure occurs it will not cascade outside that domain, limiting the damage possible.

You can have fault domains nested inside fault domains.

The scope of a fault domain could be:
 - Specific servers in a rack
 - An entire rack in a datacenter
 - An entire room in a datacenter
 - The entire data center building

Its up to the Cloud Service Provider (CSPs) to define the boundaries of a domain.

### What is a fault level?

A fault level is a collection of fault domains.

 - An AWS Region would be a Fault Level -> Fault level us-east-1 (region)
 - An Availability Zone would be a Fault Domain -> Fault domain us-east-1a (AZ) | Fault domain us-east-1b (AZ)

### Isolation 

Each Amazon Region is designed to be completely isolated from the other Amazon Regions. This achieves the greatest possible fault tolerance and stability.

Each Availability Zone is isolated, but the Availability Zones in a Region are connected through low-latency links. Each Availability Zone is designed as an **independent failure zone** (a failure zone is described as a Fault Domain).

### Failure zone

 - Availability Zones are physically separated within a typical metropolitan region and are located in risk lower flood plains.
 - Discrete and uninterruptible power supply (UPS) and onsite backup generation facilities.
 - Data centers located in different Availability Zones are designed to be supplied by independent substations to reduce the risk of an event on the power grid impacting more than one Availability Zone.
 - Availability Zones are all redundantly connected to multiple tier-1 trasit providers.

### Multi-AZ for High Availability

If an application is partitioned across AZs, companies are better isolated and protected from issues such as power outages, lightning strikes, tornadoes, earchquakes, and more.

## GLOBAL NETWORK

The AWS Global Network represent the **interconnections between AWS Global Infrastructure.**

Commonly referred to as "The Backbone of AWS", the are private expressways, where things can move very fast between datacenters.

**Edge Locations can acts as on and off ramps to the AWS Global Network**
 - AWS Global Accelerator
 - AWS Transfer Accelerations: Uses Edge Locations as an on-ramp to quickly reach AWS resources in other regions by traversing the fast AWS Global Network
 - AWS CloudFront (CDN): Uses Edge Locations as an off-ramp to provide the edge storage and compute near the end user.
 - AWS VPC Endpoints: Ensure your resources stay within the AWS Network and do no traverse over the Public Internet.

## POINTS OF PRESENCE (POP)

Points Of Presence (POP) is an intermediate location between an AWS Region and the end user, and this location could be a datacenter or a collection of hardware.

For AWS a Point Of Presence is a data center owned by AWS or a trusted partner that is utilized by AWS Services related for content delivery or expediated upload.

POP resources are:
 - Edge Locations
 - Regional Edge Caches

### Edge Locations

Edge Locations are datacenters that hold cached (copy) on the most popular files (eg: web pages, images, videos) so that the delivery of the distance to the end users is reduce.

### Regional Edge Locations

Regional Edge Locations are datacenters that hold much larger caches of less-popular files to reduce the full round trip and also reduce the cost of transfer fees.

### Tier 1

Tier 1 Network is a network that can reach every other network on the internet without purchasing IP transit or paying for peering. POPs live at the edge/intersection of two networks. 

AWS Availability Zones are all redundantly connected to multiple tier-1 transit providers.

### AWS Services using POPs

The following AWS Services **uses POPs for content delivery or expediated upload**

*Amazon CloudFront* is a **Content Delivery Network (CDN)** service that:
 - You point your website to CloudFront so that it will route request to nearest Edge Location cache.
 - Allows you to choose an origin (such a web-server or storage) that will be source of cached.
 - Caches the contents of what origin would returned to various Edges Locations around the world.

*Amazon S3 Transfer Aceleration*:
 - Allows you to generate a special URL that can be used by end users to upload files to the nearby Edge Location.
 - Once a file is uploaded to an Edge Location, it can move much faster within the AWS Network to reach S3.

*AWS Global Accelerator*:
 - Can find the optimal path from the end users to your web servers.
 - Global Accelerator are deployed within Edge Locations so you can send web traffic to and Edge Location instead of directly to your web-application.

## AWS DIRECT CONNECT

AWS Direct Connect is a **private/dedicated connection between your datacenter, office, co-location and AWS**. The benefits are:
 - Helps reduce network cost and increase bandwidth traffict throughtput (great for high traffic network).
 - Provides more consistent network experience than a typical internet-based connection (reliatable and secure).

A co-location (or carrier-hotel) is a data center where equipment, space, and bandwidth are available for rental to retail customers.

Direct connect has two very-fast connection options:
 1. Lower Bandwidth 50MBps - 500MBps
 2. Higher Bandwidth 1GBps - 10GBps

### Direct Connect Locations

Direct Connect Locations are trusted partnered datacenters that you can establish a **dedicated high speed, low latency connection from your on-premise to AWS**. You could use the AWS Direct Connect service to order and establish a connection.

## AWS LOCAL ZONES

Local Zones are datacenters located very close to a densely populated area to provide a single-digit millisecond low latency perfomance for that area (eg: 5ms). To use Local Zones you need to Opt-in.
 - Only specific AWS Services are availables.
 - Its a logical extension of a Region.
 - The identifies looks like this us-west-2-lax-1a (for Los Angeles, California which is a extension of us-west region)

The purpose of Local Zone is the support highly-demanding applications sensitive to latencies:
 - Media & Entretainment
 - Electronic Design Automation
 - Ad-Tech
 - Machine Learning

## AWS WAVELENGHT ZONES

AWS Wavelenght Zones allows for **edge-computing on 5G network**. Applications will have ultra low latency being as close as possible to users. AWS has partnered with various Telecom companies to utilize their 5G network.

You create a Subnet tied to a Wavelenght Zone and then you can launch Virual Machines (VMs) to the edge of the targeret 5G Network.

## DATA RESIDENCY

### What is Data Residency?

The physical or geographic location of where an organization or cloud resources reside.

### What is Compliance Boundaries?

A regulatory compliance (legal requirement) by a goverment or organization that describes where data and cloud resources are allowed to reside.

### What is Data Sovereignty?

Data Sovereignty is the jurisdictional control or legal authority that can be asserted over data because it's pyshical location it within jurisdictional boundaries.

For workloads that need to meet compliance boundaries strictly defining the data residency of data and cloud resources in AWS you can use:
 - AWS Outposts: Is a physical **rack of servers** that you can put in your datacenter. Your data will reside whenever the Outposts physical resides.
 - AWS Config: Is a **Policy as Code** services. You can create rules to continuous check AWS resources configuration. If they deviate from your expectations you are alerted or AWS Config can in some cases auto-remediates.
 - IAM Policies: Can be written explicitly deni access to specific AWS Regions. A Services Control Policy (SCP) are permissions applied organization wide.

## AWS FOR GOVERMENT

### What is Public Sector?

Public Sector includes public goods and govermental services such as (military, law enforcement, infrastructure, public transit, public education, health care, goverment itself).

AWS can be utilized by public sector or organizations developing cloud workloads for the public sector.

AWS achieves the by meeting regulatory compliance programs along with specific governance and security controls.

AWS has special regions for US regulation called GovCloud.

## GOVCLOUD 

Federal Risk and Authorization Management Program (FedRAMP) is a US government-wide program that provides a standardized approach to security assesment, authorization and continuous monitoring for cloud products and services.

### What is GovCloud?

A Cloud Service Provider (CSP) generally will offer an isolated region to run FedRAMP workloads.

AWS GovCloud Regions allows customers to host sensitive Controlled Unclassified Information and other types or regulated workloads.
 - GovCloud Regions are only operated by employees who are US citizens on US soil.
 - They are only accessible to US entities and root account holders who pass an screening process.

Customers can architect secure cloud solutions that comply with:
 - FedRAMP high baseline.
 - DOJ's Criminal Justice Information System (CJIS) Security Policy
 - US International Traffic in Arms Regulations (ITAR)
 - Export Administration Regulations (EAR)
 - Department of Defense (DoD) Cloud Computing Security Requirements Guide

## AWS CHINA

AWS China is the AWS cloud offerings in Mainland AWS China. AWS China is completely isolated *intentionally* from AWS Global to meet regulatory compliance for Mainland China. AWS China has it own domain at amazonaws.cn

 - In order to operate in AWS China Region you need have a Chinese Business Licence (ICP License).
 - Not all services are available in China.
 - Running in Mainland China means you would not need to traverse the The Great Firewall.

AWS has two regions in Mainland China:
 - Ningxia cn-northwest-1 operated by NSWCF
 - Beijing cn-north-1 operated by SINNET

## SUSTAINABILITY

Amazon co-founded the Climate Pledge to achieve Zero-Net Carbon Emissions by 2040 across all of Amazon Business (including AWS).

AWS Cloud's Sustainability goal are composed by three parts:
 1. Renewable Energy: AWS is working towards having their AWS Global Infrastructure powered by 100% renewable energy by 2025.
 2. Cloud Efficiency: AWS's infrastructure is 3.6 times more energy efficient than the median of US enterprise data centers surveyed.
 3. Water Stewarship: Direct evaporative technology to cool aws data centers. Use of non-potable water for cooling purposes (recycled water). On-site water threatment allows aws to remove scale-forming materials and reuse water for more cycles. Water efficency metrics to determine and monitor optimal water use for each AWS region.

AWS purchases and retires enviromental attributes to cover non-renewable energy for AWS Global Infrastructure.
 - Renewable Energy Credits (RECs)
 - Guarantees of Origin (GOs)

## GROUND STATION

AWS Ground Station is a fully managed service that lets you control satellite communications, process data, and scale your application without having to worry about building or managing your own ground station infrastructure.

To use Groud Station:
 - You schedule a Contact (select satellite, start and end time, ground location)
 - Use the AWS Ground Station EC2 AMI to lauch EC2 instances that will uplink and downlink data during the contact or receive downlinked data in an AWS S3 Bucket.

Use cases for Ground Station:
 - Wheather forecasting
 - Surface imaging
 - Communications
 - Video broadcast

## AWS OUTPOSTS

AWS Outposts is a fully managed service that offers the same AWS infrastructure, AWS Services, APIs and tools to virtually any datacenter, co-location space or on-premise facility for a truly consistent hybrid experience.

AWS Outpost is a rack of servers running AWS infrastructure on your physical location.