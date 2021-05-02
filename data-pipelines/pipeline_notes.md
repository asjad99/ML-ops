### Data Pipelines 

Data Engineers are responsible for:

- Building and maintaining the organization’s data pipeline systems
- Design the big data infrastructure and prepare it to be analyzed.
- Build complex queries to create “pipelines”.
- Arrange any problems in the programmed system.

> “Data pipelines are sequences of processing and analysis steps applied to data for a specific purpose. They’re useful in production projects, and they can also be useful if one expects to encounter the same type of business question in the future, so as to save on design time and coding. For instance, one could remove outliers, apply dimensionality reduction techniques, and then run the result through a random forest classifier to provide automatic classification on a particular dataset that is pulled every week.”


A data pipeline is nothing but a series of operations, when streamed together, helped us to automatically capture, munged, aggregated data on a recurring basis. Creating a data pipeline may sound easy or trivial, but at big data scale, this means bringing together 10-30 different big data technologies. 

-  A data engineer is the one who understands the various technologies and frameworks in-depth, and how to combine them to create solutions to enable a 
company’s business processes with data pipelines.
-  Knowledge of job orchestration and scheduling. Any experience with Airflow, Luigi or Oozie.


![alt text](ml_pipeline.png "Logo Title Text 1")



* read more: * 
Building Data Pipelines with Python — Katharine Jarmul explains how to build data pipelines and automate workflows.

 
 --------





- What are data pipelines and how are they used?
- What are a few examples of data pipeline?
- What is data validation?
- Why is data validation an important part of data pipelines?



----------

#### What is a data Pipeline? 


    - A series of steps in which data is processed.
    - Depending on the data requirements for each step, some steps may occur in parallel 
    - Data pipelines occur on a schedule e.g once a hour
    - Data Pipelines often perform Extract Transform Load (ETL) and Extract Load Transform (ELT):
    - schedules or triggers/events can be used to execute a data pipeline (e.g depending on how often customer need insights) 

####  Extract Transform Load (ETL) and Extract Load Transform (ELT):

> "ETL is normally a continuous, ongoing process with a well-defined workflow. ETL first extracts data from homogeneous or heterogeneous data sources. Then, data is cleansed, enriched, transformed, and stored either back in the lake or in a data warehouse.

> "ELT (Extract, Load, Transform) is a variant of ETL wherein the extracted data is first loaded into the target system. Transformations are performed after the data is loaded into the data warehouse. ELT typically works well when the target system is powerful enough to handle transformations. Analytical databases like Amazon Redshift and Google BigQ.”

This Quora post is also helpful if you'd like to read more.

----------

####  What are a few examples of data pipeline?


- Automated Marketing Emails
- Real-time pricing in rideshare apps (companies commonly use data pipelines to orchestrate the analysis that determines the pricing) 
- Targeted advertising based on browsing history  



![](https://paper-attachments.dropbox.com/s_57CCB7A335BDB77AAB2E972461A8839D5986AA25E977A30F29D0F24424145C71_1616664355673_Screen+Shot+2021-03-25+at+8.25.39+pm.png)



####  Data Validation: 

Ensuring the quality of your data through automated validated checks is a critical step in building data pipelines in any organizaiton - Data validation is the process of ensuring that data is present, correct and meaningful. 



#### Data Pipelines as Directed Acyclic Graphs (DAGs) 


- Data Pipelines can be well expressed as Directed Acyclic Graphs 
- the vast majority of use cases for data pipelines can be described as a directed acyclic graph (DAG)
- In ETL, each step of the process typically depends on the last.
- Each step is a node and the dependencies on prior steps are directed edges.



####  Definitions                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| - Directed Acyclic Graphs (DAGs): DAGs are a special subset of graphs in which the edges between nodes have a specific direction, and no cycles exist. When we say “no cycles exist” what we mean is the nodes cant create a path back to themselves.<br>- Nodes: A step in the data pipeline process.<br>- Edges: The dependencies or relationships other between nodes.<br>![](https://video.udacity-data.com/topher/2019/February/5c5f5b00_capture/capture.png) |

Can we have two different pipelines for the same data and can we merge them back together?

    Yes. It's not uncommon for a data pipeline to take the same dataset, perform two different processes to analyze the it, then merge the results of those two processes back together.

####  Example: 


![](https://paper-attachments.dropbox.com/s_57CCB7A335BDB77AAB2E972461A8839D5986AA25E977A30F29D0F24424145C71_1616842618960_Screen+Shot+2021-03-27+at+9.56.46+pm.png)



####  Apache Airflow: 
- Airbnb open sourced airflow in 2015 with the goal of creating a DAG-based schedulable, data pipeline tool that could run in mission critical environments. 
- Airflow DAGs are written in python that run on a schedule and/or from an external trigger 
- Airflow is simple to maintain and can run data analysis itself, or trigger external tools (Redshift, Spark, Presto, Hadoop, etc) during execution.


####  Components of Airflow

![](https://video.udacity-data.com/topher/2019/February/5c5f6105_airflow-diagram/airflow-diagram.png)

- Scheduler orchestrates the execution of jobs on a trigger or schedule. The Scheduler chooses how to prioritize the running and execution of tasks within the system. You can learn more about the Scheduler from the official Apache Airflow documentation.
- Work Queue is used by the scheduler in most Airflow installations to deliver tasks that need to be run to the Workers.
- Worker processes execute the operations defined in each DAG. In most Airflow installations, workers pull from the work queue when it is ready to process a task. When the worker completes the execution of the task, it will attempt to process more work from the work queue until there is no further work remaining. When work in the queue arrives, the worker will begin to process it.
- Database saves credentials, connections, history, and configuration. The database, often referred to as the metadata database, also stores the state of all tasks in the system. Airflow components interact with the database with the Python ORM, SQLAlchemy.
- Web Interface provides a control dashboard for users and maintainers. Throughout this course you will see how the web interface allows users to perform tasks such as stopping and starting DAGs, retrying failed tasks, configuring credentials, The web interface is built using the Flask web-development microframework.

#### How Airflow Works

![](https://video.udacity-data.com/topher/2019/February/5c5f8e1d_how-airflow-works/how-airflow-works.png)


####  Order of Operations For an Airflow DAG

- The Airflow Scheduler starts DAGs based on time or external triggers.
- Once a DAG is started, the Scheduler looks at the steps within the DAG and determines which steps can run by looking at their dependencies.
- The Scheduler places runnable steps in the queue.
- Workers pick up those tasks and run them.
- Once the worker has finished running the step, the final status of the task is recorded and additional tasks are placed by the scheduler until all tasks are complete.
- Once all tasks have been completed, the DAG is complete.

####  Creating a DAG is easy. Give it a name, a description, a start date, and an interval.


![](https://paper-attachments.dropbox.com/s_57CCB7A335BDB77AAB2E972461A8839D5986AA25E977A30F29D0F24424145C71_1616845052674_Screen+Shot+2021-03-27+at+10.37.20+pm.png)


####  Operators define the atomic steps of work that make up a DAG. Instantiated Operators are referred to as Tasks.


![](https://paper-attachments.dropbox.com/s_57CCB7A335BDB77AAB2E972461A8839D5986AA25E977A30F29D0F24424145C71_1616845149711_Screen+Shot+2021-03-27+at+10.38.43+pm.png)


