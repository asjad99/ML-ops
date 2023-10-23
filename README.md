### Notes on MLOPS

<img width="586" alt="Screenshot 2023-05-16 at 8 10 28 pm" src="https://github.com/asjad99/Engineering-Data-Products/assets/3470924/c6a9f137-bb9e-447a-bd32-904c552a0147">



 ML Engineering = Machine learning systems design + Data Engineering + ML Ops 


- We present an iterative framework for designing real-world machine learning systems. 
-  We want to take a system level view of things and architect a solution based on  business requirements where the end goal of this framework is to build a system that is deployable, reliable, and scalable.
- Enterprise grade ML, a term mentioned in [a paper put forth by Microsoft](https://arxiv.org/abs/1909.00084), refers to ML applications where there is a high level of scrutiny for data handling, model fairness, user privacy, and debuggability. While toy problems that data scientists solve on laptops using a csv dataset could be intellectually challenging, they are not enterprise grade machine learning problems.
- In deployment (via containers or spark applications, for example), governance becomes paramount, especially in regulated environments. Data lineage, data versioning, model versioning, model explainability, model monitoring are all front and center.
- Examples of System Design/Data Engineering tasks include: 
  - Ingest data from a data source
  - Build and maintain a data warehouse 
  - create a data pipeline 
  - create an analytics table for a specific use case 
  - migrate data to cloud 
  - schedule and automate pipelines 
  - backfill data 
  - debug data quality issues 
  - optimize queries 
  - design a database 


Overall ML Engineering entails the following core activities: 

| Task/Topic                                         | Description of sub-tasks/Topics                              | Selected Tools                                            | Theory/Notes                                                 | Example Code                                                 |
| -------------------------------------------------- | :----------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Frame the problem and Acquire data                 | 1. Identify areas of business that can benifit from machine learning <br /> 2. Translating a business problem into a machine learning problem. e.g supervised learning <br />3. Pick a sucess criteria - How would performance be measured? <br /> |                                                           |                                                              |                                                              |
| Data Storage and Modeling (revise)                 | 1.  Acquire relevant data - estimate space and engineering effort - setup a data version control system <br /> 2. Creating a data model  to store data and facilitating access by other team members  <br />3.  Setup Cloud Data Warehouses - Kimball methodology.  <br />4. Design a database - Relational Data Models (Postgres) <br /> 5. Document Model - NoSQL Data Models | POSTGRES, mongoDB,Google Big query , AWS - S3             |                                                              |                                                              |
| Data Acquizition                                   | Ingest data from a data source e.g Querying data- Pulling data from a database (SQL or NOSQL) or Call S3 API | POSTGRES, mongoDB, AWS - S3                               |                                                              |                                                              |
| Data Exploration                                   | - Which features are categorical/Numerical? <br /> - Which features contain blank, null or empty values?<br /> - What are the data types for various features?<br /> - What is the distribution of numerical feature values across the samples?<br />What is the distribution of categorical features?<br />Study correlation between a given target variable and all other variables<br />Visual Data Analysis: <br />Applying a dimensionality reduction on a dataset to facilitate model training or gather insights | Pandas, Matplotlib                                        |                                                              |                                                              |
| Data Cleaning                                      | Handle Missing values<br />Handle Outliers/erronous data<br />Get into Tidy data | Pandas, Apache Spark                                      | [Spark Notes](https://asjadkhan.ghost.io/ghost/#/editor/post/5f39c86010c8da00398dc9ce) | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) |
| Data Preparation/Feature Engineering               | Feature Selection<br />Feature Encoding <br /> Add new promosing transformations of features <br /> Aggregate features into promosing new features |                                                           | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) |
| Training models                                    | Using one of the following methods: Linear Regression, Logistic Regression, Decision Trees, Random Forest, XGBoost, Support Vector Machines, K-means, K-Nearest Neighbors, Neural Networks, Principal Component Analysis, Naive Bayes Classifier, Lasso/Ridge regression, etc. <br />Implementing evaluation metrics such as accuracy, precision, recall, intersection over union, or mean average precision (mAP)Grid Search and Cross Validation | scikit-learn                                              | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) | [ML_Course](https://github.com/asjad99/Machine-Learning-GYM) |
| Training Deep Learning Models                      | Using deep learning for a domain-specific application such as fraud detection, text summarization, machine translation, speech recognition, or object classification, detection, or segmentation <br /> Tuning hyperparameters involved in neural network optimization <br /> Organizing experiments to get results in the shortest time period  <br /> Setting up hyperparameter search experiments using tools such as AutoML | TensorFlow, and PyTorch                                   |                                                              |                                                              |
| Data Pipelines                                     | Building and maintaining the organization’s data pipeline systemsimplementing ETL (or ELT) best practices at scale.  e.g build an ETL pipeline that extracts data from S3, stages them in Redshift, and transforms data into a set of dimensional tables for their analytics team.`Designing an ETL system | Airflow                                                   |                                                              |                                                              |
| Distributed or Accelerating training               | Setting up code to train a model on multiple machines in parallel |                                                           |                                                              |                                                              |
| Stream Processing                                  | Converting a continuous feature into a categorical feature using bucketing | Spark Streaming , Kafka, AWS Kinesis (Realtime Streaming) |                                                              |                                                              |
| Setting up a cloud environment to deploy the model | Converting prototyped code into production code <br />Mastering cloud tools and infrastructure Preparing files (usually model architecture and parameters) for deployment <br />Encrypting files that store model parameters, architecture, and data <br />Setting up load-balancing requirements with engineers in charge of AI Infrastructure <br />Pruning or quantizing a model so it fits memory requirements | AWS                                                       |                                                              |                                                              |
| Present / Launch Solution                          | Building APIs for an application to use a model -  Setting up HTTP RESTful API services to facilitate productionize <br /> Setting up authorization and authentication to access the API | **Flask etc**                                             |                                                              |                                                              |

---



- 

  

----



### Nice to have skills: 



| Task                                            | Description                                                  |
| ----------------------------------------------- | ------------------------------------------------------------ |
| **Containers**                                  | KubernetesDocker                                             |
| **Create** **Data Lakes with Spark**            | Data Wrangling with Spark ` Setting up Spark Cluster with AWS Debugging and Optimisation`Intro to data lakes ` |
| **Feature Store**                               | kind of an in-memory database such that at real time inference we have model features readily available |
| **Speeding up model prediction time**           | - Applying techniques such as pruning, quantization, or compression to reduce memory requirements - Running inference speed vs. accuracy experiments on a model |
| **Primer on distributed systems**               | ReplicationPartitioningTransactionsConsistency and Consensus |
| **Deal with constantly shifting distributions** | Data Drift :your real world dataset would not always have same distribution. For example the way a person shops in spring would be different than that of winter. So when you train a model on spring data set and deployed it you cant test it when winters come. So the data type is drifted away from normal and this is something to keep an eye Model Drift:now when your model is deployed and you start making predictions online (realtime) with passage of time due to data drift your model performance will de-grade and you would need to keep track of those changes. you would need to re train your model on latest dataset and then re-deploy it |
