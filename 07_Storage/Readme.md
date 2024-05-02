# STORAGE

## TYPES OF STORAGE SERVICES

The are 3 main types of storages:
 - **Elastic Block Store (EBS) - Block**: *When you need a virtual hard drive attached to a VM*
    - Data is split into evenly blocks. 
    - Directly accessed by the Operation System.
    - Suports only a single write volumen.
 - **Elastic File Storage (EFS) - File**: *When you need a file-share where multiple users or VMs need to access the same file*
    - File is stored with data and metadata. 
    - Multiple connections via network share.
    - Supports multiple reads, writting locks the file.
 - **Amazon Simple Storage Service (S3) - Objects**: *When you need to upload files, and not have to worry about underlying infrastructure. Not intended for high nput and outputs per second (IOPS)*
    - Objects stored with data, metadata and unique ID.
    - Scales with limited no limit or storage limit.
    - Supports multiple reads and writes (no locks).

## INTRODUCTION S3

Object-base storage is a data storage architecture that manage data as objects, as opposed to other storage architectures:
 - File system: Which manages data as a file and fire hierarchy
 - Block storage: Which manage data as blocks within sector and tracks

S3 provides you with **unlimited storage**. You don't need to worry about the underlying infrastructure. The S3 Console provides an interface for you to upload and access your data. 

You can store an individual object from 0 bytes to 5 terabytes in size.

**S3 Objects** contain your data. They are like files, and consist of:
 - Key: This is the name of the object
 - Value: The data itself made up of a sequence of bytes
 - Version ID: When versioning enable, the version of object
 - Metadata: Additional information attached to the object

**S3 Bucket** bold objects. Buckets can also have folders which in turn hold object. S3 is a universal namespaces so bucket names must be unique (like a domain name).

## S3 STORAGE CLASSES

AWS offers a range of S3 storage classes that trade Retrieval Time, Accesibility and Durability for cheaper storage.

From most to least expensive:
 - **S3 Standart (default)**: Fast! 99.9% of Availability. 11 9's Durability. Replicated across at least 3 AZs.
 - **S3 Intelligent Tiering**: Uses ML to analyze object usage and determine the appopiated storage class. Data is moved to the most cost-effective access tier, without any perfomance impact or added overhead.
 - **S3 Standar IA (Infrequent Access)**: Still fast! Cheaper is you access files less than once a month. Additional retrieval is fee is applied. 50% less than Standard (Reduce availability).
 - **S3 One-Zone-IA**: Still fast! Object only exist in one AZ. Availability is 99.5%, but is cheaper than Standart IA by 20% less (reduce durability). Data could get destroyed. A retrieval fee is applied.
 - **S3 Glacier**: For long term cold storage. Retrieval of data can take minutes to hours but the off is very cheap storage.
 - **S3 Glacier Deep Archive**: The lowest cost storage class. Data retrieval time is 12 hours.

*S3 Outpost has it own storage class*

## SNOW FAMILY

AWS Snow Family are storage and compute devices used to physically move data in or out the cloud. When moving data over the internet or private connection its to slow, dificult or costly. Data is delivered to S3.

The options are:
 - **Snowcone**: Comes in two sizes
    - 8TB of Storage (HDD)
    - 14TB of Storage (SSD)
 - **Snowball Edge**: Come generally in two types
    - Storage Optimized 80TB
    - Compute Optimized 39.5TB
 - **Snowmobile**: 
    - 100PB of storage

## STORAGE SERVICES

This are the storage services available:
 - **Simple Storage Service (S3)** is a serverless object storage service. You can upload very large files an un unlimited amount of files. You pay for what you store. You don't worry about the underlying file-system, op upgrading the disk size.
 - **S3 Glacier** is a cold storage service. It design as a low cost storage solution for archiving and long term-backup. It uses previos generation HDD drives to get that low cost. Its highly secure and durable.
 - **Elastic Block Store (EBS)** is a persistent block storage service. It a virtual hard drive in the cloud you attach to EC2 instances. You can choose differents kinds of hard drives (SSD, IOPS SSD, Throughtput HDD, Cold HDD)
 - **Elastic File System (EFS)** is a cloud-native NFS file system service. File storage you can mount to multiple EC2 instances at the same time. When you need to share files between multiple servers.
 - **Storage Gateway** is a hybrid cloud storage service that extends your on-premise storage to cloud.
   - **File Gateway** extends your local storage to AWS S3
   - **Volume Gateway** caches your local drives to S3 so you have a countinous backup of local files in the cloud
   - **Tape Gateway** stores files into virtual tapes for backing up your files on very cost effective long term storage
 - **Snow Family** are storage devices used to physically migrate large amound of data to the cloud.
   - **Snowball Edge** are briefcase size data storage services. 50-80TB
   - **Snowcone** is a very small version of Snowball that can transfer 8TB of data
   - **Snowmobile** is a cargo container filled with racks of storage and compute that is transported via semi-trailer tractor truck to transfer up to 100PB of data per trailer.
 - **AWS Backup** a fully managed backup services that makes is easy to centralize and automate the backup of data across multiple AWS Services (eg EC2, EBS, RDS, DynamoDB, EFS, Storage Gateway). You can create backup plans.
 - **CloudEndure Disaster Recovery** continously replicates your machines into a low cost staging area in your target AWS account and prefered Region enabling fast and reliable recovery in case of IT data center failures.
 - **Amazon FXs** is a feature rich and highly-perfomant file system. That can be used for Windows or Linux
   - **Amazon FXs for Windows File Server** uses the SMB protocol and allows you to mount FSx to Windows servers
   - **Amazon FXs for Lustre** uses Linux's Lustre file system and allows you to mount FXs to Linux Servers