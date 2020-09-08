# Credit Risk Analysis
This analysis utilizes several machine learning models and techniques to predict credit risk for a firm that wants to improve the way they manage loan applications and assess good candidates for loans. The dataset used for this analysis is a csv file from LendingClub, a lending services company, which provides detailed information on the type of loans and applicants.

Prior to creating predictions, the data was prepared, trained, and tested to create subsets and address class imbalances present in the target column, "loan_status" using sckikit-learn and  The performance of each machine learning model was then evaluated through several statistical reasoning processes from imbalanced-learn and scikit-learn library, including classification reports, confusion matrices, and accuracy scores.

## Models & Techniques
### Oversampling using Random and SMOTE
#### Balanced Accuracy Scores 
Random: 0.716 

SMOTE: 0.700

### Confusion Matrices
Random

True Positive= 73 | False Positive= 28

False Negative= 4,960 | True Negative= 12,144

SMOTE

True Positive= 71 | False Positive= 30

False Negative= 5,178 | True Negative= 11,296

### Describing Precision and Recall Scores
Rejects too many applications, risk is low 0.01, recall- is high 0.72, 0.71- GOOD

SMOTE: WORSE, 0.01, 0.70 Okay

### Undersampling using Cluster Centroids
#### Balanced Accuracy Score
Cluster Centroids: 0.643

### Confusion Matrix
True Positive= 82 | False Positive= 19

False Negative= 8,983 | True Negative= 8,121

### Describing Precision and Recall Scores
risk is low, 0.01 for high_risk as well, 0.81 for recall high, 0.47 recall low - not good

### Combination (Over and Under) Sampling using SMOTEENN 
#### Balanced Accuracy Scores 
SMOTEENN: 0.697

### Confusion Matrix
True Positive= 72 | False Positive= 29

False Negative= 5,443 | True Negative= 11,661

### Describing Precision and Recall Scores
Same 0.01 high precision, 0.71 recall high, 0.68 low OKAY?

## Extension
### Oversample using RandomOverSampler


## Recommendations
Includes a final recommendation on the model to use, if any. Provide justification
