# Credit Risk Analysis
Predicting risk of credit card default using unbalanced machine learning techniques.

## Overview:

The purpose of this machine learning program is to predict when a credit account is a high risk for defaulting. In order to find the best prediction, we tested several different algorithms and compared accuracy scores, confusion matrices, and classification reports of each. 

* Random Oversampling
* SMOTE
* Cluster Centroids
* SMOTEENN
* Random Forest classifier
* Easy Ensemble classifier

## Results:

Each of the algorithms produced similar results for preceision: near 100% precision of predicting low_risk loans, but near 0 precision for predicting high-risk loans. This means that the algorithm has a low probability of correctly predicting high-risk loans. 

However, when analyzing recall, some algorithms perform better than others. Recall, or sensitivity, is the amount of data that had the prediction was correct. Recall is most commonly used in machine learning analyses, and in this scenario, it is not overly detrimental to have a false positive. It is better to over predict possible high-risk credit accounts instead of incorrectly assuming a high risk loan is low risk. 

### Outcome per Algorithm: 

##### 1. Naive Random Oversampling

* Balanced Accuracy Score: 0.6716
* Precision (high-risk): 0.01
* Precision (low-risk): 1.00
* Recall (high-risk): 0.69
* Recall (low-risk): 0.65

##### 2. SMOTE Oversampling

* Balanced Accuracy Score:0.6716
* Precision (high-risk): 0.01
* Precision (low-risk): 1.00
* Recall (high-risk): 0.69
* Recall (low-risk): 0.65

##### 3. Cluster Centroids (Undersampling)

* Balanced Accuracy Score: 0.5348
* Precision (high-risk): 0.01
* Precision (low-risk): 1.00
* Recall (high-risk): 0.67
* Recall (low-risk): 0.40

##### 4. SMOTEENN Over and Under Sampling

* Balanced Accuracy Score: 0.6346
* Precision (high-risk): 0.01
* Precision (low-risk): 1.00
* Recall (high-risk): 0.70
* Recall (low-risk): 0.57

##### 5. Random Forest Classifier

* Balanced Accuracy Score: 0.7102
* Precision (high-risk): 0.02
* Precision (low-risk): 1.00
* Recall (high-risk): 0.60
* Recall (low-risk): 0.82

##### 6. Easy Ensemble Classifier

* Balanced Accuracy Score: 0.4973
* Precision (high-risk): 0.01
* Precision (low-risk): 0.99
* Recall (high-risk): 0.17
* Recall (low-risk): 0.83



## Summary:

Since comparing the precision does not tell us much about the data, we will compare the recall (sensitivity) score. The algorithm with the strongest recall for predicting high-risk credit accounts is the SMOTEENN method, which combines over and undersampling. However, looking at the collective recall scores for high and low-risk accounts, it appears that the Random Oversampling and SMOTE oversampling algorithms also produced a comparitavely high recall for both outcomes. The algorithm that produced the highest balanced accuracy score is the Random Forest Classifier. The worst performing algorithm on this dataset was the Easy Ensemble Classifier. 

In conclusion, I would recommend the use of the SMOTE method to predict high-risk loans. Although the SMOTEENN method prouduced a higher recall of .70 for predicting high-risk accounts, the balanced accuracy score is only 0.6346, whereas the balanced accuracy score for SMOTE is 0.6716. 

Further analysis is needed to create a better preforming algorithm. We need to go back and revise the columns included in the features data. Reviewing the feature importances analysis on the Random Forest Classifier, it lists only 5 data points out of 90 total that scored above 0.05 importance. By removing some of these non-consequential data points we can get better results. 