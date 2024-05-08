# DEFENSE

## DEFENSE IN DEPTH

This are the 7 layers of security that are consider when working with cloud resources, from inner to outer layer:
 1. **Data**: Access to business and customer data, encyption to protect data.
 2. **Applications**: Applications are secure and free of security vulnerabilities.
 3. **VM/Compute**: Access to virtual machine (ports, on-premise, cloud).
 4. **Network**: Limit communication between resources using segmentation and access controls.
 5. **Perimeter**: Distributed denial of service (DDoS) protection to filter large-scale attacks before they can cause a denial of service for users.
 6. **Policies/Indentity & Access**: Controlling access to infrastructure and change control.
 7. **Physicall**: Limiting access to a datacenter to only authorized personnel.

## CONFIDENTIALITY, INTEGRITY, AVAILABILITY (CIA)

Confidentiality, Integrity and Availability (CIA) triad is a model describing the foundation to security principles and their trade-off relationships.
 - **Confidentiality**: Confidentiality is a component of privacy that implements to protect your data from unauthorized viewers. In practice this can be using cryptographic key to encrypt your data using keys to encrypt your keys (envolve encryption).
 - **Integrity**: Integrity is maintaining and assuring the accuracy and completeness of data over its entire lifecycle. In practice utilizing ACID compliance database for valid transactions. Utilizing tamper-evident or tamper proof Hardware security models (HSM).
 - **Availability**: The information needs to be made available when needed in practice: High Availability, Mitigating DDoS, Deciption Access. 

## VULNERABILITY 

A vulnerability is a hole or a weakness in the application, which can be a design flaw or an implementation but, that allows an attacker to cause harm to the stakeholders of an application.

## PENETRATION TESTING

A PenTesting is an authorized simulated cyberattack on a computer system, performed to evaluate the security of the system.

PenTesting is allowed to perform in AWS.

Permitted services:
 - EC2 Intances
 - NAT Gateway
 - ELB
 - RDS
 - CloudFront
 - Aurora
 - API Gateways
 - Lambda and Lambda Edge
 - Amazon Lightsail resources
 - Amazon Elastic Beanstalk enviroments

Prohibited Activities:
 - DNS zone walking via Amazon Route 53 Hosted Zones
 - Subject to DDoS Simulation Test policy
    - Denial of Service (DoS)
    - Distributed Denial of Service (DDoS)
    - Simulated DoS, Simulated DDoS
 - Port flooding
 - Protocol flooding
 - Request flooding (login request flooding, API request flooding)

## AWS ARTIFACT

AWS Artifact is a self-serve portal for on-demand access to AWS compliance reports. You just need to choose the report, view the PDF and download the Excel.

## INSPECTOR

Hardening is the act of eliminating as many security risk as possible. Hardening is a common for Virtual Machines where you run a collection of security checks known as security benchmark.

AWS Inspector runs a security benchmark agains specific EC2 instances.

You can run a variety of security benchmark and can perform Network and Host assessment. You only need to:
 - Install the AWS agent on your EC2 instances.
 - Run an assessment for your assessment target.
 - Review your findings and remediate security issues.

## AWS SHIELD 

AWS Shield is a managed DDoS protection service that safeguards applications running on AWS. When you route your traffic through Route53 or CloudFront you are using AWS Shield Standard.

A DDoS (Distributed Denial Service) attack is a malicious attempt to disrupt normal traffic by flooding a website with large amounts of fake traffic.

AWS Shield protects you against:
 - Layer 3: Network
 - Layer 4: Transport
 - Layer 7: Application

AWS Shield comes in two plans:
 - **Shield Standar Free**: Protection agains most common DDoS attacks:
    - Access to tools and best practices to build a DDoS resilient architecture
    - Automatically available on all AWS resources
 - **Shield Advanced (start 3000$/year)**: Additional protection against larger and more sophisticated attacks
    - Available ON:
        - Route53
        - CloudFront
        - ELB
        - Global Accelerator
        - Elastic IP (Amazon EC2 and Network Balancer)
    - Notable features:
        - Visibility and reporting on layer 3, 4 and 7
        - Access to team and support (with business or enterprise support)
        - DDoS cost protection
        - Comes with SLA

Both plans integrate with AWS Web Application Firewall (WAF) to give you Layer 7 (Application) protection. So if you are not using WAF you will not have the layer 7 protection.

## AMAZON GUARD DUTY

An Intrusion Detection System and Intrusion Protection System (IDS/IPS) is a device or software application that monitors a network or systems for malicious activity or policy violations.

GuardDuty is threat detection service that continously monitors for malicious, suspicious activity and unauthorized behavior. It uses Machine Learning to analyze the following AWS logs:
 - CloudTrail Logs
 - VPC Flow logs
 - DNS Logs

It will alert you of findigs which you can automate a incident response via CloudWatch Events or with 3rd Party Sevices.

## AMAZON MACIE

Macie is a fully managed service that continously monitors S3 data access activity for anomalies and generates detailed alerts when it detect risk of unauthorized access or inadvertent data leaks.

Macie will indentify your most at-risk users which could lead a compromise.

Macie works by uses Machine Learning to analyze your CloudTrail logs. Macie has a variety of alerts.
 - Anonymized Access
 - Config Compliance
 - Data Compliance
 - Credential Loss
 - File Hosting
 - Identity Enumeration
 - Information Loss
 - Location Anomaly
 - Open Permissions
 - Privilege Escalation
 - Ransomware
 - Service Disruption
 - Suspicous Access

## AMAZON VIRTUAL PRIVATE NETWORK (VPN)

AWS Virtual Private Tunnel (VPN) lets you stablish a secure and private tunnel from your network or device to the AWS global network.

There are two options:
 - **AWS Site-to-Site VPN**: Securely connect on-premises network or branch office site to VPC.
 - **AWS Client VPN**: Securely connect users to AWS or on-premises networks

Internet Protocol Security (IPsec) is a secure network protocol suite that authenticates and encrypts the packets of data to provide secure encrypted communication between two computers over an Internet Protocol network. It is used in virtual private networks (VPNs).

## AWS WEB APPLICATION FIREWALL (WAF)

AWS Web Application Firewall (WAF) protects your web applications from common web exploits. WAF can be attached to either CloudFront or Application Load Balancer (ALB).

With WAF you write your own rules to allow or deny traffic based on the contents of an HTTP requests. Use a ruleset from trusted AWS Security Partner in the AWS WAF Rules Marketplace. 

Protect applications from attacks covered in the OWASP top 10 most dangerous attacks:
 - Injection
 - Broken Authentication
 - Sensitive data exposure
 - XML External Entities (XXE)
 - Broken access control
 - Security misconfigurations
 - Cross Site Scripting (XSS)
 - Insecure Deserialization
 - Using component with known vulnerabilities
 - Insufficient logging and monitoring

## HARDWARE SECURITY MODULE (HSM)

A Hardware Security Module (HSM) is a piece of hardware designed to store encryption keys. HSM holds keys in memory and never write them to disk

HSM's that are multi-tenant are FIPS 140-2 Level 2 compliant, which are multiple customers virtually isolated on an HSM (eg: AWS KMS)

HSM's that are single-tenant are FIPS 140-2 Level 3 compliant, which is a simgle customer on a dedicated HSM (eg: AWS CloudHSM)

## AWS KEY MANAGEMENT SERVICE (KMS)

AWS Key Management Service (KMS) is a managed service that makes easy for you to create and control encryption keys used to encrypt your data. KMS is multi-tenant HSM

Many AWS services are integrated to use KMS to encrypt your data with a simple checkbox.

Every KEY cost 1$ but every AWS Account comes with one KMS key default for free.

KMS uses Envolve Encryption, which is when you encrypt your data, so its protected but you have to encrypt your key to protect it. So you encrypt your data key with a master key as an additional security layer.

## AWS CLOUDHSM

AWS CloudHSM is a single-tenant HSM as a service that automates hardware provisioning, software patching, high availability and backups.

CloudHSM enables you to generate and use your encyption keys on a FIPS 140-2 level 3 validated hardware.

Built on open HSM industry standards to integrate with:
 - PKCS#11
 - Java Cryptography Extensions (JCE)
 - Microsoft CryptoNG (CNG) libraries

You can also transfer your keys to other commercial HSM solutions to make it easy for you to migrate keys on or off of AWS.

Configure AWS KMS to use AWS CloudHSM cluster as a custom key rather than the default KMS key store.