# Credit Risk Analysis - Draft (This is a work in progress and will be completed in the next couple of days)
## Overview
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky ones. This analysis utilized imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling. Credit card data from  LendingClub, a peer-to-peer lending services company was the source of the data used in this project. More specifically, the credit card dataset was oversampled  with the RandomOverSampler and SMOTE algorithms. The data was then undersampled using the ClusterCentroids algorithm. Then a combinatorial approach of over and undersampling using the SMOTEENN algorithm was performed. Finally, a comparison of two new machine learning models that reduce bias; BalancedRandomForestClassifier and EasyEnsembleClassifier, were used to predict credit risk.
##  Credit Risk Resampling
### Data Set Preparation and Ingestion 
Column selection and data cleanup were performed. Null columns and rows were dropped. The interest rate was converted to a numercal value and the target column values for loan_status  were removed or assigned to low risk or high risk categories  as follows:
- Removed:  Issued
- Reassigned:
  - low_risk:  Current
  - high_risk: Late (31-120 days), Late (16-30 days), Default, In Grace Period

The data was then reviewed for missing values (there were none). 
String values were converted to numerical values using the pandas get_dummies method and loan status low_risk and high_risk strings were replaced with 0 and 1 respectively. 

The loan status risk inidator count was as follows: 
- High Risk: 347
- Low Risk : 68,470.

The data was then split into training and testing sets and Naïve random oversampling was performed. The data was resampled with the RandomOversampler and the logistic regression model was trained using the resampled data.

Code Examples
# Resample the training data with the RandomOversampler
from imblearn.over_sampling import RandomOverSampler
ros = RandomOverSampler(random_state=1)
X_resampled, y_resampled = ros.fit_resample(X_train, y_train)
Counter(y_resampled)

# Train the Logistic Regression model using the resampled data
from sklearn.linear_model import LogisticRegression
model = LogisticRegression(solver='lbfgs', random_state=1)
model.fit(X_resampled, y_resampled)

The confusion matrix results were as follows:
- True Positives: 10,291
- False Positives: 31
- False Negatives: 6,813
- True Negatives: 70

The balanced accuracy score was: 65%
The imbalanced classification report results were as follows:
-Precision: 
	- 0: 1.00
	- 1: 0.01
-Recall: 
	- 0: 0.60
- 1: 0.69
- Specificity: 
	- 0: 0.69
	- 1: 0.60
- F1 (Harmonic Mean): 
	- 0: 0.75
-1 : 0.02
- Geometric Mean: 
	- 0: 0.65
- 1: 0.65
-  Index Imabalanced Accuracy: 
	- 0: 0.41
	- 1: 0.42
- Support: 17,205 
	- 0: 17,104
	- 1: 101

In this case we are looking at credit risk, so the precision of actual positives and false negatives is goint to be more more important than sensitivity.   
