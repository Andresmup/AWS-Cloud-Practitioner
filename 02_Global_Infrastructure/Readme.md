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

Datacenters within a region will be isolated from each other (different buildings). But they will be close enough to provide low-latency (10ms).

Its common practice to run workloads in at least 3 AZs to ensure services remain available in case one or two datacenters fail (**High Availability**).

AZs are represented by a Region Code, followed by a letter identifier (EG. us-east-1)