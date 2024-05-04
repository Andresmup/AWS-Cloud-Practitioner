# NETWORKING

## CLOUD-NATIVE NETWORKING SERVICES

The components are:
 - **Region**: The geographical location of your network
 - **Availability Zones**: AZ is where is the data center of your AWS resources
 - **VPC**: Is a logically isolated section of the AWS Cloud where you can launch AWS resources (not all services require to select a VPC because the are managed by AWS)
 - **Subnets**: Is a logical partition of an IP network into multiple, smaller network segments
 - **Internet Gateway**: Enable access to the Internet
 - **Route table**: Determine where the network traffic from your subnets are directed
 - **Network ACLs (NACLs)**: Acts as a firewalls at the subnet level
- **Security Group**: Acts as firewall at the instance level

## ENTERPRISE/HYBRID NETWORKING SERVICES

The services are:
 - **DirectConnect**: Dedicated gigabit connection from on-premise data-center to AWS (very fast connection)
 - **Virtual Private Network (VPN)**: A secure connection between on-premise, remote offices, mobile employees
 - **PrivateLinks (PR)**: (VPC Interface Enpoints) keeps traffic within the AWS network and not traverse the internet to keep the traffic secure

## VPC AND SUBNETS

Virtual Private Cloud (VPC) is a logically isolated section of the AWS Network where you lauch AWS resources. You choose a range of IPs using CIDR Range (eg: CIDR Range 10.0.0.0/16 = 65536 IP Addresses)

Subnets is a logical partition of an IP network into multiple smaller network segments. You are breaking up your IP range for VPC into smaller networks. Subnets need to have a smaller CIDR range that the VPC represent their portion (eg: Subnet CIDR Range 10.0.0.0/24 = 256 IP Addresses)
 - Public Subnet can reach the internet
 - Private Subnet is one that cannot reach the internet

## SECURITY GROUPS VS NACLs

Network Access Control (NACLs) acts as a virtual firewall at the subnet level. You can create **Allow and Deny rules**. (eg: Block a specific IP address known for abuse)

Security Groups acts as a virtual firewall at the instance level. Implicitly denies all the traffic. You can create only **Allow rules**; *you cannot block a single IP addres*. (eg: Allow an EC2 instance access on port 22 for SSH)

