# Ml Engineering

> a data engineer is someone who has specialized their skills in creating software
solutions around big data.

Before we can do data science we need to setup the infrastructure

![alt text](images/pyramid.png "Logo Title Text 1")

At early stage start-ups: the primary analytic focus is to implement logging, to build ETL processes, to model data and design schemas so data can be tracked and stored. The goal here is focused on building the analytics foundation rather than analysis itself
At mid-stage growing start-ups: Since the company is growing, the data is probably growing too. The data platform needs to adapt, but with the foundation laid out already, there will be a natural shift to insight generation. Unless the company leverages Data Science for its strategic differentiation to start with, many analytics work are around defining KPI, attributing growth, and finding the next opportunities to grow
Companies who achieved scale: When the company scales up, data also scales up. It needs to leverage data to create or maintain competitive edge. e.g. Search results need to be better, recommendations need to be more relevant, logistics or operations need to be more efficient — this is the time where specialist like ML engineers, Optimization experts, Experimentation designers can play a huge role in stepping up the game.


##### Clean and wrangle data into a usable state

> Data engineers make sure the data the organization is using is clean, reliable, and prepped for whatever use cases may present themselves. 
Data engineers wrangle data into a state that can then have queries run against it by data scientists.

> Data Formats should be easy for computers to parse, people to read and widely used by systems in production. 
The computations we perform must be reproducible and tweakable. Data Pipelines need to be documented. 

##### Build and maintain the organization’s data pipeline systems

> a data pipeline is nothing but a series of operations, when streamed together, helped us to automatically capture, munged, aggregated data on a recurring basis.

> Creating a data pipeline may sound easy or trivial, but at big data scale, this means bringing together 10-30 different big data technologies. 
More importantly, a data engineer is the one who understands and chooses the right tools for the job. 

> A data engineer is the one who understands the various technologies and frameworks in-depth, and how to combine them to create solutions to enable a 
company’s business processes with data pipelines.

read more:
Building Data Pipelines with Python — Katharine Jarmul explains how to build data pipelines and automate workflows.


-----------------------------------

#### Cloud Data Storage  
  storage engines (e.g. S3, HDFS, HBase, Kudu)

#### Data Modelling  

| Algorithm           | Notes     | 
|---------------------|-----------|
| Relational Data Models (Postgres)    |           |
| Document Model - NoSQL Data Models (mongoDB)     |           |
| Graph Model         |           |


#### Cloud Data Warehouses 
    - build an ETL pipeline that extracts data from S3, stages them in Redshift, and transforms data into a set of dimensional tables for their analytics team.

### Data Ingestion  

### Large-Scale Processing 
- Batch Processing 
- Stream Processing 
 Spark Streaming , Kafka, AWS Kinesis (Realtime Streaming)  
 
 
#### Data Lakes with Spark 
    - Intro to big data eco system 
    - Data Wrangling with Spark 
    - Setting up Spark Cluster with AWS 
    - Debugging and Optimisation
    - Intro to data lakes 

### Distributed training for large scale datasets
   
#### Data Pipelines with Airflow 
    - Data Pipelines Intro
    - Data Quality 
    - Production Data Pipelines
    
### Primer on distributed systems (bonus)

    Replication
    Partitioning
    Transactions 
    Consistency and Consensus

### Containers 

Kubernetes, Docker

### REST API (Flask etc) 
 
#### Guides: 


| Notebook                 | Description | Code | Blog | 
|--------------------------|-------------|------|------|
| Speeding up Numpy        | Learn how to get optimal performance out of NumPY | | [Notes](https://asjadkhan.ghost.io/speeding-up-numpy/)          |
| Spark Tutorial           | Learn large scale Data Engineering with Spark          |     | [Notes](https://asjadkhan.ghost.io/ghost/#/editor/post/5f39c86010c8da00398dc9ce)     |
| Topic Modeling in Spark  | LSI Modeling in Spark to Extract document topics | [Python_code](https://gist.github.com/asjad99/e87a695df10b0859ee943b8e661f0fc3)  | |
|


### resources:

- Stanford Data Engineering: 
https://docs.google.com/document/d/1b9iuZiDEGVLHyMmnf6w2y1aN6yWQhAyqk3GHlpI9q6M/edit 
- Designing Data-Intensive Applications
- https://github.com/andkret/Cookbook
- Is dataFrame just a table
- https://www.mikealche.com/software-development/a-humble-guide-to-database-schema-design
- SQL Mastery
    
   
(AIEngineering)[https://www.youtube.com/channel/UCwBs8TLOogwyGd0GxHCp-Dw]  
