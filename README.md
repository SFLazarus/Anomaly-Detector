# Anomaly-Detector
Built a few anomaly detection models to determine the anomalies from the data

##  D(St)reams of Anomalies
###   The real world does not slow down for bad data
1.  Set up a data science project structure in a new git repository in your GitHub account
2.  Download the benchmark data set from:
- https://www.kaggle.com/boltzmannbrain/nab 
- https://github.com/numenta/NAB/tree/master/data
3.  Load the  one  of the data set into panda data frames
4.  Formulate one or two ideas on how feature engineering would help the data set to establish additional value using exploratory data analysis
5.  Build one or more anomaly detection models to determine the  anomalies  using the other columns as features
6.  Document your process and results
7.  Commit your notebook, source code, visualizations and other supporting files to the git repository in GitHub


---
## Data Description

This dataset (nyc_taxi) contains the number of NYC taxi passengers, where the five anomalies occur during the NYC marathon, Thanksgiving, Christmas, New Years day, and a snow storm. The raw data is from the NYC Taxi and Limousine Commission. The data file included here consists of aggregating the total number of taxi passengers into 30 minute buckets.
---
## What we want to do?
- Main goal: to detect anomalies from New york city taxi data
- First we shall go through dataset and understand what features can we use to improve results of our anomaly detector.
![](https://github.com/SFLazarus/Anomaly-Detector/blob/main/reports/visulaizing-nyctaxi-data.png)
- We created new feature `changeValue` which stores the difference between two continuous samples' values.
![](https://github.com/SFLazarus/Anomaly-Detector/blob/main/reports/change-values.png)
- We also created another feature `moving_average`, which stores moving averages of 5 continous samples
![](https://github.com/SFLazarus/Anomaly-Detector/blob/main/reports/moving-average.png)
---
## Results:
### One Class SVM based Anomaly detector:
![](https://github.com/SFLazarus/Anomaly-Detector/blob/main/reports/oneclassSVM.png)
- It has detected almost 29 outliers but we only had 5 actual ones, so it didn't perform well in our case.
### Isolation Forest based Anomaly detector:
![](https://github.com/SFLazarus/Anomaly-Detector/blob/main/reports/isolation_forest.png)
- It has detected NYC marathon, Thanksgiving, Christmas, New Years day, overall it performed well.
### Local Outlier Factor based Anomaly detector:
![](https://github.com/SFLazarus/Anomaly-Detector/blob/main/reports/local_outlier_factor.png)
- It has also detected NYC marathon, Thanksgiving, New Years day, this model has also performed well.
---
## Conclusion and Further improvements:

- Our models performed quite well on this data but am not sure if these models perform the best with other similar data too, it would only be fair to test on other data and evaluate its performance.
- From this project, we see that Local Outlier Factor and Isolation Forest performed better than OneClassSVM model
- In future, we can tweak certain parameters such as contamination which we used in this project and others to get the most of these models.

---
# Project Structure:
### Readme.md
- Project description
### Data
- Contains link to dataset
### Notebooks
- Jupyter Notebook for Exploratory data analysis, Visualization, Feature Engineering and Anomaly Detection.
### Reports
- plot- change in values  
- Plot- raw data visualization
- Plot- moving averages
- Plot- OneClassSVM based Anomaly detector
- plot- Local Outlier Factor based Anomaly detector
- Plot- Isolation Forest based Anomaly detector

### Requirements.txt
- Info about Tools, frameworks and libraries required to reproduce the work flow
