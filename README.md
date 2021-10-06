# Credit Risk Analysis
Analyst: <code><i> Stanley Misina, Columbia University Data Analytics Bootcamp</i></code><br />
Systems Used: <i><code> Python 3.8.11, Jupyter Notebook 6.4.3 </i> </code> <br />
Data Source Provided: <i><code>LoanStats_2019Q1.csv</code></i>

## Overview
#### Machine Learning in Finance
Credit risk is an inherently unbalanced classification problem due to the number of data points observed and weighed during application processing. The task of building a reliable credit evaluation process is of the utmost importance for modern lenders. Machine learning solutions are powerful for predicting credit worthiness, anticipating anomalies, and reducing risk.

The dataset used for this machine language evaluation is from LendingClub, a peer-to-peer lending services company.

## Results
#### Comparison of Models for Credit Decision
When testing performace of these models, four primary measures are considered: accuracy, precision, recall, and processing time.
- **Accuracy** is the ratio of correct predictions to the total number of input samples
- **F1 score** is a simplified measure of model performance. It is a weighted harmonic mean of _precision_ and _recall_
  - _**Precision**_ is the ability of a classifier not to label an instance positive that is actually negative
  - _**Recall**_ is the ability of a model to find all positive instances
-  **Processing time** is taken into consideration as the models all run at different rates of speed. This factor will be important when large-scale processing and in considering service level expectation

#### Performance Metrics
We have chosen six models for comparison. The results for each present on a scale of 0 to 1. Closer to one indicates better performance in the testing environment.
<img width="917" alt="Accuracy_Time_Results" src="https://user-images.githubusercontent.com/84740997/136130621-070a5d01-5b5d-4621-a417-a88a6c3caff9.png">

## Summary
#### Recommendations
- Our recommended processing model is the **Easy Ensemble Adaptive Boost Classifier (EEABC)**. With an accuracy score of 0.93, and f1 of 0.97, this is the most accurate performer of the six tested; **_however_**, there is a caveat in processing time. When running multiple credit applications, 33 seconds per decision can be prohibitive during time sensitive processing.

- A secondary recommendation is to use a two-tiered process by employing the **Balanced Random Forest Classifier (BRFC)** for fast primary processing (only 1.76 seconds per decision) that performs well regarding precision (0.99), and f1 (0.93). Accuracy and recall are behind EEABC at .078 and 0.87 respectively. EEABC could be run as a secondary pipeline for turn down applications and approval auditing.
