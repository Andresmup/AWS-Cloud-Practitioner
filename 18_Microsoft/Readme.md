# MICROSOFT ON AWS

AWS has multiple services and tools to make it easy to run windows workloads on AWS.
 - **Windows Servers on EC2**: You can select from a number of Windows Servers versions including the latest version, Windows Server 2019.
 - **SQL Server on RDS**: In RDS you can select from a number of SQL Servers database versions.
 - **AWS Directory Service**: Lets you run Microsoft Active Directory (AD) as a managed service.
 - **AWS License Manager**: Makes it easier to manage your software licenses from software vendors such Windows.
 - **Amazon FSx for Windows File Server**: Is a fully managed scalable storage built for Windows.
 - **AWS Software Development KIT (SDK)**: Allows you to write code in your favourite language to interact with AWS API. The SDK supports .NET which is popular in Windows developers.
 - **Amazon Workspaces**: Allows you to run a virtual desktop. You can launch a Windows 10 desktop to provide secure and durable workstation that is accesible wherever you have an internet connection.
 - **AWS Lambdas**: Supports PowerShell as a programming language to write your serverless functions.
 - **AWS Migration Acceleration Program (MAP) for Windows**: Is a migration methodology from moving large enterprise. AWS has Amazon Partners that specialize in providing professional services for MAP.

## AWS LICENSE MANAGER

Bring-Your-Own-License (BYOL) is the process of reusing an existing software license to run vendor software on a cloud vendor's computing service. BYOL allows companies to save money since they may have purchased the license in bulk or at a time that provided a greater discount then if purchased again. Eg: License Mobility is Microsoft Volume Licensing customer with eligible servers applications covered by active Microsoft Software Assurance.

AWS License Manager is a service that makes it easier for you to manage your software licenses from software vendors centrally across AWS and your on-premises enviroments. You can choose license software based on virtual cores (vCPUs), physical cores, sockets or number of machines. This includes a variety of software products from Microsoft, IMB, SAP, Oracle and other vendors.

AWS License Manager works with:
 - **EC2**: Dedicated Instances, Dedicated Spot, Spot Instances
 - **RDS**: Only Oracle databases.

For Microsoft Windows Server and Microsoft SQL Server license you generally need to use a Dedicated Host.