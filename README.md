# Credit Card Fraud Detection

This project focuses on detecting fraudulent credit card transactions using machine learning models. The dataset used is highly imbalanced, with the majority of transactions being normal and a small fraction being fraudulent. The notebook includes data exploration, preprocessing, feature engineering, model training, evaluation, and a discussion on deployment.

## Table of Contents
- [Credit Card Fraud Detection](#credit-card-fraud-detection)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#Introduction)
  - [Data Exploration and Analysis](#data-exploration-and-analysis)
  - [Data Preprocessing](#data-preprocessing)
  - [Model Selection](#model-selection)
  - [Model Training and Evaluation](#model-training-and-evaluation)
  - [Model Deployment](#model-deployment)
  - [Flask Application](#Flask-Application)
  - [Communication](#communication)
  - [Dependencies](#dependencies)

## Introduction
The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.\
It contains only numerical input variables which are the result of a PCA transformation.

Due to confidentiality issues, there are not provided the original features and more background information about the data.

Features V1, V2, ... V28 are the principal components obtained with PCA;
The only features which have not been transformed with PCA are Time and Amount. Feature Time contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature Amount is the transaction Amount, this feature can be used for example-dependant cost-senstive learning.
Feature Class is the response variable and it takes value 1 in case of fraud and 0 otherwise.

## Data-Exploration-and-Analysis
Analyzed the dataset to understand feature relationships, identified missing values, and visualized distributions. Feature relationships were further explored through correlation matrices and feature importance scores from models. This phase helped in detecting data imbalances and selecting appropriate methods to address them.


## Data-Preprocessing
After choosing the most suited dataset the preparation phase begins, the preparation of the dataset that includes selecting the wanted attributes or variables, handling missing value i.e. cleaning it by excluding Null rows, deleting duplicated variables, feature scaling (Amount and Time) using Robust Scaling . All those alterations lead to the wanted result which is to make the data ready to be modeled.

## Model Selection
Three machine learning models were created in the modeling phase, Logistic Regression, Decision Tree, and Random Forest Classifier and applied on Orignial dataset. And model comapred on matrics such as Accuracy, Precision, recall, and F1-Score. A comparison of the results will be presented later in the paper to know which technique is most suited in the credit card fraudulent transactions detection. The dataset is sectioned into a ratio of 80:20, the training set will be the 80% and remaining set will be the testing set which is the 20%. 

## Model-Training-and-Evaluation
Data is highly imbalance so used Undersampling and Oversampling method to balance the data and then trained the dataset with three models Logistic Regression, Decision Tree, and Random Forest Classifier.

Out of all the models the model that scored the best is Random Forest Classifier as its accuracy is 99.99% and Recall 1%, the second best is Decision Tree and the model that scored the lowest accuracy out of all models is Logistic Regression with a score of 94.68%.

## Model-Deployment
The final chosen model, Random Forest is saved using Pickle for future Predictions. The model is saved in a file called  'CreditCard_Model.pkl'

## Flask Application
Use Flask to create a user interface for the credit card fraud detection project. The flask application allows the user to enter credit card transaction data, and the data is trained Random Forest Classifier model. Once transaction features are entered then we get the prediction on whether the transaction is legitimate or fraudulent.


## Communication
We investigated the data, checking for data unbalancing, visualizing the features and understanding the relationship between different features. We then investigated two predictive models. The data was split in 3 parts, a train set, a validation set and a test set. For the first three models, we only used the train and test set.

We started with Logistic Regression model, for which we obtained an Accuracy,f1-Score, recall and preciosn around 94% when predicting the target for the test set.

We followed with an Decision Tree model, with Accuracy,f1-Score, recall and preciosn around 99% for prediction of the test set target values.

In conclusion, the analysis identifies the Random Forest model as the best performer based on the F1-Score metric. With an AUC-ROC of 0.908053, Precision of 0.948718, Recall of 0.816176, and an F1-Score of 0.87747, the Random Forest model demonstrates a balanced performance across precision and recall, making it a robust choice for the given task.

## Dependencies
- <b>Pandas</b> for data manipulation
- <b>Numpy</b> for numerical computations
- <b>Seaborn</b> and <b>matplotlib</b> for data visualization
- <b>Scikit-Learn</b> for model training and evaluation
- <b>Imbalanced-learn</b> for handling class imbalance(SMOTE,random undersampling/oversampling)
- <b>Pickle</b> for saving and loading the model for future prediction

