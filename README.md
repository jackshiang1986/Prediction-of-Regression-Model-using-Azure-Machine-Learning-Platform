# Prediction of Regression Model using Azure Machine Learning Platform

This project served as the Summative Assessment for module "Principles of Machine Learning" of Professional Diploma in Data Science of Lithan Academy.

## Project Overview
This project served as the continuation from the project of previous module, and the repository for the previous project is “Train, Test and Publish a Regression Model using Azure Machine Learning Platform”.

In this project, techniques for further improving the base boosted decision tree regression model, such as using different algorithms, feature selection, handling of outliers, hyperparameter tuning were used to obtain the optimal model. Subsequently, cross-validation check was performed for the optimal model to check if it was well generalized. Finally, the optimal model was published as web service, and it was used to predict the flight delay of the test data ‘Test-Flights.csv’ using Excel Online.

## Objectives of the Project
The following are the objectives of the project:
1.	Create an improved / optimal machine learning model in AML for predicting how many minutes a flight will be delayed or early.
2.	Deploy the improved / optimal model as a web service and predictions can be readily made using Excel Online.

## Project Outline
Since the base model was already available from the previous module, its experiment file in AML could be directly used for building the improved / optimal model. The following were the techniques used for improving the model:
1.	Feature selection:
In this step, features of the base model were dropped sequentially (started from the least important) based on their importance found using the ‘Permutation Feature Importance’ module to check their impact on model performance (change in coefficient of determination).
2.	Comparison of performance using different algorithms:
Model performances based on other algorithms, such as linear regression and decision forest regression were also studied. It was found that both linear regression and decision forest regression were no better. Hence only boosted decision tree regression would be used for further study.
3.	Handling outliers:
From the exploratory data analysis (EDA), it was found that there were some outliers in the dataset. For handling these outliers, the ‘Apply SQL Transformation’ module of AML was utilized. It was found that the performance of the model improved significantly after handling those outliers. Hence the model with outliers removed was then used for subsequent steps.
4.	Feature selection (after handling outliers):
In this step, features of the model were dropped sequentially (started from the least important) based on their importance found using the ‘Permutation Feature Importance’ module to check their impact (change in coefficient of determination). “DayOfWeek” column was dropped since dropping it would not decrease the coefficient of determination of the model.
5.	Hyperparameter tuning for the reduced model:
For the reduced model from Step 4, the “Tune Model Hyperparameters” module was utilized for random sweeping of those parameter range specified in the “Boosted Decision Tree Regression” module in order to find the optimal model (or at least an improvement). The improved / optimal model with better performance was found and ready for cross-validation check in the next step.
6.	Cross-validation check for the optimal model:
In this step, the “Cross Validate Model” module was utilized for performing the cross validation of the optimal model obtained from Step 5. It was found that the performance of the optimal model was very consistent for all folds. Hence it was concluded that the optimal model should be well generalized for real world data.

Finally, the optimal model obtained from above steps was published as web service, and was used to predict the flight delay of the test data ‘Test-Flights.csv’ using Excel Online. From the testing result using Excel Online, it was found that the optimal model was able to correctly predict flight delay within 10 minutes of the actual delay time for 23 out of 25 rows. This further confirmed that the optimal model was well generalized for real world data.

The following documents are provided in this repository:
  1. PML-0322A-Lee Jack Shiang-Project.docx: Word document for the project report
  2. Test-Flights.csv: Test data for the optimal model
