# Credit Risk Analysis
## With Machine Learning Models
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

False Negative= 6,369 | True Negative= 10,749

### Precision and Recall Scores
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

### Precision and Recall Scores
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
Precision (high-risk): 0.01
Precision (low-risk): 1.00

Recall (high-risk): 0.67
Recall (low-risk): 0.57

#### Summary of Scores:
(Random, SMOTE, Cluster Centroids, SMoTEENN)
All models fit a perfect precision score for low-risk detections and had decent F1 scores, between 0.73-0.81 (except for Cluster Centroids, poor at 0.58) meaning the models are generally okay at producing fewer false positives or false negatives.

However, the objective is to flag high-risk loans and the recall values are fairly poor for both models, between 0.41-0.68) for both high-risk and low-risk detections. This indicates a higher count of false negatives. All models also obtained a very low precision output (0.1) for high-risk loans and low F1 scores (0.1-0.2) for high-risk loans, which can allow for more inaccurate predictions. The balanced accuracy scores were also particularly low.

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
Balanced Random Forest Classifier (BRFC)

Precision (high-risk): 0.04
Precision (low-risk): 1.00

Recall (high-risk): 0.67
Recall (low-risk): 0.91

Easy Ensemble AdaBoost

Precision (high-risk): 0.07
Precision (low-risk): 1.00

Recall (high-risk): 0.91
Recall (low-risk): 0.94

#### Summary of Scores:
(Balanced Random Forest Classifier, Easy Ensemble AdaBoost)
Both models fit a perfect precision score for low-risk detections and great F1 scores, between 0.95 and 0.97, respectively, meaning the models are generally good at producing fewer false positives or false negatives.

The objective is to flag high-risk loans and the recall values for both models, high-risk and low-risk detections, were high as well, 0.91-0.94 (except for BRFC's high-risk detections at 0.67). This represents a significant drop in false negatives compared  to the models reviewed earlier. They also obtained a higher precision outputs for high-risk loans, 0.04 and 0.07, and F1 scores of 0.07 and 0.14 for high-risk loans, which allows for more accurate predictive reading.

# Recommendations
The best performing model and predictor for this analysis turned out to be the Easy Ensemble AdaBoost Classifier due to its highest accuracy score, 0.925, highest F1 score for high-risk loans, 0.14, and for low-risk loans, 0.97. Though it stands out from the other models, it does display potential for false positives (FP) in some cases due to its high recall value (0.91) and low precision value (0.07). This means low-risk loans could potentially be rejected because they get labeled high-risk. This kind of miscalculation in a model could be turn out to be inefficient and even costly for the firm in the long run. A better solution would be to use the model as a first step but not rely on it fully until it is further improved.
