## Anomoly Detection 

- developing an credit card fraud detection system (anomaly detection) all in realtime

- it would be a feedback loop like we monitor the model performance on new incoming dataset (viii) and have a threshold that if the model performance degrades we then launch a trigger (Aws lambda function or something else) to retrain the model on subset of incoming data and then re-deploy it.  

## Trajectory Prediction 

Make trajectory prediction research also deployable. This would be a little on computer vision side. like you have  a camera which is deployed on road intersections and you detect pedestrians in the frame and forecast their trajectories (usefull for autonomous driving) and repeat the entire realtime deployment that we discussed.

### Enterprise Knowledge Retreival Tool for unstrucuted data 

- Semantic search to retrieve an ordered list 
- use the list for QA training 

Other ideas: 

- [Fast Forward Labs research reports & prototypes](https://www.cloudera.com/products/fast-forward-labs-research/fast-forward-labs-research-reports.html)
- [Udacity Nano-degree](https://github.com/san089/Udacity-Data-Engineering-Projects)