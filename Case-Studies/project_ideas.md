## Anomoly Detection 

- Develop a realtime credit card fraud detection system by implementing end-end ML workflow 

  #### Data Analysis and Business Understanding 

  Preprocess data and analyze target variable 

  feature engineering and extract their relative importance 

  #### Model Building 

  Try out different models and evaluate performance 

  - One-Class SVM 
  - Isolation Forest 
  - Local Outlier Factor 

  #### Setup Data Pipeline 

  - Upload credit card data to AWS S3 bucket
  - Deploy model as a Flask API endpoint on EC2 
  - Set up AWS Lambda trigger to send data in realtime to the deployed model 
  - Score model and send predictions to the dashboard 

  #### Monitoring and Visualization 

  - Set up R-Shiny Dashoard and display predictions. 
  - In another tab monitor model performance in realtime.
  - Setup alerts when model performance degrades. 

  #### Retrain Model 

  TBD

  #### Re-deploy Model

  TBD

  #### CI/CD pipeline 

  TBD 

## Trajectory Prediction 

Make trajectory prediction research also deployable. This would be a little on computer vision side. like you have  a camera which is deployed on road intersections and you detect pedestrians in the frame and forecast their trajectories (usefull for autonomous driving) and repeat the entire realtime deployment that we discussed.

### Enterprise Knowledge Retreival Tool for unstrucuted data 

- Semantic search to retrieve an ordered list 
- use the list for QA training 

Other ideas: 

- [Fast Forward Labs research reports & prototypes](https://www.cloudera.com/products/fast-forward-labs-research/fast-forward-labs-research-reports.html)
- [Udacity Nano-degree](https://github.com/san089/Udacity-Data-Engineering-Projects)