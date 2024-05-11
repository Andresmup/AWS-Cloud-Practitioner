# TCO AND MIGRATION

## TOTAL COST OF OWNERSHIP (TCO)

The Total Cost of Ownership (TCO) is a financial estimate intended to help buyers and owners determine the direct and indirect costs of product or service.

Creating a TCO reports is usefull when your company is looking to migrate from on-premise to cloud.

CAPEX On-premise:
 - Software license fees
 - Implementation
 - Configuration
 - Training 
 - Physical security
 - Hardware
 - IT Personal
 - Maintenance

OPEX AWS:
 - Subscription fees
 - Implementation
 - Configuration
 - Training 

## CAPEX VS OPEX

### Capital Expenditure (CAPEX)

Spending money upfront on physical infrastructure. Deducting that expense from your tax bill over time.
 - Server cost (computers)
 - Storage cost (hard drives)
 - Network cost (routers, cables, switches)
 - Backup and archive costs
 - Disaster recovery costs
 - Datacenter costs (rent, cooling, physical security)
 - Technical personal

With Capital Expenses you have to guess upfront what you plan to spend

### Operational Expenditure (OPEX)

The costs associated with an on-premise datacenter that has shifted the cost to the service provider. The customer only has to be concerned with non-physical costs.
 - Leasing software and customizing features
 - Training employees in cloud services
 - Paying for cloud support
 - Billing based on cloud metrics (eg: computage usage, storage usage)

With Operation Expenses you can try a product or service without investing in equipment

## SHIFTING IT ROLES

A company considering migrating their workloads from on-premise to the cloud to take advantages of the savings. There is a consern among the staff that there will be mass layoffs. But Cloud does not make your IT personnel redundant.

Shifting your IT team:
 - A company need IT personnel during the migration phase
 - A company can transition some roles to new cloud roles (eg:Networking to Cloud Networking)
 - A company may decide to take a hybrid approach so they'll allways need to ahve a traditional IT team and a Cloud IT team
 - A company can change employees activities from managing infrasctructure to revenue generating.

## AWS PRICING CALCULATOR 

The AWS Pricing calculator (calculator.aws) is a free cost estimated tool than can be used within your web-browser without the need for an AWS Account to estimate the cost of a various AWS services.

The AWS Pricing calculator contains 100+ services that you can configure for cost estimate.

To calculate Total Cost of Ownership an organization needs to compare their existing cost against the AWS costs and so the AWS Pricing Calculator can be used to determine that cost. You can export your final estimate to .csv

## MIGRATION EVALUATOR 

AWS Migration Evaluator (TSO logic) is an estimate tool used to determine an organization existing on-premise cost so it can compare it against AWS Costs for planned cloud migration.

Migration Evaluator uses an Agentless Collector to collect data from your on-premise infrastructure to extract your on-premise costs.

## EC2 VIM IMPORT/EXPORT 

VM Import/Export allows users to import Virtual Machine images to EC2. You prepare your Virtual Image for upload, upload it to an S3 Bucket and use the AWS CLI to import your image. It will generate an Amazon Machine Image (AMI).

AWS has import instruction for:
 - VMWare
 - Citrix
 - Microsoft Hyper-V
 - Microsoft VHD from Azure
 - Linux VHD from Azure

## DATABASE MIGRATION SERVICE (DMS)

Database Migration Service (DMS) allows you to quickly and securely migrate one database to another. DMS can be used to migrate your on-premise database to AWS.

AWS Schema conversion tool is used in many cases to semi/automatically convert a source database schema to a target dabase schema. 

Each migration path requires a bit of research since not all combinations of sources and targets are posible.

## AWS CLOUD ADOPTION FRAMEWORK (CAF)

The AWS Cloud Adoption Framework is a whitepaper to help you plan your migration from on-premise to AWS.

At highest level, the CAF organizes guidance into six focus areas:
 - **Business Perspective**: How to update the staff skills and organizational processes to optimize business value as they move ops to the cloud (eg: Business managers, finance managers, budget owners and strategy stakeholders).
 - **People perspective**: How to update the staff skills and organizational processes to optimize and maintain their workforce and ensure competencies are in place at the appropiate time (eg: Human resources, staffing, people managers).
 - **Governance perspective**: How to update the staff skill and organizational processes that are necessary to ensure business governance in the cloud and manage and measure cloud investments to evaluate their business outcomes (eg: CIO, program managers, project managers, enterprise architects, business analytics).
 - **Platform perspective**: How to update the staff skills and organizational processes that are necessary to deliver and optime cloud solution and services (eg: CTO, IT managers, solution architect).
 - **Security Perspective**: How to update the staff skills and organizational processes that are necessary to ensure that architecture deployed in the cloud aligns to the organization's security control requirements, resilency and compliance requirements (eg: CISO, IT security managers, IT security analysts).
 - **Operations Perspective**: How to update the staff skills and organizational processes that are necessary to ensure system health and reliabilty during the move of operations to the cloud and them to operate using agile, ongoing, cloud computing best practices.