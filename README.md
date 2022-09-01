# Prediction of Regression Model using Azure Machine Learning Platform

* Introduction

In this project, Azure Machine Learning (AML) studio is utilized for data pre-processing, and for subsequent training, evaluation, and deployment of a machine learning model as a web service for future predictions using Excel Online. The dataset which is used for this project is “Flight Delays Data”, a built-in dataset in AML studio. The built-in “Flight Delays Data” in AML studio consists of 2,719,418 rows (observations) and 14 columns (variables). A more detailed overview for this dataset is provided in Activity 2 of the attached project report (.docx).

* Data Pre-processing, Cleansing and Model Building

For this project, a machine learning model which is aimed to predict how many minutes a flight will be delayed or early is built (hence the dependent variable is ArrDelay column of the dataset). Since ArrDelay is a variable of continuous value, this is a regression problem and the machine learning model shall be based on regression algorithm. However, prior to training the model, some data pre-processing (eg. joining of 2 datasets, data cleansing, standardization for selected numerical variables etc.) and some data visualization (using the Execute R Script module in AML studio) shall be done. After completing the data-preprocessing and data visualization, a regression model can be built in AML studio. 

* Reverse Engineering for Model Improvement

Once the base regression model is built, several techniques (reverse engineering) which can be used for improving model’s performance, such as feature selection, handling of outliers, hyperparameter tuning etc. will be performed in order to get the optimal model. Subsequently, cross-validation will be performed for the optimal model to check if it is well generalized. 

* Deployment of the Optimal Model

Finally, the optimal model will be published as web service, and it will be used to predict the ArrDelay of the test data ‘Test-Flights.csv’ using Excel Online. The predicted ArrDelay will then be compared with the real values and check if the optimal model can be performing well for real world data.

The following documents are provided in this repository:
  1. PML-0322A-Lee Jack Shiang-Project.docx: Word document for the project report
  2. Test-Flights.csv: Test data for the optimal model
