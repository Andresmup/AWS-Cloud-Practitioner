# PROVISIONING SERVICES

Provisioning is the allocation or creation of resources and services to a customer.

AWS Provisioning Services are responsable for setting up and managing those AWS Services, this are the services:
 - **Elastic Beanstalk (EB)**: Is a Platform as a Service (PaaS) to easily deploy web-applications. EB will provision various AWS Services, including EC2, S3, SNS, CloudWatch, EC2 auto-scalling groups and ELB. EB it's similar to Heroku but in AWS cloud.
 - **AWS OpsWorks**: Is a configuration management service that also provides managed instances of the open-source configuration managed software Chef and Puppet.
 - **CloudFormation**: Is a infrastructure modeling and provisioning service. Automate the provisioning of AWS Services by writting CloudFormation templates in either JSON or YAML files. This is known as Infrastructure as a Code (IaaS).
 - **AWS QuickStarts**: Are pre-made packages that can launch and configure your AWS compute, network, storage and other services required to deploy a workload on AWS.
 - **AWS Marketplace**: A digital-catalogue of thousands of software listings from independient sotfware vendors you can use to find, buy, test and deploy software.
 - **AWS Amplify**: Is a mobile and web-application framework that will provision multiple AWS services as your backend.
 - **AWS App Runner**: A fully managed service that makes it easy for developers to quicky deploy containerized web applications and APIs, at scale and with no prior infrastructure experience required.
 - **AWS Copilot**: Is a command line interface (CLI) that enables customers to quickly launch and easily manage containerized applications on AWS.
 - **AWS CodeStar**: Provides unified user interface, enabling you to easily manage your software deployment activities in one place. Easily launch common type of stacks (eg LAMP).
 - **AWS Cloud Developmnet Kit (CDK)**: An Infrastructure as a Code (IaC) tool. Allows you to use your favorite programming language. Generate out CloudFormation templates as the means for IaC.

## AWS ELASTIC BEANSTALK (EB)

A Platform as a Service (PaaS) allow customers to deploy, run and manage applications without the complexity of building and maintaining the infrastructure typically associated with developing and lauching an app.

Elastic Beanstalk (EB) is PaaS for deploying web-applications with little-to-no knowledge of the underlying infrastructure so you can focus on writting application code instead of setting up an automated deployment pipeline and DevOps tasks. Choose a platform, upload your code and it runs with little knowledge of the infrastructure.

AWS for entreprise and large companies do not recommend EB for production.

Elastic Beanstalk is powered by CloudFormation templates setup for:
 - Elastic Load Balancer
 - Autoscaling Groups
 - RDS Database
 - EC2 Instances preconfigured or custom platforms
 - Monitoring (CloudWatch, SNS)
 - In-place and blue/green deployment methodologies
 - Security (rotates password)
 - Can run dockerized enviroments