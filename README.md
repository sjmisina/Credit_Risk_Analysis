# Credit Risk Analysis
Analyst: <code><i> Stanley Misina, Columbia University Data Analytics Bootcamp</i></code><br />
Technology Used: <i><code> Python 3.8.11, Jupyter Notebook 6.4.3 </i> </code> <br />
Data Source Provided: <i><code>LoanStats_2019Q1.csv</code> - a credit card dataset from LendingClub, a peer-to-peer lending services company</i>

## Overview
#### Machine Learning in Finance
Credit risk is an inherently unbalanced classification problem due to the number of data points must be observed and weighed for codue dilligence. The task of building a reliable credit evaluation process is of the utmost importance for modern lenders. Machine learning solutions are powerful for predicting credit worthiness, anticipating anomalies, and reducing risk. 

## Results
#### Comparison of Models for Credit Applications
Testing the performace of the models, there are four primary measures to consider: accuracy, precision, recall, and processing time:
- **Accuracy** is the ratio of correct predictions to the total number of input samples
- **F1 score** is a simplified measure of model performance. It is a weighted harmonic mean of _precision_ and _recall_
  - _**Precision**_ is the ability of a classifier not to label an instance positive that is actually negative
  - _**Recall**_ is the ability of a classifier to find all positive instances
-  **Processing time** is taken into consideration as the models all run at different rates of speed. This factor will be important when large-scale processing and in considering service level expectation

#### Performance Metrics
We have chosen six models for comparison. The results are all presented on a scale of 0 to 1. Closer to one indicates better performance in our testing environment.

## Summary
#### Recommendations
- Our recommended processing model is the **Easy Ensemble Adaptive Boost Classifier** (EEABC). With an accuracy score of 0.93, a precision score of 0.99, a 0.94 recall score, and f1 of 0.97, this is the best performer of the six tested. and the lowest showing of False Positives at  **_However_**, there is a caveat: processing time. When multiple credit applications are put into the decision model, or if running on slow hardware, 33 seconds per decision can be prohibitive.

- The secondary recommendation is to use a two-tiered process by employing the **Balanced Random Forest Classifier (BRFC)** for primary processing, and use EEABC as a verification layer for application. BRFC performed well with speed (1.76 seconds per decision), precision (0.99), and f1 (0.93). Accuracy and recall are behind EEABC at .078 and 0.87 respectively. Turn down applications and for approval auditing, EEABC can be employed to perform an automated verification for saving some turndowns that should be approved.
