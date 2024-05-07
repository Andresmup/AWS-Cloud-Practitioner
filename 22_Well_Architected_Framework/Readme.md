# AWS WELL ARCHITECTED FRAMEWORK

The AWS Well architected framework is a whitepaper created by AWS to help customers build using best-practices defined by AWS (aws.amazon.com/architecture/well-framework).

The framework is divided into 5 sections called pillars which address different aspects or "lenses" that can be aplied to a Cloud workloard.

**Your Cloud Workload**:
 - **AWS Well-Architected Framework**: If the foundations is not solid structural problems will arise
    - **General definitions**
    - **General design principles**
    - **The review process**
 - **5 Pillars**: Each pillar also has its own detailed whitepaper
    - **Operational Excelence**
    - **Security**
    - **Reliability**
    - **Performance efficiency**
    - **Cost Optimization**

## GENERAL DEFINITIONS

Here are some general definitions:
 - **Component**: Code, configuration and AWS resource against a requirement
 - **Workload**: A set of components that work together to deliver business value
 - **Milestones**: Key changes of your architecture throught product life cycle
 - **Architecture**: How components work together in a workload
 - **Technology Portfolio**: A collection of workloads required for the business to operate
 - **Business Value**: You can trade-off pilars based on Business Context
    - **Operational Excellent Pilar**: Run and monitor systems
    - **Security Pillar**: Portect data and systems, mitigate risks
    - **Reliability Pillar**: Mitigate and recover from disruptions
    - **Perfomance Efficency Pillar**: Use computing resources effectively
    - **Cost Optimization Pillar**: Get the lowest price

## ON ARCHITECTURE

The AWS Well architected framework is designed around different kind of team structure. Enterprises generally have centralized teams with specific roles where AWS has distributed teams with flexible roles. Distributed teams can come with new risks, AWS mitigates these with Practices, Mechanisms and Leadership principles.

On-Premise Enterprises (managed by TOGAF or Zachman framework) has centralized team consisting of:
 - Technical Architect (infrastructure)
 - Solution Architect (software)
 - Data Architect
 - Networking Architect
 - Security Architect

Amazon Web Services (supported by virtual community of SMEs, Principle Engeineers) has distributed teams consisting of:
 - Practices: Team experts (Raise the bar)
 - Mechanisms: Automated check for standards
 - Amazon Leadership Principle

## AMAZON LEADERSHIP PRINCIPLES

The Amazon Leadership Principles are a set of principles used during tbe company decision-making, problem-solving, simple brainstorming and hiring:
 - **Customer Obsession**: Leaders prioritize the customer, striving to earn and maintain their trust above all else, even over focusing on competitors.
 - **Ownership**: Leaders think long-term, acting in the best interest of the company as a whole and taking responsibility beyond their immediate roles.
 - **Invent and Simplify**: Innovation and simplicity are valued, with leaders actively seeking new ideas and ways to streamline processes.
 - **Are Right, A Lot**: Leaders exhibit strong judgment and seek diverse perspectives, aiming to make correct decisions consistently.
 - **Learn and Be Curious**: Leaders continually seek self-improvement and embrace curiosity about new opportunities.
 - **Hire and Develop the Best**: Exceptional talent is recognized and nurtured, with a focus on raising the performance bar across the organization.
 - **Insist on the Highest Standards**: Leaders maintain high standards and drive their teams to deliver quality, ensuring problems are addressed promptly.
 - **Think Big**: Leaders inspire boldness and innovation, encouraging a forward-thinking mindset that goes beyond conventional boundaries.
 - **Bias for Action**: Speed and calculated risk-taking are valued, with a preference for action over prolonged deliberation.
 - **Frugality**: Leaders encourage resourcefulness and efficiency, emphasizing the importance of accomplishing more with fewer resources.
 - **Earn Trust**: Leaders communicate openly, listen attentively, and hold themselves and their teams accountable, striving to earn trust through their actions.
 - **Dive Deep**: Leaders are hands-on and detail-oriented, staying connected to the intricacies of their work and maintaining a healthy skepticism.
 - **Have Backbone; Disagree and Commit**: Leaders are willing to challenge decisions respectfully and commit fully once a decision is made, prioritizing conviction over social harmony.
 - **Deliver Results**: Leaders focus on delivering key business outcomes with quality and timeliness, persevering through setbacks.
 - **Strive to be Earth’s Best Employer**: Leaders prioritize creating a positive work environment that fosters growth, diversity, and empathy, aiming to be a model employer.
 - **Success and Scale Bring Broad Responsibility**: Leaders recognize their impact on the world and strive to continually improve, leaving a positive legacy for future generations.

## GENERAL DESIGN PRINCIPLES

When designing a infrastructure this are important principles:
 - **Stop guessing your capacity needs**: Cloud computing you use little to much based on demand
 - **Test systems at production scale**: Clone production env to testing, tear down testing not in use to save money
 - **Automate to make architectural experimentation easier**: Using CloudFormation with ChangeSets, StackUpdate and DriftDetection
 - **Allow for evolutionary architectures**: CI/CD, rapid or nightly releases, Lambdas deprecating run-times forcing you to evolve
 - **Drive architectures using data**: CloudWatch, CloudTrail automatically turned on collecting data
 - **Improve through game days**: Simulate traffic on production or purposely kill EC2 instances to see test recovery

## ANATOMY OF A PILLAR

A Pillar of the AWS Well-Architected Framework is structured as follows:
 - **Design Principles**: A list of design principles that need to be considered during implementation
 - **Definition**: Overview of the best practice categories
 - **Best Practices**: Detailed information about each best practice with AWS Services
 - **Resources**: Additional documentation, whitepapers and videos to implement this pillar

## OPERATIONAL EXCELLENT

Operational excellent design principles:
 - **Perform operations as code**: Apply the same engineering discipline you would to application code yo your cloud infrastructure. By treating your operations as code you can limit human error and enable consistent responses to events (eg: Infrastructure as Code).
 - **Make frequent, small, reversible changes**: Design worloads to allow components to be updated regulary (eg: rollbacks, incremental changes, blue/green deployment, CI/CD).
 - **Refine operations procedures frequently**: Look for continuous opportunities to improve your operations (eg: use game days to simulate traffic or event failure on your production workloads).
 - **Anticipate failure**: Perform post-mortems on system failures to better improve, write test code, kill production servers to test recovery.
 - **Learn from all operational failures**: Share lessons learned in a knowledge base for operational events and failures across your entire organization.

## SECURITY 

Security design principles:
 - **Implement a strong identity foundation**: Implement Principle of Least Privilege (PoLP), use centralized identity, avoid Long-lived credentials, (eg: IAM Roles).
 - **Enable traceability**: Monitor alert and audit actions and changes to your environment in real-time. Integrate log and metric collection and automate investigation and remediation.
 - **Apply security at all layers**: Take defense in depth approach with multiple security controls for everything (eg: Edge Network, VPC, Load Balancing Instances, OS, Application Code).
 - **Automate security best practices**
 - **Protect data in transit and at rest**
 - **Keep people away from data**
 - **Prepare for security events**: Incident management systems and investigation policy and processes. Tools to detect, investigate and recover from incidences.

## RELIABILITY

Reliability design principles:
 - **Automatically recover from failure**: Monitor Key Perfomance Indicators (KPIs) and trigger automation when threshold is breached.
 - **Test recovery procedures**: Test how your workloads fail and validate your recovery procedures. You can use automation to simulate different failures or to recreate scenarios that led to failure before.
 - **Scale horizontally to increase aggregate system availability**: Replace one large resource with multiple small resources to reduce impact of a single failure on the overall worload. Distribute request across multiple, smaller resources to ensure that they don't share a common point of failure.
 - **Stop guessing capacity**: In on-premise it takes a lot of guess work to determine the elasticity of your workloads demands. With Cloud you don't need to guess how much you need because you can request the right size of resources on-demand.
 - **Manage change in automation**: Making changes via Infrastructure as Code, will allow for a formal process to track and review infrastructure.

## PERFOMANCE EFFICIENCY 

Perfomance efficiency design principles:
 - **Democratize advantage technologies**: Focus on product development rather than procurement, provisioning and management of services. Take advantage of advanced technology specialized and optimized for your use case with on-demand cloud services.
 - **Go global in minutes**: Deploying your workloads in multiple AWS Regions around the world allows you to provide lower latency and a better experience for your customers at minimal cost.
 - **User serverless architectures**: Serverless architectures remove the need for you to run and maintain physical servers for traditional compute activities. Removes the operational burden of managing physical servers, and can lower transactional cost because managed services operate at cloud scale.
 - **Experiment more often**: With virtual and automatable resources, you can quickly carry out comparative testing using different types of instances, storage or configurations.
 - **Consider mechanical sympathy**: Understand how cloud services are consumed and always use the technology approach that aligns best with your workload goal (eg: consider access data patterns when you select database or storage approaches).

## COST OPTIMIZATION

Cost optimization design principles:
 - **Implement Cloud Financial Management**: Dedicate time and resources to build capability Cloud Financial Management and Cost Optimization tooling.
 - **Adopt a consumption model**: Pay only for the computing resources that you require and increase or decrease usage depending on business requirements.
 - **Measure overall efficiency**: Measure the business output of the workload and the cost associated with delivering it. Use this measure to know the gains you make from increasing output and reducing costs.
 - **Stop spending money on undifferentiated heavy lifting**: AWS does the heavy lifting of data center operations like racking, stacking and powering servers. It also removes the operational burden of managing operating system and applications with managed services. This allows you to focus on your customers and business projects rather than on IT infrastructure.
 - **Analyze and attribute expenditure**: The Cloud makes it easier to accurately identify the usage and cost of systems, which then allows transparent attribution of IT costs to individual workload owners. This helps measure return on investment (ROI) and gives workload owners an opportunity to optimize their resources and reduce costs.
 
## AWS WELL-ARCHITECTED TOOL

The Well-Architected Tool is an auditing tool to be used to asset your cloud workloads for alignment with the AWS Well Architected Frameworks.

## AWS ARCHITECTURE CENTER

The AWS Architecture Center is a web-portal that contains best practices and references architectured for a variety of different workloads (aws.amazon.com/architecture)