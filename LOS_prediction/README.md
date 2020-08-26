# ICU Length of Stay Prediction
A key characteristic of each patient is their ICU length of stay (LOS). 
Once ICU patients are ’admitted’ to hospital, they are assigned a length of stay, after which time they will be discharged.

In our agent-based model, the patients' LOS is combined with patient admissions and the probability of developing sepsis to simulate patient flow. 

Each patient in the agent-based simulation is assigned a cluster based on admissions dynamics; then a LOS is drawn from an LOS distribution specific to that cluster. (The exploration of patient-clustering methods can be found in the Data_processing folder)


In this notebook we use a machine learning approach to effectively capture sub- population dynamics in patient outflow. 


#### Length of Stay - Machine learning prediction
Based on the best $R^2$ score following hyperparameter tuning, we use a different machine learning model for each of the four clusters. 

The result is that our clustering method generates LOS distributions that are less sparse, and closely aligned with the expected LOS for each cluster, when compared to results without initial clustering. 


los_prediction.ipynb shows the model selection and hyperparameter tuning for each of the four models used.

