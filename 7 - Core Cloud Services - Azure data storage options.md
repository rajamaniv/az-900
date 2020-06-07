# Core Cloud Services - Azure data storage options

## Introduction

### Learning objectives

- survey the data storage options in Azure
- discover how Azure data storage can meet your business demands
- compare Azure data storage with on-premises storage

## Benefits of using Azure to store data

- automated backup and recovery: mitigates the risk of losing your data if there is any unforeseen failure or interruption
- replication across the globe: copies your data to protect it against any planned or unplanned events, such as scheduled maintenance or hardware failures. You can choose to replicate your data at multiple locations across the globe
- support for data analysis: supports performing alanytics on your data consumption
- encryption abilities: data is encrypted to make it highly secure. Also have tight control over who can access the data
- multiple data types: Azure can store almost any type of data you need. Can handle video files, text files, even large binary files like virtual hard disks. Also many options for relational and NoSQL data
- data storage in virtual disk: can store up to 32 TB of data in its virtual disks.
- storage tiers: prioritize access to data based on frequently used versus rarely used information

### Types of data

1. Structured data: data that adheres to a schema, so all data has same fields or properties. Relies on keys to indicate how one row in a table relates to data in another row of other table. Also refer as relational data. Straightforward beause it's easy to center, query and analyze.

2. Semi structured data: doesn't fit neatly into tables, rows, and columns. Instead, uses tags or keys that organize and provide a hierarchy for the data. Also referred as non-relational or NoSQL data.

3. Unstructured data: emcompasses data that has no designated structure to it. For exemple, pdf document, JPEG, JSON, etc.

## How Azure data storage can meet your business storage need

### Azure SQL database

Relational database as a service (DaaS) based on the latest stable version of SQL Server database engine.

### Azure Cosmos DB

Globally distributed database service. Supports shema-less data, highly responsive, always on.

### Azure Blob storage

Can contain anything. Can store up to 8 TB of data for VMs.

### Azure Data Lake Storage

Contains both structured and unstructured data. Combines scalability and cost benefits of object storage with reliability and performance of the Bid Data file system capabilities.

### Azure Files

Fully managed file shares in the cloud that are accessible via the industry standard Server Message Block (SMB) protocol. Used to share files anywhere, diagnostic data, application data sharing

### Azure Queue

Service for storing large number of messages that can be accessed anywhere in the world. Can be used to build flexible applications and separate functions. Can use queue storage to:

- Create a backlog of work and to pass message between different Azure web servers
- Distribute load among different web servers/infrastructure and manage bursts of traffic
- Build resilienc against component failure when multiple users access your data at the same time

### Disk storage

Provides disks for virtual machines, application and other services. Disks can be managed or unmanaged by Azure. Comes in different sizes and performance levels (HDDs, SSDs).

### Storage tier

- hot storage tier: storing data accessed frequently
- cool storage tier: infrequently accessed and stored at least 30 days
- archive storage tier: data rarely accessed and stored at least 180 days with flexible latency requirements

### Encryption and replication

#### Encryption for storage services

1. Azure Storage Service Encryption (SSE): encrypts data before storing it and decrypts the data before returning it
2. Client side encryption: data encrypted and decrypted by client libraries

#### Replication for storage availability

Provides region and geographic replications to protect data against natural disaster, fire, floodings, etc.

## Comparison between Azure data storage and on-premise storage

### Cost effectiveness

You need to buy on prem hardware, which can be significant up-front. Azure data storage is pay as you go.

### Reliability

Can be challenging and expensing on premise, Azure provides all.

### Storage types

Azure has everything, no need to do everything yourself

### Agility

Azure has more flexibility
