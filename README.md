Source Code : https://kh3-ls-storage.s3.us-east-1.amazonaws.com/Updated%20Project%20guide%20data%20set/creditcard.csv

FIND DEFAULT (PREDICTION OF CREDIT CARD FRAUD)

Problem Statement:

A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash.
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. 
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 2,84,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions. We have to build a classification model to predict whether a transaction is fraudulent or not.

The workflow that would be followed is: 
•	Data Collection
•	Data Pre-processing
•	Data Analysis
•	Split Test/Train Data
•	Logistic Regression Model
•	Evaluation 

Using Jupiter notebook to develop coding, the first step is to Import dependencies as numpy, pandas, train_test_split, Logistic Regression and accuracy score. Then loading the data set to a pandas DataFrame and named it as “credit_card_data”. As a next step read the csv file and this would load the dataset into the data frame and printed the first and last 5 lines of the dataset using head() and tail() method, so that it helps to analyse the features present in the dataset. Class column in the dataset helps to find the particular transaction is legit or fraudulent. In the class column the label ‘0’ represent the legit transaction and ‘1’ represent the fraudulent transaction. Got all the information about the dataset using info() function, It gives information about the datatype of each column also null and non-null values, with the help of these values the missing values can be found. In this is data set there is no missing values at all, also check the missing values in each column by using isnull() gives the no of missing values. 
As a next step found the distribution of legit transaction and fraudulent transaction by using value_counts() function. There it gives the count of legit and fraudulent transaction. For normal transaction we have 2,84,315 transaction and for fraudulent transaction it is about 492 transaction, here it comes to know the data is highly imbalanced, because in two class 99% of data present in one particular class, in this case ML can’t recognize the Fraudulent transaction, so here the processing takes place. Let us create two variable which is legit and fraud, it checks the class value and store the particular value in the particular variable. Then did some statistical measure in the dataset for both legit and fraud using describe() function to know some important statistical measure. Now compare the value for both the legit and fraud with mean value using groupby() function and created a sample dataset from the original dataset, which contain a similar distribution of normal transaction and fraudulent transaction using sample function for an even distribution took 492 random values as sample for the legit transaction, here n=492. 
Concatenating two dataframes legit_sample and fraud by creating new_dataset, did some analysis using head (), tail () and mean () function and splitting the data into features and targets, created two variables X and Y and drop the class column in X data set and print the y which contain class column. 
As a next step split the data in to train and test data using train_test_split function as X_test, Y_test, X_train, Y_train. Where 80% of data stored in X_train, corresponding labels will be stored in Y_train and 20% of data stored in X_test and corresponding label stored in Y_test. Then training the Logistic Regression model with train data, with the help of fit function the data has been fitted. Finally the model has been evaluated by accuracy score.
Accuracy score of test data: 0.934010152284264
Accuracy score of train data: 0.9580686149936467

The accuracy of the model on the test data set should be > 75%



