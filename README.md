# Credit-Card-Fraud-Detection


## Problem statement
The aim of the project is to predict fraudulent credit card transactions with the help of 
various machine learning models. For banks, retaining the customers is the most 
important business goal. But banking fraud poses a significant threat to this goal 
for banks, so the goal is to identify all the transactions beforehand and classify it as 
fraud or genuine transaction and in case of fraudulent transaction, customers can be 
contacted immediately and required action can be taken so that the customers does not 
have any credibility issues with bank.

## Steps to be followed 
### Data understanding and EDA 
Loading the data and look for the dependency of 
dependent variables on independent variables and also perform various steps like 
scaling and encoding. Since the data is in PCA format, we need not to preform these 
steps but still we can select the important principal components instead of using the 
whole data.
### Train/Test Split
Divide the data in the ratio of 70:30 for the purpose of training and 
evaluating the accuracy of the model on the test data.
Balancing the data: The given data is highly imbalanced with only 0.172% of the data 
with positive class. There are various way to solve this problem such as oversampling, 
undersampling, SMOTE, ADASYN. We will be trying the model using both SMOTE and 
ADASYN approach.


## Model Building
Since it is a classification problem with two output classes, we will be
trying KNN, Logistic Regression, XGboost, Decision Tree and Random Forest model. 
Each model has its own advantages and disadvantages, KNN will consume lot of 
computational time, Logistic Regression works best on linear separable data, Decision 
Tree may overfit, XGBoost/Random Forest are difficult to interpret also it’s not possible 
to know which independent variable has high impact on dependent variable but since 
the data is already in PCA form XGBoost/Random forest will be the best models for this 
case. 

## Hyperparameter tuning
We will try for K–Cross validation and Stratified K-Cross 
validation to test the training accuracy and then to select the hyperparameter, either
RandomiszedSearchCV or GridSearchCV could be used. In GridSearchCV instead of 
trying to run model on each value of hyperparameter, models runs within the range of 
various values and then select that range and iteratively runs within that range thus selecting the best value. In RandomiszedSearchCV some random set of values are 
selected then model is evaluated on those values but since the dataset is larger, 
GridSearchCV would a better approach in this case. 


## Model Evaluation
We could not finalize the model based on just accuracy especially in 
this case of highly imbalanced data, accuracy would be much higher. We will be 
evaluating the model on other metrics as well such as precision and recall, going by the 
business use case recall would be more important since we are more interested to get 
all the fraudulent cases
