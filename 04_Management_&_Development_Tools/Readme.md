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

## COMMAND LINE INTERFACE (CLI)

AWS Command Line Interface (CLI) allows users to programmatically interact with the AWS API via entering single or multi-line commands into a shell.

The AWS CLI is a Python executable program, Python is required to install the AWS CLI. It can be installed en Windows, Mac, Linux / Unix. The name of the program is aws.

## SOFTWARE DEVELOPMENT KIT (SDK)

A Software Development Kit (SDK) is a collection of software deveplopment tools in one installable package.

You can use the AWS SDK to programmatically create, modify, delete or interact with AWS resources.

AWS SDK is offered in various programming languages (Java, Python, Ruby, Node.js, Go, .NET, PHP, JavaScript, C++)

## CLOUD SHELL

AWS Cloud Shell is a browser-based shell built into the AWS Management Console. AWS CloudShell is scoped per region, same credentials as logged in user and it's free. Cloud Shell include:
 - Preinstalled Tools
 - Storage included: 1GB of storage per AWS Region
 - Saved files and settings: Files saved into your home directory are available in future sessions for the same AWS region
 - Shell Enviroments: Seamlessly switch between Bash, PowerShell, Zsh 

## INFRASTRUCTURE AS CODE (IaC)

You write a configuration script to automate creating, updating or destroying cloud infrastructure.
 - IaC is a blueprint of your infrastructure
 - IaC allows you to easily share, version or inventory your cloud infrastructure

AWS has two offerings for writting Infrastructure as Code
 - AWS CloudFormation (CFN): CFN is a Declarative IaC tool, which means.
   - What you see its what you get
   - More verbose, but zero chance of mis-configuration
   - Uses scripting languages (JSON, YAML)
 - AWS Cloud Development Kit (CDK): CDK is an Imperative IaC Tool
   - You say what you what, the rest is filled in implicit
   - Less verbose, you could end up with mis-configurations
   - Does more than Declarative
   - Uses programming languages

### CloudFormation (CNF)

AWS CloudFormation allows you to write Infrastructure as Code (IaC) either a JSON or YAML file.

CloudFormation is simple but it can lead to large files or is limited in some regard to creating dynamic or repeatable infrastructure compared to CDK. CNF comes with its own CLI

Since CDK generates out CloudFormation is still important to be able to read and understand CloudFormation in order to debug IaC stacks.

### Cloud Development Kit (CDK)

AWS CDK allows you to use programming languages to write Infrastructure as Code (IaC)
 - CDK is powered by CloudFormation (it generates out CloudFormation templates)
 - CDK has a large library of reusable cloud components called CDK Construct (https:construct.dev)
 - CDK comes with its own CLI
 - CDK Pipelines quickly setup CI/CD pipelines for CDK projects
 - CDK has a testing framework for Unit and Integration Testing

AWS SDK looks similar, but the key difference is CDK ensures Idempotent of your infrastructure

## AWS TOOLKIT FOR VSCODE

AWS Toolkit is an open-source plugin for VSCode to create, debug and deploy AWS resources.
 1. AWS Explorer: Explore a wide range of AWS resources linked to your AWS account
 2. AWS CDK Explorer: Allows you to explore your stacks defined by CDK
 3. Amazon Elastic Container Service: Provide IntelliSense for ECS task-definitions files
 4. Serverless Applications: Create, debug and deploy serverless aplications via SAM and CFN

## ACCESS KEY 

Access Key is a key and secret required to have programmatic access to AWS resources when interacting with the AWS API outside of the AWS Management Console

An Access Key is commonly refered to as AWS Credentials

A user must be granted access to use Access Key

Some important aspects are:
 - Never share your access key
 - Never commit access key to a codebase
 - You can have two active Access Key
 - You can deactivate Access Key
 - Access Key have whatever access a user has to AWS resources
 - Access Key are stored in ~/.aws/credentials

The Default credentials will be the access used when no profile is specified. But you can store multiple access key by giving the profiles names.

You can use *aws configure* CLI command to populate the credential file

The AWS SDK will automatically read from these enviromenment variables. This is a safe way of using an Access Key within your code.