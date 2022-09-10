# Prediction of Regression Model using Azure Machine Learning Platform

This project serves as the Summative Assessment for module "Principles of Machine Learning" of Professional Diploma in Data Science of Lithan Academy.

## Project Overview
This project serves as the continuation from the project of previous module, and the repository for the previous project is “Train, Test and Publish a Regression Model using Azure Machine Learning Platform”.

In this project, techniques for further improving the base boosted decision tree regression model, such as using different algorithms, feature selection, handling of outliers, hyperparameter tuning are used to obtain the optimal model. Subsequently, cross-validation check is performed for the optimal model to check if it is well generalized. Finally, the optimal model is published as web service, and it is used to predict the ArrDelay of the test data ‘Test-Flights.csv’ using Excel Online.

## Objectives of the Project
The following are the objectives of the project:
1.	Create an improved / optimal machine learning model in AML for predicting how many minutes a flight will be delayed or early.
2.	Deploy the improved / optimal model as a web service and predictions can be readily made using Excel Online.

## Project Outline
Since the base model is already available from the previous module, its experiment file in AML can be directly used for building the improved / optimal model. The following are the techniques used for improving the model:
1.	Feature selection:
In this step, features of the base model are dropped sequentially (start from the least important) based on their importance found using the ‘Permutation Feature Importance’ module to check their impact on model performance (change in coefficient of determination).
2.	Comparison of performance using different algorithms:
Model performances based on other algorithms, such as linear regression and decision forest regression are also studied. It is found that both linear regression and decision forest regression are no better. Hence only boosted decision tree regression will be used for further study.
3.	Handling outliers:
From the exploratory data analysis (EDA), it is found that there are some outliers in the dataset. For handling these outliers, the ‘Apply SQL Transformation’ module of AML is utilized. It is found that the performance of the model improves significantly after handling those outliers. Hence the model with outliers removed is then used for subsequent steps.
4.	Feature selection (after handling outliers):
In this step, features of the model are dropped sequentially (start from the least important) based on their importance found using the ‘Permutation Feature Importance’ module to check their impact (change in coefficient of determination). “DayOfWeek” column is dropped since dropping it will not decrease the coefficient of determination of the model.
5.	Hyperparameter tuning for the reduced model:
For the reduced model from Step 4, the “Tune Model Hyperparameters” module is utilized for random sweeping of those parameter range specified in the “Boosted Decision Tree Regression” module in order to find the optimal model (or at least an improvement). The improved / optimal model with better performance is found and ready for cross-validation check in the next step.
6.	Cross-validation check for the optimal model:
In this step, the “Cross Validate Model” module is utilized for performing the cross validation of the optimal model obtained from Step 5. Cross-validation is a useful method for flagging either overfitting or selection bias in the training data. It is also useful for measuring if the optimal model is generalized well. It is found that the performance of the optimal model is very consistent for all folds. Hence it is concluded that the optimal model should be well generalized for real world data.

Finally, the optimal model obtained from above steps is published as web service, and is used to predict the ArrDelay of the test data ‘Test-Flights.csv’ using Excel Online. From the testing result using Excel Online, it is found that the optimal model is able to correctly predict ArrDelay within 10 minutes of the actual delay time for 23 out of 25 rows. This further confirms that the optimal model is well generalized for real world data.

The following documents are provided in this repository:
  1. PML-0322A-Lee Jack Shiang-Project.docx: Word document for the project report
  2. Test-Flights.csv: Test data for the optimal model
