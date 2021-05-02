# End-to-End AI Project Development 

### About: 
With 2,3 trillion gigabytes of data created each day, companies have access to a broad range of information on their users, market and much more.
This Data allows them to constantly improve their product/service. 

- At early stage start-ups: the primary analytic focus is to implement logging, to build ETL processes, to model data and design schemas so data can be tracked and stored. The goal here is focused on building the analytics foundation rather than analysis itself
- At mid-stage growing start-ups: Since the company is growing, the data is probably growing too. The data platform needs to adapt, but with the foundation laid out already, there will be a natural shift to insight generation. Unless the company leverages Data Science for its strategic differentiation to start with, many analytics work are around defining KPI, attributing growth, and finding the next opportunities to grow
- Companies who achieved scale: When the company scales up, data also scales up. It needs to leverage data to create or maintain competitive edge. e.g. Search results need to be better, recommendations need to be more relevant, logistics or operations need to be more efficient — this is the time where specialist like ML engineers, Optimization experts, Experimentation designers can play a huge role in stepping up the game.

Before we can do data science we need to setup the infrastructure

![alt text](images/ml_hierarchy_of_needs.png "Logo Title Text 1")


Developing an AI project development life cycle involves five distinct tasks:

-  Data engineering: People responsible for data engineering prepare data
and transform data into formats that other team members can use.
-  Modeling: People assigned to modeling look for patterns in data that can
help a company predict outcomes of various decisions, identify business risks
and opportunities, or determine cause-and-effect relationships.
-  Deployment: People in charge of deployment take a stream of data, combine it
with a model, and test the integration before putting the model into production.
-  Business analysis: Team members responsible for business analysis evaluate a deployed
model’s performance and business value and adjust accordingly to maximize benefit or abandon unproductive models.
-  AI infrastructure: People who work in AI infrastructure build and maintain reliable, fast, secure, and scalable software
systems to help people working in data engineering, modeling, deployment and business analysis.



| Task/Topic                                         | Description of sub-tasks/Topics                              | Selected Tools                                            | Theory/Notes                                                 | Example Code                                                 |
| -------------------------------------------------- | ------------------------------------------------------------ | --------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                    | Translating a business problem into a machine learning problemPick a sucess criteria |                                                           |                                                              |                                                              |
| Data Storage and Modeling                          | Creating a data model  to store data and facilitating access by other team membersSetup Cloud Data Warehouses - Kimball methodology. design a database - Relational Data Models (Postgres)Document Model - NoSQL Data Models | POSTGRES, mongoDB, AWS - S3                               |                                                              |                                                              |
| Data Acquizition                                   | Ingest data from a data source e.g Querying data- Pulling data from a database (SQL or NOSQL) or Call S3 API | POSTGRES, mongoDB, AWS - S3                               |                                                              |                                                              |
| Data Exploration                                   | Which features are categorical/Numerical?Which features contain blank, null or empty values?What are the data types for various features?What is the distribution of numerical feature values across the samples?What is the distribution of categorical features?Study correlation between a given target variable and all other variablesVisual Data Analysis: Applying a dimensionality reduction on a dataset to facilitate model training or gather insights | Pandas, Matplotlib                                        |                                                              |                                                              |
| Data Cleaning                                      | Handle Missing valuesHandle Outliers/erronous dataGet into Tidy data | Pandas, Apache Spark                                      | [Spark Notes](https://asjadkhan.ghost.io/ghost/#/editor/post/5f39c86010c8da00398dc9ce) | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) |
| Data Preparation/Feature Engineering               | Feature SelectionFeature Encoding                            |                                                           | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) |
| Training models                                    | Using one of the following methods: Linear Regression, Logistic Regression, Decision Trees, Random Forest, XGBoost, Support Vector Machines, K-means, K-Nearest Neighbors, Neural Networks, Principal Component Analysis, Naive Bayes Classifier, Lasso/Ridge regression, etc.Implementing evaluation metrics such as accuracy, precision, recall, intersection over union, or mean average precision (mAP)Grid Search and Cross Validation | scikit-learn                                              | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) |
| Training Deep Learning Models                      | Using deep learning for a domain-specific application such as fraud detection, text summarization, machine translation, speech recognition, or object classification, detection, or segmentation Tuning hyperparameters involved in neural network optimization Organizing experiments to get results in the shortest time period Setting up hyperparameter search experiments using tools such as AutoML | TensorFlow, and PyTorch                                   |                                                              |                                                              |
| Data Pipelines                                     | Building and maintaining the organization’s data pipeline systemsimplementing ETL (or ELT) best practices at scale.  e.g build an ETL pipeline that extracts data from S3, stages them in Redshift, and transforms data into a set of dimensional tables for their analytics team.`Designing an ETL system | Airflow                                                   |                                                              |                                                              |
| Distributed or Accelerating training               | Setting up code to train a model on multiple machines in parallel |                                                           |                                                              |                                                              |
| Stream Processing                                  | Converting a continuous feature into a categorical feature using bucketing | Spark Streaming , Kafka, AWS Kinesis (Realtime Streaming) |                                                              |                                                              |
| Setting up a cloud environment to deploy the model | Converting prototyped code into production code Mastering cloud tools and infrastructure Preparing files (usually model architecture and parameters) for deploymentEncrypting files that store model parameters, architecture, and dataSetting up load-balancing requirements with engineers in charge of AI InfrastructurePruning or quantizing a model so it fits memory requirements | AWS                                                       |                                                              |                                                              |
| Building APIs for an application to use a model    | Setting up HTTP RESTful API services to facilitate communications between software components - Setting up authorization and authentication to access the API | **Flask etc**                                             |                                                              |                                                              |



----


### Data Ingestion 

### Resources:

- Stanford Data Engineering: 
https://docs.google.com/document/d/1b9iuZiDEGVLHyMmnf6w2y1aN6yWQhAyqk3GHlpI9q6M/edit 
- Designing Data-Intensive Applications
- https://github.com/andkret/Cookbook
- Is dataFrame just a table
- https://www.mikealche.com/software-development/a-humble-guide-to-database-schema-design
- SQL Mastery
  
   

(AIEngineering)[https://www.youtube.com/channel/UCwBs8TLOogwyGd0GxHCp-Dw]  


#### Guides: 

Data Drift :
your real world dataset would not always have same distribution. For example the way a person shops in spring would be different than that of winter. So when you train a model on spring data set and deployed it you cant test it when winters come. So the data type is drifted away from normal and this is something to keep an eye 

Model Drift:
now when your model is deployed and you start making predictions online (realtime) with passage of time due to data drift your model performance will de-grade and you would need to keep track of those changes. you would need to re train your model on latest dataset and then re-deploy it
