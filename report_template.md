# Credit Risk Classification Report Template

## Overview of the Analysis
In this anaylsis, a linear regression model will be used to evaluate 'High risk' and 'Healthy' loans. Due to the inherent nature of credit risk classification, oversampling is used on the historical dataset in order to correctly identify creditworthy borrowers before running this new dataset through the model. The performance of these two will determine what be adopted to predict the creditworthiness of borrowers.

### Data
Historical lending activity from a peer-to-peer lending services company was used to build a the models. The data included features that are considered good indicators of worthiness such as borrower's income, debt-to-income ratio, total debt to date and so forth.

### Variables
The target variable is 'loan_status' where '0' represents a 'Healthy loan' and '1' reperesents a High Risk loan. We used value counts to illustrate the imbalance(Original dataset) or balance(oversampled dataset) data. 


## Machine Learning Processes

### original Dataset
#### - Data preparation 
The data was split between features 'X' which is all of the variables excluding the target variable and the target varaible 'y'. 'value_counts()' functin was used to determine if there is an imbalance. Data was then split using the 'train_test_split' funtion to group the data into training and testing data.

#### Logistic regression model implementation: 
LogisticRegression model is imported from SKLearn library. The "train" data was fitted into the model "test" data was used to make the prediction. The predicted target data was compared to the 'y' test data to evaluate the model's perfromance. 

#### Resampled dataset:
'RandomOverSampler' was used to mitigate the imbalance of the original dataset. This new balanced dataset was then treated as above: Split into training and test, ran through the Linear Regression model and performance determined.


## Results
* Machine Learning Model 1: Model 1 used the original dataset. The results were as follows:
  * Accuracy: 95% of the predictions were accurate
  * Precision: The average is 99% with the a skewed perfroamance towards healthy loans at     100% and 85% on High risk loans.
  * Recall: 99% of average/total where it scores 99% for 'healthy loan' and 91% for 'high-risk loan'.  

  

* Machine Learning Model 2: Model 2 used the resampled dataset. The results were as follows:
  * Accuracy: 99% of the predictions were accurate
  * Precision: The average is 99% with the a skewed perfroamance towards healthy loans at     100% and 84% on High risk loans.
  * Recall: 99% of average/total where it scores 99% for both "healthy loan" and "high-risk loan". This is an improvement of 8% from the previous model on the high risk loans.

## Summary

* Both models performed really well but model 2 out perfroms model 1 in precision and accuracy as shown above. The number of false negatives (Recall) is lower in model 2
* Lenders will view False Positives as more costly as they will end up approving a high risk loan that may be defaulted. Therefore a model which provides a lower number of False Negatives will be preferred. Model 2 with the oversampled data provides more accurate predictions than the imbalanced model and would be the recommended model.

If you do not recommend any of the models, please justify your reasoning.
