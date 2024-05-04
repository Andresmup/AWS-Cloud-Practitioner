# GOVERNANCE

## ORGANIZATIONS AND ACCOUNTS

AWS Organizations must be turned on, once turned it cannot be turned off. You can create as many AWS Accounts as you like, one account will be the Root (master) Account.

Some important aspects are
 - **AWS Organizations** allow the creation of AWS Accounts. Centrally manage billing, control access, compilance, security and share resources across AWS Accounts.
 - **Root Account User** is a single sign-in identity that has complete access to all AWS services and resources in an Account. Each AWS Account has a Root Account User.
 - **Organization Units** are a group of AWS Accounts within an organization which can also contain other organizational units, creating a hierarchy
 - **Service Control Policies** give central control over the allowed permissions for all accounts in your organizations, helping to ensure your account stay within your organization's guidelines

## AWS CONTROL TOWER

AWS Control Tower helps Enterprises quickly set-up a secure AWS multi-account. Provides you with a baseline enviroment to get started with a multi-account architecture, the key points are:
 - **Landing Zone**: A landing zone is a baseline enviroment following well-architected and best-practices to start lauching ready workloads
    - AWS SSO enable
    - Centralized logging for AWS CloudTrail
    - Cross account security auditing
 - **Account Factory**
    - Automates provisioing of new accounts in your organization
    - Standardize the provisioning of the new accounts with pre-approved account configurations
    - Configure your account factory with new pre-approved network configurations and region selections
    - Enable self-service for your builders to configure and provision new accounts using AWS Service Catalog
 - **Guardrails**: Pre-packaged governance rules for security, operations and compliance that customers can select and apply enterprise-wide or to specific groups of accounts

## AWS CONFIG

Change management in the context of Cloud Infrastructure is when we have a formal process to:
 - Monitor changes
 - Enforce changes
 - Remediate changes

Compliance as a Code (CaC) is when we utilize programming to automate the monitoring, enforce and remediating changes to stay compliant with a compliance program or expected configuration

AWS Config is a Compliance-as-Code framework that allows us to manage changes in your AWS accounts on a per region basis (need to be turned on in every region we want). AWS Config should be used:
 - I want this resource to stay configured a specific way for compliance
 - I want to keep track of configuration changes to resources
 - I want a list of all resources within a region
 - I want to analyzed potential security waknesses, or you need a detailed historical information

## AWS QUICK STARTS

AWS Quick Starts are pre-built templates by AWS and AWS Partners to help deploy wide range of stacks.

A Quick Start is composed of 3 parts:
 - A reference architecture for the deployment
 - AWS CloudFormation templates that automate and configure the deployment
 - A deployment guide explaining the architecture and implementation in detail

 Most Quick Starts reference deployments enable you to spin up a fully functionall architecture in less that an hour

## TAGGING

A tag is a key and value pair that you can assign to AWS resources. Tags allow you to organize your resources in the following ways:
 - **Resource management**: Specific workloads, enviroments (eg: developer enviroment)
 - **Cost management and optimization**: Cost tracking, budgets, alerts
 - **Operation management**: Bussiness commitments and SLA operations (eg: mission-critical services)
 - **Security**: Classification of data and security impact
 - **Governance and regulatory compliance**
 - **Automation**
 - **Workload optimization**

Tag examples:
 - Dept = Finance
 - Status = Approved
 - Team = Compliance
 - Enviroment = Production
 - Project = Enterprise
 - Location = USA

Tagging can be used in conjunction with IAM policies (eg: restrict access based on tags)

## RESOURCE GROUPS

Resource Groups are a collection of resources that share one or more tags. It helps you to organize and consolidate information based on your project and the resources that you used. 

Resources Groups can display details about a group of resource based on:
 - Metric
 - Alarm
 - Configuration settings

At any time you can modify the settings o your resouce groups to change what resources appear.

Resource Groups appears in the Global Console Header under the Systems Manager.

## BUSINESS CENTRIC SERVICES

Some services are:
 - **Amazon Connect**: Is a virtual call center service. You can create workflow to route callers. You can record phone calls. Manage a queue of callers. Based on the same proven system used by the Amazon customer service teams
 - **Workspaces**: Is a virtual remote desktop service. Secure managed service for provisioning either Windows or Linux desktops in just a few minutes whick quickly scales up to thousands of desktops
 - **WorkDocs**: Is a shared collaboration service. A centralized storage to share content and files. Its similar to Microsoft SharePoint (shared folder where the company has the ownership)
 - **Chime**: Is a video conference service. It is similar to zoom. It is secure by default and it can show you a calendar of your incoming calls
 - **WorkMail**: Is a managed business email, contact and calendar service with support for existing desktop and mobile email client applications (IMAP). Similar to Gmail
 - **PinPoint**: Is a markeging campaign management service. PinPoint is for sending targeted emails via SMS, push notifications and voice messages. You can perform A/B testing or create Journeys (complex emails workflows)
 - **Single Email Service (SES)**: Is a transactional email service. You can integrate SES into your application to send emails. You can create common templates, track open-rates, keep track of your reputation
 - **QuickSight**: Is a Bussiness Intelligent (BI) service. Connect multiple data sources and quickly visualize data in the form of graphs with little to no programming knowledge