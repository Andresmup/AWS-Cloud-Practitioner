# SERVERLESS

Serverless architecture generally describe fully managed cloud services. The classification of a cloud service being serverless is not a Boolean answer (yes or no), but a answer of scale where a cloud service has a degree of serverless (similar to energy rating levels, some services are more serverless than others).

When the underlying servers, infrastructure and operating system (SO) is taken care of by the Cloud Service Provider. Serverless is generally by default highly available, scalable and cost-effective (you pay for what you use).

A serverless service could have all or most of the following characteristics:
 - Highly elastic and scalable
 - Highly available
 - Highly durable
 - Secure by default
 - Pay-for-value (you don't pay for idle servers)
    - Abstracts away the underlying infrastructure and are billed based on the execution of your business task
    - Serverless can scale-to-zero meaning when not in use the serverless resources cost nothing

## SERVERLESS SERVICES

This are the most important AWS serverless services:
 - **DynamoDB**: Is a serverless NoSQL key/value and document database. It is designed to scale to billions of records with guaranteed consistent data return in at least one second. You don't have to worry about managing shards.
 - **S3**: Is a serverless object storage service. You can upload very large and an unlimited amount of files. You pay for what you store. You don't worry about underlying file-system or upgrading the disk size.
 - **ECS Fargate**: Is serverless orchestation container service. It is the same as ECS except you pay-on-demand per running container. With ECS you have to keep a EC2 server running even if you have no containers running; in ECS Fargate AWS manages the underlying server, so you don't have to scale or upgrade the EC2 server.
 - **AWS Lambda**: Is a serverless functions service. You can run code without provisioning or managing servers. You upload small pieces of code, choose how much memory and how long the function is allowed to run before timing out. You are charged based on the runtime of the serverless function rounded to the nearest 100ms.
 - **State Functions**: Is a state machine. It coordinates multiple AWS services into serverless workflows. Easily share data among Lambdas. Have a group of lambdas wait for each other. Create logical steps. Also works with Fargate tasks.
 - **Aurora serverless**: Is the serverless on-demand version of Aurora. *When you want "most" of the benefits of Aurora but can trade to have cold-starts or you don't have lots of traffic demand.