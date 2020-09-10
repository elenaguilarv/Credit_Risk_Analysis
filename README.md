# Credit Risk Analysis
## Using Machine Learning Models
This analysis utilizes several machine learning models and techniques to predict credit risk for a firm that wants to improve the way they manage loan applications and assess good candidates for loans. The dataset used for this analysis is a csv file from LendingClub, a lending services company, which provides detailed information on the type of loans and applicants.

Prior to creating predictions, the data was prepared and split by the target variable "loan_status" and the other columns also known as features that help predict the target values. Identifying credit risk is an unbalanced classification problem. The ratio of good loans outweighs the risky loans, therefore a variety of sampling techniques were used to get a representative sample for training and evaluation. The performance of each machine learning model was evaluated through library tools that produce classification reports, confusion matrices, and accuracy scores. 

# Resources
Python, Jupyter Notebook, numpy, pandas, scikit-learn, imblearn

File: LoanStats2019Q1.csv

# Techniques
## Oversampling using Random and SMOTE
### Balanced Accuracy Scores 
Random: 0.635

SMOTE: 0.647

### Confusion Matrices
Random

True Positive= 51 | False Positive= 36
False Negative= 5,422 | True Negative= 11,696

SMOTE

True Positive= 58 | False Positive= 29

False Negative= 6,369 | True Negative= 10.749

### Precision and Recall Scores
#### Description:
Random                 

Precision (high-risk): 0.01
Precision (low-risk): 1.00

Recall (high-risk): 0.68
Recall (low-risk): 0.59

SMOTE

Precision (high-risk): 0.01
Precision (low-risk): 1.00

Recall (high-risk): 0.67
Recall (low-risk): 0.63


## Undersampling using Cluster Centroids
### Balanced Accuracy Score
Cluster Centroids: 0.515

### Confusion Matrix
True Positive= 54 | False Positive= 33

False Negative= 10,116 | True Negative= 7,002

###Precision and Recall Scores
#### Description:

Precision (high-risk): 0.01
Precision (low-risk): 1.00

Recall (high-risk): 0.62
Recall (low-risk): 0.41

## Combination (Over and Under) Sampling using SMOTEENN 
### Balanced Accuracy Scores 
SMOTEENN: 0.620

### Confusion Matrix
True Positive= 58 | False Positive= 29

False Negative= 7,301 | True Negative= 9,817

### Precision and Recall Scores
#### Description:
Precision (high-risk): 0.01
Precision (low-risk): 1.00

Recall (high-risk): 0.67
Recall (low-risk): 0.57

# Extension
## Oversampling using Ensemble Learners
#### Balanced Accuracy Scores 
Balanced Random Forest Classifier: 0.788

Easy Ensemble AdaBoost: 0.925

### Confusion Matrices
Balanced Random Forest Classifier

True Positive= 58 | False Positive= 29

False Negative= 1,560 | True Negative= 15,558

Easy Ensemble AdaBoost

True Positive= 79 | False Positive= 8

False Negative= 979 | True Negative= 16,139

### Describing Precision and Recall Scores
Balanced Random Forest Classifier

Precision (high-risk): 0.04
Precision (low-risk): 1.00

Recall (high-risk): 0.67
Recall (low-risk): 0.91

Easy Ensemble AdaBoost

Precision (high-risk): 0.07
Precision (low-risk): 1.00

Recall (high-risk): 0.91
Recall (low-risk): 0.94

# Recommendations
The best performing model and predictor for this analysis turned out to be the Easy Ensemble AdaBoost Classifier. Though it stands out from the other models, it does display higher potential for false positives (FP) in some cases due to its high recall value (0.91) and low precision value (0.07). This means low-risk loans could potentially be rejected because they get labeled high-risk. This kind of miscalculation in a model could be turn out to be inefficient and even costly for the firm in the long run. A better solution would be to use the model as a first step but not rely on it fully until it is further improved.
