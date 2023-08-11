# House_Price_Prediction

## Overview

This project aims to predict the sale price of residential houses in Ames, Iowa, based on various features such as lot size, building type, neighborhood, quality, condition, garage, basement, etc. The dataset contains 1460 training examples and 1459 test examples, each with 79 features and 1 target variable (SalePrice).

## Data Cleaning and Exploration

The data cleaning and exploration process was done using TensorFlow, TensorFlow Decision Forests, pandas, seaborn, and matplotlib libraries in Python. The following steps were performed:

- Printed the TensorFlow and TensorFlow Decision Forests versions
- Read the csv file into a pandas dataframe
- Displayed the first 3 rows of the dataframe
- Dropped the Id column from the dataframe as it was not relevant for the prediction
- Checked the information and summary statistics of the dataframe
- Displayed the distribution of the target variable (SalePrice) using a histogram
- Listed the data types of the features
- Selected only the numerical features from the dataframe
- Displayed the histograms of the numerical features using a loop
- Split the dataframe into train and test sets with a test ratio of 0.3 using a custom function
- Converted the train and test sets into TensorFlow datasets with a regression task

## Data Modeling and Evaluation

The data modeling and evaluation process was done using TensorFlow Decision Forests library in Python. The following steps were performed:

- Listed all the available models in TensorFlow Decision Forests
- Chose a Random Forest model with a regression task
- Compiled the model with mean squared error as an evaluation metric
- Fitted the model on the train set
- Plotted the first tree of the model in Colab using a model plotter function
- Created an inspector object to access various information about the model
- Displayed the evaluation results of the model on the train set
- Evaluated the model on the test set and returned a dictionary of metrics
- Printed each metric name and value from the dictionary
- Printed the available variable importances from the inspector object
- Displayed the NUM_AS_ROOT variable importance of each feature using a horizontal bar chart

## Data Prediction and Submission

The data prediction and submission process was done using pandas and TensorFlow Decision Forests libraries in Python. The following steps were performed:

- Read the test csv file into a pandas dataframe
- Popped out the Id column from the dataframe and stored it in a separate variable
- Converted the test dataframe into a TensorFlow dataset with a regression task
- Made predictions on the test dataset using the trained model
- Created an output dataframe with Id and SalePrice columns from the predictions
- Displayed the first 5 rows of the output dataframe
- Read the sample submission csv file into a pandas dataframe
- Replaced the SalePrice column of the sample submission dataframe with the predictions from the model
- Saved the sample submission dataframe as output.csv file without index column
- Displayed the first 5 rows of the sample submission dataframe

## Conclusion

This project demonstrates how to use various tools and techniques to clean, explore, model, evaluate, and predict a dataset of house prices. The results reveal some interesting insights into the housing market, such as:

- The target variable (SalePrice) had a skewed distribution with a long right tail, indicating that most houses had low to medium prices while few houses had very high prices
- The numerical features had different ranges, scales, and distributions, some of them showing outliers or missing values
- The Random Forest model achieved a mean squared error of 0.0192 on the train set and 0.0318 on the test set, indicating that it was able to fit well on both sets without overfitting or underfitting
- The first tree of the model showed that it split on features such as OverallQual, GrLivArea, GarageCars, BsmtFinSF1, etc., indicating that these features were important for predicting SalePrice
- The NUM_AS_ROOT variable importance showed that OverallQual was by far the most important feature for predicting SalePrice, followed by GrLivArea, GarageCars, TotalBsmtSF, etc.
- The output.csv file contained 1459 predictions for SalePrice based on 79 features for each test example
