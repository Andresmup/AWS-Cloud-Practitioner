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
