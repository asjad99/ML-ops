### Data Modeling: A brief Overview

We discus the The big picture of data modeling and some Wisdom useful for practical settings.  

- There Exist variety of data models and they have a rich history. We make choices and pick one of the other by considering various factors such as size of data, how it will be used(queried) in future etc 

- The history of Data modeling goes back to hierarchical models where we presented the data as one big tree. It couldn’t be used to represent many-to-may relationships hence it was dropped.  

- The relational Model was invented in the 1970s by Edgar Codd to solve this problem. The key idea was to organize data into relations(tables) and tuples, It was an instant hit with business data process applications where we needed to store structured data in order to perform transaction or batch processing.  Overtime Relational databases solidified their dominance outside of business application by powering numerous scientific and web applications we use today. 
- Storing the data in simple tables did reduce a lot of complexity and made certain kind of data usage easier(in terms of reads, writes and transformations). The interesting bit of RDMs was the query optimizier where we could index a certain column(depending on how we wish to query it in future) in order to build a performant application. 

- **SQL vs NoSQL Comparison:** 


    SQL has number of challenge starting from 
        -  Impedance Mismatch:  means you need lots of boilerplate code or an ORM solution to translate between the relational model to the objects of OOP paradigm that most modern languages use. 
    
    In Response a NOSQL movement was started:
    
        - It offers support for specialised queries and better performance due to locality. 
        - It is closer to data structures used by the application (if data . Lastly it offers a schema flexibility.  
        - But the price is  Its hard to refer to a nested item document with a  for many-to-many relatkionships document databases are less idea. We need joins in that case. If we denoramilze the then application code needs to do additional work of 



---



**DB Design:**   **E/R Model**



DB design involves the following: 

**Database design: Why do we need it?**

​	Agree on structure of the database before deciding on a particular implementation
**Consider issues such as:**

​	What entities to model

​	How entities are related

​	What constraints exist in the domain

​	How to achieve good designs
**Several formalisms exist**We discuss one flavor of E/R diagrams



---

**E/R Basics: Entities & Relations**

