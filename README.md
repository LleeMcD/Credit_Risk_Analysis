# Credit Risk Analysis - Draft 
## Overview
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky ones. This analysis utilized imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling. Credit card data from  LendingClub, a peer-to-peer lending services company was the source of the data used in this project. More specifically, the credit card dataset was oversampled with the RandomOverSampler and SMOTE algorithms. The data was then undersampled using the ClusterCentroids algorithm. Then a combinatorial approach of over and undersampling using the SMOTEENN algorithm was performed. Finally, a comparison of two new machine learning models that reduce bias; BalancedRandomForestClassifier and EasyEnsembleClassifier, were used to predict credit risk.
##  Credit Risk Resampling
The balanced accuracy, precision and recall scores for each of the six maching learning models were as follows.:
- Naive Random Oversampling
	- Balanced Accuracy = 65%
	- Precision = 99%
	- Recall = 60%
-



In this case we are looking at credit risk, so the precision of actual positives and false negatives is goinG to be more more important than sensitivity.   
