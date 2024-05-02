# DATABASE

## WHAT IS A DATABASE?

A database is a data-store that stores semi-structured and structured data.

A database is more complex data store because it requires using formal design and modeling techniques.

Databases can be generally categorized as either:
 - **Relational Databases**: Structured data that strongly represents tabular data (table, rows and columns)
    - Row-oriented or Columnar-oriented
 - **Non-relational Databases**: Semi-structured that may or may not distantly resemble tabular data

Databases have a rich set of functionality:
 - Specialized language to query (retrieve data)
 - Specialized modeling strategies to optimize retrieval for different use cases
 - More fine tune control over the transformation of data into usefull data structures and reports

Normally databases infers someone is using a relational row-oriented data store

## WHAT IS A DATA WAREHOUSE?

A relational **datastore designed for analityc** workloads, which generally is **column-oriented data-store**

Companies will have terabytes and millions of rows of data and they need a fast way to be able to produce analytics reports.

Data warehouses generally perform aggregation:
 - Aggregation is grouping data (eg: total, average)
 - Data warehouse are optimized around columns since they need quickly agregate column data

Data warehouses are generally design to be HOT, which means they can return queries very fast even though the have vast amounts of data.

Data warehouses are infrequently accessed meaning they aren't intended for real-time reporting but maybe once or twice a day or once a week, to generate business user reports.

A data warehouse needs to consume data from a relational databases on a regular basis or if the ingestion is made by other source be prepared by an ELT process.

## WHAT IS A KEY/VALUE STORE?

A key-value database is a type of non-relational database (NoSQL) that uses a simple key-value method to store data.

Key values stores are dumb and fast. They generally lack features like:
 - Relationships
 - Indexes
 - Aggregation

A key/value stores a unique key alongside a value.

| Key | Value |
| --- | --- |
| Bobby | 010110101001 |
| Katty | 101011001101 |
| Liam | 011011001100 |

A simple key/value store will interpret this data resembling a dictionary (aka associative arrays or hash)

| Key | Value |
| --- | --- |
| Bobby | {species: "dog", sound: "guau guau"} |
| Katty | {species: "cat", sound: "miau miau"} |
| Silver | {species: "horse", habitat: "farm"} |

A key/value store can resemble tabular data, it does not have to have the consistent columns per row (hence is schemaless)

| Name (Key) | Species (Value) | Sound (Value) | Habitat (Value) |
| --- | --- | --- | --- |
| Bobby | dog | guau guau |  |
| Katty | cat | miau miau |  |
| Silver | horse |  | farm |

Due to their simple design they can scale well beyond a relational database

## WHAT IS A DOCUMENT STORE?

A document store is a NOSQL database that stores documents as its primary data structure. A document could be a XML but more commonly is JSON or JSON-like.

Document stores are sub-class of key/value stores.

The components of a document store compared to Relational Database.

Database (RDBMS) -> Database (Document):
 - Tables -> Collection
 - Rows -> Documents
 - Columns -> Fields
 - Indexes -> Indexes
 - Joins -> Embedding and Linking

## NOSQL DATABASE SERVICES

### DynamoDB

DynamoDB is a serverless NoSQL key/value and document database. It is designed to scale to billions of records with guarantedd consistent data return in at least a second. You don't have to worry about managing shards.

DynamoDB is AWS's flagship database service meaning wherever you think of a database service that just scales, is cost effective and very fast we should think DynamoDB. *When we want a massively scalable database*

### DocumentDB

DocumentDB is a NoSQL document database that is MongoDB compatible. *When you want a MongoDB database*

### Amazon Keyspaces

Amazon Keyspaces is a fully managed Apache Cassandra database. Cassandra is an open-source NoSQL key/value database similar to DynamoDB in that is a columnar store database but has some additional functionality. *When we want to use Apache Cassandra*

## RELATIONAL DATABASE SERVICES

### RDS

Relational Database Service (RDS) is a relational database service that supports multiple SQL engines. Relational is synonimous with SQL and Online Transactional Processing (OLTP). Relational database are the most commonly used type of database among tech companies and starts-ups.

RDS supports the following SQL Engines:
 - **MySQL**: The most popular open-source SQL database that was purchased and now owned by Oracle.
 - **MariaDB**: When Oracle bought MySQL. MariaDB made a fork of MySQL was made under a different open-source license.
 - **PostgresSQL (PSQL)**: Most popular open-source SQL database among developers. Has rich-features over MySQL but at added complexity.
 - **Oracle**: Oracle's propietary SQL database. Well used by Enterprise companies. You have to buy a license to use it.
 - **Microsoft SQL Server**: Microsoft's propietary SQL database. You have to buy a license to use it.
 - **Aurora** AWS fully managed database

### Aurora

Aurora is a fully managed database of either MySQL (5x faster) and PSQL (3x faster) database. *When you want a highly available, durable, scalable and secure relational database for Postgres or MySQL*

#### Aurora Serverless

Aurora Serverless is the serverless on-demand version of Aurora. *When you want "most" of the benefits of Aurora but can trade to have cold-starts or you don't have lots of traffic demand.

### RDS on VMWare

RDS on VMWare allows you to deploy RDS supported engines to on on-premise data-center. The datacenter must be using VMWare for server virtualization. *When you want databases managed by RDS on you own datacenter*

## OTHER DATABASE SERVICES

### RedShift 

RedShift is a petabyte-size data-warehouse. Data-warehouses are for Online Analytical Processing (OLAP). Data warehouses can be expensive because the are keeping data "hot". Meaning that we can run a very complex query and get fast a very large amount of data.

### ElastiCache

ElastiCache is a managed database of the in-memory and caching open-source databases Redis or Memcached. *When you need to improve the perfomance of application by adding a caching layer in-front of web-server or database*

### Neptune

Neptune is a managed graph database. Data is represented as interconnected nodes. *When you need to understand the connection between data (eg Mapping fraud rings or Social media relationship)*

### Amazon Timestreams

Amazon Timestreams is a fully managed time series database. Think of devices that sends lots of data that are time sensitive such as IoT devices. *When you need to measure how things change over the time*

### Amazon Quantum Ledged Database

Is a fully managed ledger database that provides transparent, inmmutable and cryptographically variable transaction logs. *When you need to record history of financial activities that can be trusted*

### Database Migration Service (DMS)

DMS is a database migration service. You can migrate from:
 - On-premise database to AWS
 - From two databases in different AWS accounts using different SQL engines
 - From an SQL to NoSQL database