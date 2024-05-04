# EC2 PRICING MODELS

The are 5 different ways to for EC2 (Virtual Machines)
 - **On-demand**: *Least commitment*
    - Low cost and flexible
    - Only pay per hour or the second
    - Short-term, spiky, unpredictable workloads
    - Cannot be interrupted
    - Ideal for first-time apps
 - **Reserved**: (up to 75% of) *Best long term*
    - Steady state or predictable usage
    - Commit to EC2 over 1 a 3 year term
    - Can resell unused reserved instances 
 - **Spot**: (up to 90% off) *Biggest savings*
    - Request spare computing capacity
    - Flexible start and end times
    - Can handle interruptions (server randomly stopping and starting)
    - Ideal for non-critical backgroud jobs
 - **Dedicated**: *Most expensive*
    - Dedicated servers
    - Can be on-demand, reserved or spot
    - When you need a guarante of isolated hardware (enterprise requirements)

AWS saving plans is another way to save but can be used for than just EC2

## ON-DEMAND

On-demand is a Pay-As-You-Go (PAWG) model, where you consume compute and the you pay.

When you launch and EC2 instance it is by default using On-Demand pricing

On-Demand has no up-front payment and no long-term commitment. You are charged by the second (minimum of 60 seconds) or the hour.
 - **Per second**: For Linux, Windows, Windows with SQL Enterprise, Windows with SQL standard and Windows with SQL Web Instances that do not have a separate hourly charge.
 - **Per-hour**: Full hour for all the other instances types.

When looking up pricing it will always show EC2 pricing is the hourly rate.

On-Demand is for applications where the workload is for short-term, spiky and unpredictable. When you have a new app for development or you want to run experiment.

## RESERVED INSTANCES (RI)

Designed for applications that have a steady-state, predictable usage or required reserved capacity. Reduce payment is based on (Term * Class offering * RI attibutes * Payment option)

### Term

The longer the term the greater the savings.

You commit to a 1 year or 3 year contract. Reserved instances do not renew automatically. When they expire your instance will use On-Demand with no interruption to service.

### Class

The less flexible the greater the savings
 - **Standard**: Up to 75% reduced pricing compared to on-demand. You can modify RI attibutes.
 - **Convertible**: Up to 54% reduced pricing compared to on-demand. You can exchange RI based on RI attibutes if greater or equal in value.

### Payment Options

The greater upfront the greater the savings
 - **All upfront**: Full payment is made at the start of the term
 - **Partial upfront**: A portion of the cost must be paid upfront and the remaining hours in the term are billed at the discounted hourly rate
 - **No upfront**: You are billed a discounted hourly rate for every hour within the term, regardless of whether the Reserved Instances is being used

RI can be shared between multiple account within an AWS organization.

Unused RIs can be sold in the Reserved Instance Marketplace

### RI Attibutes

RI Attributes (aka Instances Attributes) are limited based on Class Offering and can affect the final price of an RI instance. There are 4 RI attibuted.
 - **Instances Types**: For example m4.large. This is composed of the instance family (m4) and the size (large)
 - **Region**: The Region in which the Reserved Instance is purchased
 - **Tenancy**: Wheater your instance runs on shared (default) or single-tenant (dedicated) hardware
 - **Platform**: The Operating system (eg: Windows Linux/Unix)

### Regional or Zonal RI

When you purchase a RI, you determine the scope of the Reserved Instance. The scope does not affect the price.

| Regional RI: purchase for a Region | Zonal RI: purchase for an Availability Zone |
| --- | --- |
| Does not reserved capacity (no guarantee of those servers will be available) | Reserves capacity in the specified Availability Zone |
| RI discount applies to instance usage in any AZ in the Region | RI discount applies to instances in the selected AZ (No AZ Flexibility) |
| RI discount applies to instance usage within the instance family, regardless of size. Only supported on Amazon Linux/Unix Reserved Instances with defaul tenancy | No instance size flexibility. RI discounts applies to instance usage for the specified  instance type and size only |
| You can queue purchases for regional RI | You can't queue purchases for zonal RI |

### RI Limits

There is a limit to the number of Reserved Instances that you can purchase per month.

Per month you can purchase:
 - 20 Regional Reserved Instances per Region
 - 20 Zonal Reserved Instances per AZ

#### Regional Limits

You cannot exceed your running On-Demand Instances limit by purchasing regional Reserved Instances. The default On-Demand Instances limit is 20

Before purchasing RI ensure your On-Demand limit is equal or greater than your RI you intend to purchase.

#### Zonal Limits

You can exceed your running On-Demand Instances limit by purchasing zonal Reserved Instances.

If you already have 20 running On-Demand Instances and you purchase 20 zonal Reserved Instances, you can launch a further 20 On-Demand Instances that match the specifications of your Zonal Reserved Instances.

### Capacity Reservation

EC2 Instances are backed by different kind of hardware, and so there is a finite amount of servers available within an Availability Zone per instance type or family.

*You go to launch a specific type of EC2 instance but AWS has ran out of that server*

Capacity Reservation is a service of EC2 that allows you to request a reserve of EC2 instance type for a specific Region and AZ.

The reserved capacity is charged at the selected instance type's On-Demand rate whethet an instance is running in it or not.

You can also use your regional reserved instances with your Capacity Reservations to benefit from billing discounts

### Standard vs Convertible RI

There are some key difference between Standard and Covertible

**Standard RI**
 - RI attibutes can be modified:
    - Change the AZ within the same Region
    - Change the scope of the Zonal RI to Regional RI or vice versa
    - Change the instance size (Linux/Unix only, default tenancy)
    - Change network from EC2-Classic to VPC and visa-versa
 - Chan't be exchange
 - Can be bought or sold in the RI Marketplace

**Convertible RI**
 - RI attibutes can't be modified (you perform an exchange)
 - Can be exchange during the term for another Convertible RI with new RI attributes, including:
    - instance family
    - instance type
    - platform
    - scope
    - tenancy
 - Can't be bought or sold in the RI Marketplace (just dealing with AWS directly)

### RI Marketplace

EC2 Reserved Instance Marketplace allows you to sell your unused Standard RI to recoup your RI spend or RI you do not intend or cannot use.

Reserved Instances can be sold after they have been active for at least 30 and once AWS has received the upfront payment (if applicable).

You must have a US bank account to sell Reserved Instance on the Reserved Instance Marketplace.

The must be at least one month remaining in the term of the RI you are listing.

You will retain the pricing and capacity benefit of your reservation until it's sold and the transaction is complete.

Your company name (and the address upon request) will be shared with the buyer for tax purposes.

A seller can set only the upfront pricce for a RI. The usage price and other configuration (eg: instance type, availability zone, platform) will remain the same as when the RI was initially purchased.

The term lenght will be rounded down to the nearest month. (eg RI with 9m 15d remaining will be rounded to 9m)

You can sell up to 20000 in RI per year. 

RI in the GovCloud region can not be sold on the RI marketplace.

## SPOT INSTANCES

AWS has unused compute capacity that they want to maximize the utility of their idle servers.

Spot Instances provide a discount of 90% compared to On-Demand pricing. Spot Instances can be terminated if the computing capacity is needed by other on-demand customer.

Designed for applications that have flexible start and end times or appications that are only feasible at very low computer cost
 - Load balancing workloads
 - Flexible workloads
 - Big data workloads

Termmination Conditions:
 - Instances can be terminated by AWS at any time
 - If your instances is terminated by AWS, you don't get charged for a partial hour of usage
 - If you terminate an instance you will still be charged for any hour that it ran

AWS Batch is an easy and convenient way to use Spot Pricing

## DEDICATED INSTANCES

Dedicated Instances is designed to meet regulatory requirements. When you have strict server-bound licensing that won't support multi-tenancy or cloud deployments you use Dedicated Host

Multi-tenant: When multiple customers are running worloads in the same hardware. Virtual Isolation is what separate customers.

Single-tenant: When a single customer has dedicated hardware. Physical Isolation is what separates customers.

Choose you tenancy when you launch your EC2

Dedicated can be offered for:
 - On-demand
 - Reserved (up to 60% savings)
 - Spot (up to 90% savings)

Enterprises and Large Organizations may have concers or obligations about against sharing the same hardware with other AWS customer.

## SAVING PLANS

Saving plans offer you the similar discounts as Reserved Instances but simplifies the purchasing process.

There are 3 types of Saving Plans:
 - Compute Saving Plans
 - EC2 Instances Saving Plans
 - SageMaker Sagving Plans

You choose the following Payment options:
 - All upfront
 - Partial upfront
 - No upfront

You choose an hourly commitment

### Compute

Compute Saving Plans provide the most flexibility and help to reduce your cost by up to 66%. These plans automatically apply to EC2 instances usage, AWS Fargate, and AWS Lambda service usage regardless of instance family, size, AZ, Region, OR or tenancy.

### EC2 Instances

Provide the lowest prices, offering saving up to 72% in exchange for commitment to usage if individual instance families in a region.

Automatically reduces your cost on the selected instance family in that region regardless of AZ, size, OR or tenancy. Give you the flexibility to change your usage between instances within a family in that region.

### SageMaker

Helps you reduce SageMaker cost by up to 64%, automatically apply to SageMaker usage regardless of instance family, size, component or Region.