# MANAGEMENT & DEVELOPMENT TOOLS

## AWS APPLICATION PROGRAMMING INTERFACE API

### What is an Application Programming Interface (API)?

An API is software that allows two applications/services to talk to each others. The most common type of API is via HTTP/S request.

AWS API is HTTP API and you can interact by sending HTTP request, using an application interacting with APIs like Postman.

Each AWS Service has its own Service Endpoint which you send request.

To authorize you will need generated a signed request. You make a separate request with your AWS Credentials and get back a token.

You need to also provide an Action and accompanying parameters as payloads.

Rarely do users directly send HTTP request directly to the AWS API, it much easier to interact with the API via a variety of Developer Tools.
 - AWS Management Console: A WISWIG Web Interface
 - AWS SDK: Interact with the API using your favourite programming language
 - AWS CLI: Interact with the API via a terminal/shell program
 - HTTP Request: Directly interact with the AWS API

## AWS MANAGEMENT CONSOLE

The AWS Management Console is a web-based unified console. Build, manage and monitor everything from simple web apps to complex cloud development.

Point and Click to manually launch and configure AWS resources with limited programming knowledge.

This is known as *ClickOps* since you can perform all your system operations via clicks.

The AWS Management Console is located at: console.aws.amazon.com

### Service Console

AWS Service each have their own customized console. You can access this consoles by searching the service name.

Some AWS Services Consoles will act as an umbrella console containing many AWS Service (eg: VPC Console, EC2 Console, System Manager Console, Sagemake Console, CloudWatch Console).

## ACCOUNT ID

Every AWS Account has a unique Account ID. The Account ID can be easily found by dropping down the current user in Global Navigation. The AWS Account ID is composed of 12 digit.

The AWS Account ID is used:
 - When logging is with a non-root user account.
 - Cross-account roles
 - Support cases

It is generally good to keep your Account ID private as it is one of many components used to identify an account for attack by a malicious actor.

## AWS TOOLS FOR POWER SHELL

PowerShell is a task automation and configuration management framework. A command-line shell and scripting language.

Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR) and accepts and returns .NET objects.

AWS Tools for PowerShell lets you interact with the AWS API via PowerShell Cmdlets.

Cmdlets is a special type of command in PowerShell in the form of capitalized werb-and-noun (eg:New-S3Bucket)

## AMAZON RESOURCE NAME (ARNs)

Amazon Resource Name (ARNs) uniquely indetify AWS resources. ARN are required to specify a resource unambiguosly across all of AWS.

The ARN has the following format versions:
 - arn:partition:service:region:account-id:resource-id
 - arn:partition:service:region:account-id:resource-type:resource-id
 - arn:partition:service:region:account-id:resource-type/resource-id

The ARN can be split in
 - Partition
    - aws -> AWS Regions
    - aws-cn -> China Regions
    - aws-us-gov -> AWS GovCloud (US) Regions
 - Service: Identifies the service
    - ec2
    - s3
    - iam
 - Region: which AWS resource is in
    - us-east-1
    - us-west-1
    - ca-centra-1
 - Account ID
    - 123456789012
    - 999999999999
 - Resource ID: Could be a name or path
    - user/Andres
    - instance/i-1234567890abcdef0

In the AWS Management Console its commnon to be able to copy the ARN to your clipboard

Resource ARNs can include a path. Path can include a wildcard character, namely an asterisk (*)