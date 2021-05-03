## ML Process Summary



 The ML project development life cycle An ML project starts with data about a service or product on which you fit models to be deployed into production. These models need to be monitored and their performance evaluated. The firm’s AI infrastructure supports these tasks.

### Frame the Problem and Look at the Big Picture

1. identify areas of the business that could benefit from machine learning 
2. Define the objective in business terms. 
   - appropriately frame and scope the task
   - communicate with other stakeholders about what machine learning is and is not capable of (there are often many misconceptions)
3. How will your solution be used?
   * develop understanding of business strategy, risks, and goals to make sure everyone is on the same page
4. What are the current solutions/workarounds (if any)? (How are being things currently done)

5. How should you frame this problem (supervised/unsupervised, online/offline, etc.)?
6. How should performance be measured?
   * Choosing F1-score to evaluate a model’s performance on a classification task 
   * Implementing evaluation metrics such as accuracy, precision, recall, intersection over union, or mean average precision (mAP)
7. Is the performance measure aligned with the business objective?
8. What would be the minimum performance needed to reach the business objective?
9. What are comparable problems? Can you reuse experience or tools?
10. Is human expertise available?
11. How would you solve the problem manually?
12. List the assumptions you (or others) have made so far.
    * Verify assumptions if possible.

###  Data Acquizition 

Note: automate as much as possible so you can easily get fresh data.

1. List the data you need and how much you need.

2. Find and document where you can get that data (identify what kind of data the organization has). 

   * e. g Querying data from a database

3. Check how much space it take and engineering efforts required(initial assessment). 

4. understand operational constraints (e.g. what data is actually available at inference time)

5. Legal/Ethics/Privacy

   1. Get access authorizations and check legal obligations 
   2. proactively identify ethical risks, including how your work could be mis-used by harassers, trolls, authoritarian governments, or for propaganda/disinformation campaigns (and plan how to reduce these risks)
   3. identify [potential biases and potential negative feedback loops]
   4. Ensure sensitive Information is deleted or protected (e.g anonymized)

6. Keep track of data sources. e.g  Setting up a data version control system

   

Examples: 

* Setting up a Mechanical Turk project 

- Collecting data by manually taking images of cats 

- Coding a JavaScript tracker on a website to collect user data 

- Scraping the web and, if necessary, synchronizing data from different sources

- Labeling data. e.g \- Writing a labeling tutorial for workers

### EDA - Explore the data: 

**Before EDA:** 

1. Check the size and type of data 
2. See if the data is in appropriate for  - Convert the data to a format you can easily manupulate (without changing the data itself)
3. Sample a test set, set it aside and never look at it 

**EDA:** 

1. Grab a copy of the data 

2. Document the EDA in a Jupyter notebook

3. Study Each Attribute and its characteristics (Name, Type, % of missing values, noisy, usefulness, type of distribution)

4. For Supervised Machine Learning, identify the target attribute 

5. Visualize the data. e.g Visualizing high-dimensional data in lower dimensions using methods such as PCA or t-SNE

6. Study the correlations between attributes 

7. Study how you would solve the problem manually

8. Identify the promising transformations you may want to apply

9. make plans to collect more of different data (if needed and if possible)

   

**Data Cleaning:** 

* Fix or remove outliers 
* Fill in missing values(e.g with zero, mean, median) or drop their rows  
* deal with corrupted/erronous  data
* (For ML) Feature Selection: Drop the attributes that provide no useful infomration for the task 

### Prepare the data: 

* Create appropriate training and validation set https://www.fast.ai/2017/11/13/validation-sets/)
* Writing function for data transformation (they will come in handy next time) e.g  Converting a continuous feature into a categorical feature using bucketing 

* stitch together data from many different sources: often this data has been collected in different formats or with inconsistent conventions
* Moving data and building data pipelines. e.g 
  *  Writing a script to allow online learning for a model 
  *  Designing an ETL system 
  *  Writing a script to preprocess training data and send it as input to a model automatically
  *  Writing a script to record model predictions in a database

### Feature Engineering: 

* Discretize continuous features
* Decompose features (e.g categorical, data/time etc)
* Add Promosing transformations of feature(e.g log(x), sort(x), x^2)
* Aggregate features into promising new features
* Standardise or normalize features  

### **Modeling**:

1. Train many quick and dirty models from different categories using standard parameters
2. Measure and compare their performance 
3. Analyse the most significant variables for each algorithm
4. Analyse the types of errors the models make 
5. Perform a quick round of feature selection and engineering
6. Perform one or two more quick iterations of the five previous steps 
7. Shortlist the top three to five most promising models, preferrring models that make different types of errors 
8. fit model resource needs into constraints (e.g. will the completed model need to run on an edge device, in a low memory or high latency environment, etc)

### Fine-tunings 

- Fine-tune the hyper hyperparameters using cross-validation (e.g. in the case of deep learning, this includes choosing an architecture, loss function, and optimizer)
  - *ADD MORE DETAILS HERE* 
- train the model (and debug why it’s not training). This can involve:
  - adjusting hyperparmeters (e.g. such as the learning rate)
  - outputing intermediate results to see how the loss, training error, and validation error are changing with time
  - inspecting the data the model is wrong on to look for patterns
  - identifying underlying errors or issues with the data
  - realizing you need to change how you clean and pre-process the data
  - realizing you need more or different data augmentation
  - realizing you need more or different data
  - trying out different models
  - identifying if you are under- or over-fitting

* try ensemble methods. Combining your best models will often produce better performance than running them individually. 
* Once you are confident about your final model, measure its performance on the test set to esitmate the generalization error. 

### Present/Launch the solution 

**Productionize**:

- creating an API or web app with your model as an endpoint in order to productionize
- exporting your model into the needed format
- plan for how often your model will need to be retrained with updated data (e.g. perhaps you will retrain nightly or weekly)

**Monitor**:

- track model performance over time
- monitor the input data, to identify if it changes with time in a way that would invalidate your model
- communicate your results to the rest of the organization
- have a plan in place for how you will monitor and respond to mistakes or unexpected consequences



----

Guides: 

* [What do machine learning practitioners actually do?](https://www.fast.ai/2018/07/12/auto-ml-1/)

* Appendix B - Machine Learning Project checklist from   

* [Building Machine Learning Powered Applications: Going from Idea to Product](https://mitpress.mit.edu/books/fundamentals-machine-learning-predictive-data-analytics)

* choose which model to use: Model Selection: https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html

  

*People with machine learning skills demonstrate the ability to use classic machine learning models (for example, PCA, K-means, K-NNs, SVM, Logistic Regression, Linear Regression, and Decision Tree learning), methods to train them (such as initialization, optimization, regularization, and hyperparameter tuning), and techniques to strategize machine learning projects.*