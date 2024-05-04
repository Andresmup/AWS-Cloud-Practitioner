# APPLICATION INTEGRATION

Application integration is the process of letting two independent applications to comunicate and work with each other, commonly facilitated by an intermediate system.

Cloud workloads encourage systems and services to be loosely coupled and so AWS has many services for the specific purpose of application integration.

The common systems or design patters utilized for Application Integration generally are:
 - Queueing
 - Streaming
 - Pub/Sub
 - API Gateways
 - State Machine
 - Event Bus

## QUEUEING

A messaging system is used to provide asynchronous communication and decouple processes via messages / events. From a sender and receiver (producer and consumer).

A queueing system is a messaging system that generally will delete messages once they are consumed. Simple comunication. Not real time. Have to pull. Not reactive.

### Simple Queueing Service (SQS)

Simple Queueing Service (SQS) Is a fully managed queueing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. (eg: use case is you need to queue up transactions emails to be sent)

## STEAMING 

Streaming is message system where multiple consumers can react to events (messages). Events live in the stream for long term periods of time, so complex operations can be applied. It's in real time.

### Amazon Kinesis

Amazon Kinesis is the AWS fully managed solution for collecting, processing and analyzing streaming data in the cloud.

## PUB/SUB

Publish-Subscribe (Pub/Sub) pattern is commonly implemented in messaging systems.

In a pub/sub system the sender of messages (publishers) do not send their messages directly to the receivers. They instead send their messages to an event bus. The event bus categorizes their messages into groups.

Then receivers of messages (subscribers) subscribe to these groups. Whenever new messages appear within their subscriptions the messages are immediately delivered to them.

Some aspects are:
 - Publisher have no knowledge of who their subscribers are
 - Subscribers do not pull for messages
 - Instead messages are automatically and immediatelly pushed to subscribers
 - Messages and events are interchangeables terms in pub/sub

### Simple Notification Service (SNS)

Simple Notification Service (SNS) is a highly available, durable, secure, fully managed pub/sub messaging service that enables you to decouple microservices, distributed systems and serverless applications.

## API GATEWAY

An API Gateway is a program that sits between a single-entry point and multiple backends. API Gateway allows for throttling, logging, routing logic or formatting of the request and response.

### AWS API Gateway

AWS API Gateway is a solution for creating secure APIs in your cloud enviroment at any scale. Create APIs that acts as a front door for applications to access data, bussiness logic or functionality from back-end services.

## STATE MACHINE

A state machine is an abstract model which decide how one states moves to another based on a series of conditions. A state machine is similar to a flow chart.

### Step Function

AWS Step Function is a services to coordinate multiple AWS services into a serverless workflow. 

A graphical console to visualize the components of your application as a series of steps.

Automatically triggers and tracks each step, and retries when there are errors, so your application executes in order and as expected every time.

Logs the state of each step, so when things go wrong you can diagnose and debug problems quickly.

## EVENT BUS

An event bus receives events from a source and routes events to a target based on rules

### EventBridge

EventBridge is a serverless event bus service that is used for application integration by streaming real-time data to your applications

Some characteristics of the EventBridge are:
 - **Event Bus**: Holds event data, define rules on an event bus to react to events.
    - **Default Event Bus**: An AWS account has a default event bus
    - **Custom Event Bus**: Scoped to multiple accounts or other AWS accounts
    - **SaaS Event Bus**: Scoped to third-party SaaS providers
 - **Producers**: AWS Services that emit events
 - **Partner Sources**: Third-party apps that can emit events to an event bus
 - **Event**: Data emmited by services. JSON objects that travel (stream) within the event bus
 - **Rules**: Determines what events to capture and pass to targets (100 rules per bus)
 - **Target**: AWS Services that consume events (5 target per bus)

## APPLICATION INTEGRATION SERVICES

This are the AWS Services used fpr application integration:
 - **Simple Notification Service (SNS)**: Is a pub/sub messaging system. Sends notifications via various formats such as Plain-text email, HTTP/s (webhooks), SMS (text messages), SQS and Lambda. Push messages which then are sent to subscribers.
 - **Simple Queueing Service (SQS)**: Is a queueing message service. Send events to a queue. Other applications pull the queue for messages. Commonly used for background jobs.
 - **Step Functions**: Is a state machine service. It coordinate multiple AWS services into a serverless workflow. Easily share data among Lambdas. Have a group of lambdas wait for each other. Create logical steps. Also works with Fargate tasks.
 - **EventBridge (CloudWatch Events)**: Is a serverless event bus that makes it easy to connect applications together from your own application, third party services and AWS services.
 - **API Gateway**: Is a fully managed service for developers to create, publish, maintain, monitor and secure APIs. You can create API endpoints and route them to AWS services.
 - **AppSync**: Is a fully managed GraphQL service. GraphQL is an open-source agnostic query adaptor that allows you to query data from many different sources.
 - **Kinesis**: Is a real-time streaming data service. Create Producers which send data to a stream. Multiple consumers can consume data within the stream. Use for real-time analytics, click streams, ingesting data from a fleet of IOT Devices.
 - **Amazon MQ**: Is a managed message broker service that uses Apache Active MQ.
 - **Managed Kafka Service (MSK)**: Is a fully managed Apache Kafka service. Kafka is an open-source platform for building real-time streaming data pipelines and applications. Similar to Kinesis but more robust.