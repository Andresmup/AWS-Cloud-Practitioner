# LOGGING

## LOGGING SERVICES

This are logging services in AWS:
 - **CloudTrail**: Logs all API calls (SDK, CLI) between AWS Services.
    - Detect developer misconfigurations
    - Detect malicious actors
    - Automate responses
 - **CloudWatch**: Is a collection of multiple services
    - **CloudWatch Logs**: A centralized place to store your cloud services log data or application logs.
    - **CloudWatch Metrics**: Represents a time-ordered set of data points. A variable to monitor.
    - **CloudWatch Events (EventBridge)**: Trigger an event based on a condition (eg: ever hour take snapshot of server).
    - **CloudWatch Alarms**: Trigger notifications based on metrics.
    - **CloudWatch Dashboards**: Create visualizations based on metrics.
 - **AWS X-Ray**: Is a distributed tracing system. You can use it to PinPoing issues with your microservices. See how data moves from one app to another, how long it took to move and if it failed to move forward.

## CLOUD TRAIL

AWS Cloud Trail is a service that enables governance, compliance, operational auditing and risk auditing of your AWS account.

AWS CloudTrail is used to monitor API calls and Actions made on an AWS account.

Easily identify which user and accounts made the call to AWS:
 - **Where**: Source IP Address
 - **When**: EventTime
 - **Who**: User, UserAgent
 - **What**: Resource, region, action

CloudTrail is already logging by default and will collect logs for 90 days via Event History.

If you need more than 90 days you need to create a Trail.

Trails are output to S3 and do not have GUI like Event History. To analyze a Trail you'd have to use Amazon Athena.

## CLOUD WATCH ALARMS

A CloudWatch Alarm monitors a CloudWatch Metric based on a defined thresold. When alarm breaches (go outside the define thresold) than it change state.

CloudWatch Metric Alarm States
 - **OK**: The metric expression is withing the defined thresold.
 - **ALARM**: The metric expression is outside of the defined thresold.
 - **INSUFICIENT_DATA**
    - The alarm has just started
    - The metric is not available
    - Not enought data is available

When it changes state we can define what action it should tigger:
 - Notification
 - Auto Scaling Groups
 - EC2 Action

### Anatomy of an Alarm

The important parts are:
 - **Treshold Condition**: Defines when a datapoint is breached.
 - **Metric**: The actual data we are measuring
 - **Data Point**: Represents the metric's measurement at a given period
 - **Evaluation Periods**: Number of previous periods
 - **Period**: How often it checks to evaluate the Alarm
 - **Datapoints to Alarm**: 1 datapoint is breached in an evaluation period going back 4 periods. *This is what tiggers the alarm*

## CLOUD WATCH LOGS

Logs Streams represents a sequence of events from a application or instance being monitored. You can create Log Stream manually but generally this is automatically done by the service you are using.

Logs Events is a single event in a log file. Log events can be seen within a Log Stream.

### Cloud Watch Logs Insights

Cloud Watch Logs Insights enables you to interactively search and analyze your CloudWatch log data and has the following advantages:
 - More robust filtering than using a simple filter event in a Log Stream
 - Less burdensome then having to export logs to S3 and analyze them via Athena

Cloud Watch Insights supports all types of logs. It is commonly used via the console to do ad-hoc queries against logs groups.
 - Cloud Watch Insights has its own language called "Cloud Watch Insights Query Syntax".
 - A single requet can query uo to 20 logs groups
 - Queries times out after 15 minutes, if they are not completed
 - Queries results are available for 7 days
 - AWS provides sample queries that can get you started form common taks, and easy learning the Query Syntax
 - You can create and save your own queries to make future repetitive tasks easier

## CLOUD WATCH METRICS

A CloudWatch Metric represents a time ordered set of data points. Its a variable that its monitored over time.

CloudWatch comes with many predefined metrics that are generally name spaced by AWS Service.

For example in EC2 Per-instances Metrics are:
 - CPUUtilization
 - DiskReadOps
 - DiskWrite
 - DiskWriteBytes
 - NetworkIn
 - NetworkOut
 - NetworkPacketsIn
 - NetworkPacketsOut