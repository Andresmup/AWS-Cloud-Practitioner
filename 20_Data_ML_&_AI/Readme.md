# DATA, ML AND AI 

Artificial Inteligence (AI) are machines that performs jobs that mimic human behavior.

Machine Learning (ML) are machines that gets better at a task withput expliciting programming.

Deep Learning (DL) are machines that have and artificial neural network inpired by the human brain to solve complex problems.

Some AWS service are:
 - **Amazon SageMaker**: Is a fully managed service to build, train and deploy machine learning models at scale.
    - **Apache MXNet on AWS**: Open-source deep learning framework
    - **TensorFlow on AWS**: Open-source machine intelligence library
    - **Pytorch on AWS**: Open-source machine learning framework
 - **Amazon SageMaker Ground Truth**: Is a data-labelling service. Have humans labels a dataset that will be used to train machine learning models.
 - **Amazon Augmented AI**: Human-intervention review service. When SageMaker's uses machine learning to make a prediction is not confident it has the right awswer queue up the predicator for human review.

## ML AND AI SERVICES

This are some services and products in AWS:
 - **Amazon CodeGuru**: Is machine-learning code analysis service. CodeGuru perform code-reviews and will suggest chances to improve quality of code. It can show visual code profiles (show the internals of your code) to pinpoint perfomance.
 - **Amazon Lex**: Is a conversion interface service. With Lex you can build voice and text chatbots.
 - **Amazon Personalize**: Is a real-time recommendation service. Same technology used to make products recomendations to customers shopping on the Amazon platform.
 - **Amazon Polly**: Is a text-to-speech service. Upload your text and an audio file spoken by synthetised voice is generated.
 - **Amazon Rekognition**: Is a image and video recognition service. Analyze images and videos to detect and label objects, people, celebrities.
 - **Amazon Transcribe**: Is a speech-to-text service. Upload your audio file and it converted.
 - **Amazon Textract**: Is a OCR (extract text from scanned documents) service used when you have paper forms and you want to digitally extract the data.
 - **Amazon Translate**: Is a neural machine learning translation service. Uses deep learning models to deliver more accurate and natural sounding translations.
 - **Amazon Comprehend**: Is a Natural Language Processor (NLP) service. Find relationships between text to produce insights. Look at data such as Customer emails, support tickets, social media and makes predictions.
 - **Amazon Forecast**: Is a time-series forecasting service. Forecast bussiness outcomes such a product demand, resource need or financial perfomance.
 - **AWS Deep Learning AMIs**: Amazon EC2 instances pre-installed with popular deep learning frameworks and interfaces such as TensorFlow, Pytorch, Apache MXNet, Chainer, Gluon, Hovorod and Keras.
 - **AWS Deep Learning Contaniners**: Docker images instances pre-install with popular deep learning frameworks and interfaces such as TensorFlow, PyTorch and Apache MXNet.
 - **AWS DeepComposer**: Is a machine-learning enable musical keyboard.
 - **AWS DeepLens**: Is a video camera that uses deep-learning.
 - **AWS DeepRace**: A toy race car that can be powered with machine-learning to perform autonomous driving.
 - **Amazon Elastic Inference**: Allow you to attach low-cost GPU-powered acceleration to EC2 instances to reduce the cost of running deep learning by up to 75%.
 - **Amazon Fraud Detector**: Is a fully managed fraud detection a service. Identify potencially fraudulent online activities such as online payment fraud and the creation of fake accounts.
 - **Amazon Kendra**: Is a enterprise machine learning search engine service. Uses natural language to suggest answers to questions instead of just simple keyword matching.

## ML AND AI SERVICES EXTENDED 

This are some services AI and ML services in AWS:
 - **Amazon Bedrock**: Is a Large Language Model (LLM) cloud service offering to generate text and image responses
 - **Amazon CodeWhisper**: An AI code generator that will predict code to meet you use case.
 - **Amazon DevOps Guru**: Uses ML to analyze your operational data and applications metrics and events to detect operational abnormalities. *Is there is something wrong with your cloud operations?*
 - **Amazon Lookout for Equipment/Metrics/Vision**: Uses ML models for quality control and perfomanced automated inspections.
 - **Amazon Monitron**: Uses ML models to predict unplanned equipament downtime. Monito has an IOT sensor that captures vibrations and sensor data.
 - **AWS Neuron**: An SDK used to run deep learning workloads on AWS Inferentia and AWS Trainium based instance.

## BIG DATA AND ANALYTICS SERVICES

Bid Data is a term used to describe massive volumes of structured/ustructured data that is so large it is difficult to move and process using traditional database and software techniques.

AWS offers different services related to data, big data and data analytics:
 - **Amazon Athena**: Is a serverless interactive query service. It can take a bunch of CSV or JSON files in a S3 Bucket and load them into temporary SQL tables, so you can run SQL queries. *When you need to query CSV or JSON files*
 - **Amazon CloudSearch**: Is a fully managed full-text search service. *When you want add search to your website*
 - **Amazon ElasticSearch Service (ES)**: Is a managed ElasticSearch cluster. ElasticSearch is a open-source full-text search engine. It is more robust than CloudSearch but requires more server and operational maintaince.
 - **Amazon Elastic MapReduce (EMR)**: Is for data processing and analysis. It can be used for creating reports just like Redshift, but it more suited when you need to transform unstructured data into structured data on the fly.
 - **Amazon Kinesis Data Streams**: Is a real-time streaming data-service. Create Producers which send data to a stream. Multiple Consumers can consume data within a stream. Use for real-time analytics, click streams, ingesting data from a fleet of IOT devices.
 - **Amazon Kinesis Firehose**: Is a serverless and a simpler version of Data Streams, you pay-on-demand based on how much data is consumed though the stream and you don't worry about the underlying servers.
 - **Amazon Kinesis Data Analytics**: Allows you to run queries against data that is flowing through your real-time stream so you can create reports and analysis on emerging data.
 - **Amazon Kinesis Video Stream**: Allows you to analyze or apply processing real time streaming video.
 - **Managed Kafka Service (MSK)**: Is a fully managed Apache Kafka Service. Kafka is an open-source platform for building real time streaming data pipelines and applications. It is similar to Kinesis but with more robust functionalities.
 - **Amazon Redshift**: Is a petabyte-size data-warehouse. Data-warehouses are for Online Analytical Processing (OLAP). Datawarehouses can be expensive because data is "hot" which means we can run queries very complex and large and get the results very fast.
 - **Amazon QuickSight**: Is a Business Intelligent (BI) dashboard. You can create bussiness dashboards to power business decisions. It requires little to no programming knowledge and connect and ingest to many different type of databases.
 - **AWS Pipeline**: Automates the movement of data. You can reliably move data between compute and storage services.
 - **AWS Glue**: Is an Extract, Transform, Load (ETL) service. Moving data from one location to another and where you need to perform transformations before the final destination. Similar to Database Migration Service (DMS) but more robust.
 - **AWS LakeFormation**: Is a centralyzed, curated and secure repository that store all your data. A data lake is a storage repository that holds a vast amount of raw data in tis native format until it is needed.
 - **AWS Data Exchange**: Is a catalogue of third-party datasets. You can download for free subscribe or purchase datasets. (Eg: covid-19 food traffic data, IMDB TV and Movie data, Historical Wheather Data)

## AMAZON QUICKSIGHT

Amazon QuickSight is a Business Intelligence (Bi) Dashboard that allows you to ingest data from various AWS storage or datawarehouse services to quickly visualize business data with minimal programming or data formula kwoledge.

QuickSight uses SPICE (super-fast, parallel, in-memory, calculation engine) to achieve blazing fast performance at scale.

Some services included in QuickSight stack are:
 - **Amazon QuickSight ML Insights**: Detects anomalies, perform accurate forecasting, Generative Natural Language Narratives.
 - **Amazon QuickSight Q**: Ask question using natural language, on all your data and receive answer in seconds.

## ML AND DL FRAMEWORKS AND TOOLS

With SageMaker you can use some ML and DL frameworks, this are some of them:
 - **Apache MXNet**: Adopted by AWS, supports both imperative and symbolic.
 - **PyTorch**: Optimized tensor library for deep learning using GPUs and CPU.
 - **Tensor Flow**: Low-level machine learning framework.
 - **Keras**: High-level machine learning framework built on top and ships with Tensor Flow.
 - **Apache Spark**: Unified analytics engine for large-scale data processing.
   - **Spark ML**: Uniform set of high-level APIs that helps user create and tune practical machine leargning pipelines.
 - **Chainer**: Powerful, flexible and intuitive deep learning framework, supports CUDA.
 - **Hugging Face**: An AI Community of ML Models and datasets.

### Apache MXNet

Apache MXNet is a deep learning machine learning framework which supports many different programming languagues (Python, Java, R, Go, etc.). Some features of MXNet are:
 - **Scalable**: Designed for distributed cloud infrastructure.
 - **Flexible**: Supports both imperative and symbolic programming.
 - **Portable**: Can be used on low-end or edge devices and on serverless compute.
 - **Multiple**: Supports multiple programming languages.

AWS has made ApacheMXNet their ML framework of choice. There is a lot of support to use ApacheMXNet within AWS SageMaker and AWS ML containers.

MXNet has two high-level interfaces.
 - Gluon API: Imperative programming.
 - Module API: Symbolic programming.