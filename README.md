# Credit Risk Analysis  
## Overview
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky ones. This analysis utilized imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling. Credit card data from  LendingClub, a peer-to-peer lending services company was the source of the data used in this project. More specifically, the credit card dataset was oversampled with the RandomOverSampler and SMOTE algorithms. The data was then undersampled using the ClusterCentroids algorithm. Then a combinatorial approach of over and undersampling using the SMOTEENN algorithm was performed. Finally, a comparison of two new machine learning models that reduce bias; BalancedRandomForestClassifier and EasyEnsembleClassifier, were used to predict credit risk. The results are below, related images are in the appendix.
## Results
####  Credit Risk Resampling Techiques
The balanced accuracy, precision and recall scores for each of the four machine learning models for credit risk resampling were as follows.:
- Naive Random Oversampling
	- Balanced Accuracy = 65%
	- Precision = 99%
	- Recall = 60%
	
- SMOTE Oversampling
	- Balanced Accuracy = 66%
	- Precision = 99%
	- Recall = 69%
	
- Undersampling
	- Balanced Accuracy = 54%
	- Precision = 99%
	- Recall = 69%
	
- Combination (Over and Under) Sampling
	- Balanced Accuracy = 64%
	- Precision = 99%
	- Recall = 57%

The SMOTEENN oversampling technique demonstrated the best results, combination (over and under) sampling had the worst results. However the recall scores for each method indicate that there is room for improvement. Credit risk ensemble techniques were subsequently used to improve the accuracy of the results.	
####  Credit Risk Ensemble Techiques
The balanced accuracy, precision and recall scores for the two risk esemble machine learning models were as follows:
- Balanced Random Forest Classifier
	- Balanced Accuracy = 66%
	- Precision = 99%
	- Recall = 100%
	
- Easy Ensemble AdaBoost Classifier
	- Balanced Accuracy = 66%
	- Precision = 99%
	- Recall = 100%

## Recommendations
Both techniques yielded almost identical results. We are looking at credit risk, so the precision of actual positives and false negatives is going to be more more important than sensitivity. The recommended technique in this case would be AdaBoost. AdaBoost is an ensemble learning method that uses an iterative approach to learn from the mistakes of weak classifiers, then turn them into strong ones. AdaBoost can be applied over any classifier to learn from its shortcomings and propose a more accurate model, it works by putting more weight on difficult to classify instances and less on those already handled well. AdaBoost algorithms can be used for both classification and regression problems.
### Appendix
### Credit Risk Resampling Techniques
![Naive](https://github.com/LleeMcD/Credit_Risk_Analysis/blob/main/Images/Naieve.png)
![SMOTE](https://github.com/LleeMcD/Credit_Risk_Analysis/blob/main/Images/SMOTE.png)
![Undersampling](https://github.com/LleeMcD/Credit_Risk_Analysis/blob/main/Images/Undersampling.png)
![Undersampling](https://github.com/LleeMcD/Credit_Risk_Analysis/blob/main/Images/Combination.png)

### Credit Risk Ensemble Techniques
![Forest](https://github.com/LleeMcD/Credit_Risk_Analysis/blob/main/Images/Forest.png)
![AdaBoost](https://github.com/LleeMcD/Credit_Risk_Analysis/blob/main/Images/AdaBoost.png)

### Resources
- A Guide to Understanding AdaBoost: Boosting to Save The Day: https://blog.paperspace.com/adaboost-optimizer/
- Understanding AdaBoost: https://towardsdatascience.com/understanding-adaboost-2f94f22d5bfe
- © 2020 - 2021 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
