# Data Science Salary Estimator: Project Overview 
* Created a tool that estimates data science salaries (MAE ~ $ 11K) to help data scientists negotiate their income when they get a job.
* Performed Exploratory Data Analysis(EDA) on the data set to understand it and make some accurate discovery.
* Engineered features from the text of each job description to quantify the value companies put on python, excel, aws, and spark. 
* Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model. 


## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn,pickle  


## Data Overview

*	Job title
*	Salary Estimate
*	Job Description
*	Rating
*	Company 
*	Location
*	Company Headquarters 
*	Company Size
*	Company Founded Date
*	Type of Ownership 
*	Industry
*	Sector
*	Revenue
*	Competitors 

## Data Cleaning
After scraping the data, I needed to clean it up so that it was usable for our model. I made the following changes and created the following variables:

*	Parsed numeric data out of salary 
*	Made columns for employer provided salary and hourly wages 
*	Removed rows without salary 
*	Parsed rating out of company text 
*	Made a new column for company state 
*	Added a column for if the job was at the company’s headquarters 
*	Transformed founded date into age of company 
*	Made columns for if different skills were listed in the job description:
    * Python  
    * R  
    * Excel  
    * AWS  
    * Spark 
*	Column for simplified job title and Seniority 
*	Column for description length 
## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables. 
![alt text](https://github.com/himalaypatel24/Data-Science-Project/blob/main/Data%20Science%20Salary%20Estimator:/Capture.PNG "Avg Salary For Differnt Job Role")
![alt text](https://github.com/himalaypatel24/Data-Science-Project/blob/main/Data%20Science%20Salary%20Estimator:/download%20(1).png "No Of Data Scintist Per State")
![alt text](https://github.com/himalaypatel24/Data-Science-Project/blob/main/Data%20Science%20Salary%20Estimator:/download%20(2).png "Avg Salary in K by State")

## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.   

I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.   

I tried three different models:
*	**Multiple Linear Regression** – Baseline for the model
*	**Lasso Regression** – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.
*	**Random Forest** – Again, with the sparsity associated with the data, I thought that this would be a good fit. 

## Model performance
The Random Forest model far outperformed the other approaches on the test and validation sets. 
*	**Random Forest** : MAE = 11.00
*	**Linear Regression**: MAE = 19.28
*	**Ridge Regression**: MAE = 19.82


## Refernce:
* KEN JEE: https://www.youtube.com/channel/UCiT9RITQ9PW6BhXK0y2jaeg
