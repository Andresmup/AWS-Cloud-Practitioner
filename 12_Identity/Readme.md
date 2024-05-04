# IDENTITY 

## ZERO-TRUST MODEL

The Zero Trush Model operates on the principle of *trust no one, verify everything*.

Malicious actors being able to by-pass conventional access controls demostrates traditional security measures are no longer suficient.

In the zero-trust model Identity becomes the primary security perimeter. The primary or new security perimeter defines the first line of defense and its security controls that protect a company's cloud resources and assets.

Network-Centric (old-way): Traditional security focused on firewalls and VPN's since there were few employees or workstations outside the office or they were in specific remote offices.

Identity-Centric (new-way): Bring-your-own-device, rmeote workstations is much more common, we can't trust if employee is in a secure location, we have indentity based security controls like MFA, or providing provisional access based on the level of risk from where, when and what a user wants to access. Identity-Centric does not replace but augments Network-Centric-Security.

## ZERO-TRUST ON AWS

Identity Security Controls you can implement on AWS to meet the Zero Trust Model:
 - **AWS Identity and Access Management (IAM)**: This is the service where users, groups and policies are created.
    - **IAM Policies**: Set of permissions that allow "users" to use certain services and actions
    - **Permission Boundaries**: The boundaries is the maximum permissions that an identity-based policy can grant to an IAM entity. An entity's permissions boundary allows it to perform only the actions that are allowed by both its identity-based policies and its permissions boundaries.
    - **Service Control Policies**: Organization-wide policies
    - **IAM Policy Conditions**: Factors that control access
        - aws:SourceIp: Restrict on IP address
        - aws:RequestedRegion: Restrict on region
        - aws:MultiFactorAuthPresent: Restrict if MFA is turned off
        - aws:CurrentTime: Restrict access based on time of day

AWS does not have a ready-to-use intelligent identity controls, which is why AWS is considered to not have a zero-trust offering for customers, and third party services need to be used.

A collection of AWS Service can be setup to intelligetish detection of identity concerns but requires expert knowledge, the services are:
 - **Cloud Trail**: Which tracks all API calls.
 - **GuardDuty**: Detects suspicious or malicious activity based on CloudTrail (feed GuarDuty) and other logs.
 - **Detective**: Used to analyzed, investigate and quickly identify secure issues (can ingest findings from GuardDuty)
 
## ZERO-TRUST ON AWS WITH THIRD PARTIES

AWS does technically implement a Zero Trust Model but does not allow for intelligent indentity security controls. 

Third-party identity solutions have more intellingent security controls for real-time detection:
 - Azure Active Directory (Azure AD)
 - Google BeyondCorp
 - JumpCloud

In order to access to your AWS resources you connect this Third-party identity solutions via AWS Single Sign-On.

## DIRECTORY SERVICE

A directory service maps the names of network resources to their network addresses.

A directory service is shared information infrastructure for locating, managing, administering and organizing resources (volumes, folders, files, printers, devices, and other objects).

A directory service is a critical component of a network operating system. A directory server is a server that provides a directory service.

Each resource on the network is considered an object by the directory server. Information about a particular resource is stored as a collection of attributes associated with that resource object.

Well known directory services are:
 - Domain Name Service (DNS): The directory service of the internet
 - Microsoft Active Directory
    - Azure Active Directory
 - Apache Directory Server
 - Oracle Internet Directory (OID)
 - OpenLDAP
 - Cloud Identity
 - JumpCloud

## IDENTITY PROVIDERS (IdPs)

Identity Provider (IdP) is a system entity that creates, maintains and manages identity information for principals and also providers authentication services to applications within federation or distributed network.

A trusted provider of your user identity that lets you use authenticated access to other services. Identity Providers could be Facebook, Amazon, Google, Twitter, Github, Linkedin.

Federated Identity is a method of linking a user's identity across multiple separate identity management system.
 - OpenID: OpenID is about providing who you are
 - OAuth2.0: OAuth is about granting access to functionality
 - SAML: Exchange authentication and authorization between an identity provider and a service provider. An important use case for SAML is Single-Sign-On via web browser

## SINGLE-SIGN-ON (SSO)

Single-Sign-On (SSO) is an authentication scheme that allows a user to log-in with a single ID and password to different systems and software.

SSO allows IT departments to administrate a single identity that can access many machines and cloud services.

Login for SSO is seamless, where once a user is logged into their primary directory they are not presented with a login screen again.

## LDAP

Lightweight Directory Access Protocol (LDAP) is an open, vendor-neutral, industry standard application protocol for accessing and maintaining distributed directory information services over an Internet Protocol (IP) network.

A common use of LDAP is to provide a central place to store usernames and passwords.

LDAP enables for same-sing-on. Same-sign-on allows users to SingleID  and password, but they have to enter it in every time they want to login.

### LDAP over SSO?

SSO is much convinient, and most of SSO system are using LDAP. But LDAP was not dessigned natively to work with web-applications; so some systems only supports integration with LDAP and not SSO.

## MULTI-FACTOR AUTHENTICATION (MFA)

Multi-Factor Authentication (MFA) is a security control where after you fill in your username/email and password you have to use a second device such as a phone to confirm that its you logging in.

MFA protects against people who have stolen your password.

## SECURITY KEY

Security Key is a secondary device used as second step in authentication process to gain access to a device, workstation or application.

A security key can resemble a memory stick. When your finger makes contact with the button the device will generate and autofill a security token.

## IDENTITY AND ACCESS MANAGEMENT (IAM)

AWS Identity and Access Management (IAM) is a service where you can create and manage AWS users and groups, use permissions to allow and deny to access AWS resources.

Some components are:
 - **IAM Polices**: JSON documents which grant access permission for a specific user, groups or role to access services. Policies are attached to IAM identities.
 - **IAM Permission**: The API actions that can or cannot be performed. They are represented in the IAM Policy document.
 - **IAM Identities**
    - **IAM Users**: End users who log into the console or interact with AWS resource programmatically or via clicking UI interfaces
    - **IAM Groups**: Group up of Users so they share permission levels of the group (Admins, Developers, Auditors)
    - **IAM Roles**: Roles grant AWS resources permission to specific AWS API actions. Associate policies to a Role and the assign it to a AWS Resource.

## ANATOMY OF AN IAM POLICY

IAM Policy are written in JSON and contains the permission which determine what API action are allowed or denied.
 - **Version policy language version**: 2012-10-17 is the lasted version
 - **Statement**: Statement container for the policy element, you are allow to have multiples
 - **Sid** (optional): A way of labelling statements
 - **Effect**: Set whether the policy will Allow or Deny
 - **Action**: List the actions that the policie allows or denies
 - **Principal**: Acount, user, role or federated user to which you would like to allow or deny access
 - **Resource**: The resource to which the action(s) apply
 - **Condition** (optional): Circunstances under which the policy grants permission

## PRINCIPLE OF LEAST PRIVILEGE (PoLP)

Principle of least privilege (PoLP) is the compute security concept of providing a user role or application the least amount of permission to perform a operation or action.
 - **Just-Enought-Access (JEA)**: Permitting only the exact actions for identity to perform task
 - **Just-In-Time (JIT)**: Permitting the smallest lenght of duration an identity can use permissions
 - **Risk-based adaptive policies**: Each attempt to access a resource generate a risk score of likely the request is to be from a compromised source. The risk score could be based on (device, user location, IP address, service request and more). AWS currently does not have Risk-based adaptative policies built into IAM.

## AWS ACCOUNT ROOT USER

First we need to distinguish:
 - **AWS Account**: The account which hold all your AWS resources
 - **AWS Account - Root User**: A special account with full access that cannot be deleted
 - **AWS Account - User**: A user for commont task that is assigned permissions

AWS Account Root User is a special user who is created at the time AWS account creation:
 - The Root User account uses an email and password to login. While a regular user has to provide the AccountID / Alias, username and password
 - The Root User account cannot be deleted
 - The Root User account has fully permissions to the account and its permissions can not be limited
    - You cannot use IAM Policies to explicitly deny the root user access to resources
    - You can only use an AWS Organization Service Contol Policy (SCP) to limit the permission of the root user
 - There can only be one Root User per AWS account
 - The root user is instead for very specific and specialized task that are infrequenly or rarely performed
    - An AWS Root account should not be used for daily or common task
 - Its strongly recommended to never user Root User Access Key
 - Its strongly recommended to turn on MFA for the Root User

### Exclusive Root User Tasks

Administrative tasks that only the Root User can perform:
 - **Change account settings**: 
    - Include the account name, email address, root user password, and root user access key
    - Other account settings, such as contact information, payment current preference and regions do not require root user credential
 - **Restore IAM user permissions**: If the only IAM Administrator accidentally revokes their own permissions, the root user can edit policies and restore those permission
 - **Active IAM access to the Billing and Cost Management console**
 - **View certain tax invoices**
 - **Close the AWS Account**
 - **Change or cancel AWS Support Plan**
 - **Register as a seller in the Reserved Instances Marketplace**
 - **Enable MFA Delete on S3 Bucket**
 - **Edit or Delete and Amazon S3 Policy that includes an invalid VPC ID or VPC endpoint ID**
 - **Sign up for GovCloud**

## AWS SSO

AWS Single-Sign-On (SSO) is where you create or connect your workforce identities in AWS once and manage access centrally accross your AWS configuration.

Choose your Identity Source:
 - AWS SSO
 - Active Directory
 - SAML 2.0 IdP

Managed User Permissions Centrally
 - AWS Account
 - AWS Applications
 - SAML Applications

User get Single Click Access