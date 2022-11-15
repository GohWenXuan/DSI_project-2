# GA Project 2: Ames Housing Saleprice Challenge
## Goh Wen Xuan

## Problem Statement

We are a team of data scientist. We are tasked by our Client who is a group Property Agents who are looking to expand into the Iowa property market. We are tasked to predict the prices of houses based on their characteristics. 

Our client is also interested in understanding what are the important variables that affects house prices in order to understand what are the most important data to be collected to predict the prices of future house listings on their site.

## Executive Summary

We are provided with Ames Housing data set which contains information from the Ames Assessor’s Office used in computing assessed values for individual residential properties sold in Ames, Iowa from 2006 to 2010. The data has 82 columns which include 23 nominal, 23 ordinal, 14 discrete, and 20 continuous variables (and 2 additional observation identifiers).

## Data Dictionary
The link to the data dictionary is [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt). 

## Methodology

**Initial Data Cleaning and EDA**
The train.csv contains 2051 rows and 81 columns. From initial data exploratory, multiple feature are observed to have many missing values, ranging up to 99.5%. Each missing feature is investigated and the missing values are either dropped or filled in methodically with explaination behind them. The cleaning method is applied for both train and test dataset. 

**Preprocessing**
Out of the 81 columns, or thereby refered to as 'feature', there are 39 numerical features and 42 categorical features in the train dataset

Categorical features refers to qualitative data types such as 'Mas Vnr Type' (Masonary Veneer Type) or 'Garage Type'. These various features are represented by objects. On the other hand, numerical features are more straight-forward and the different category are represented by numerical values. For machine learning/ modeling purpose, both categorical and numerical features have to be converted to numerical values by using encoding. 

Each feature is then plotted against sales price to determine which feature are correlated among each other. To further explore the correlation, the correlation function and Recursive Feature Elimination (RFE) to further narrow the top features.

**Feature Engineering**
Feature engineering is performed to eliminate features that are considered multicollinearity as that would impact the model negatively. Categorical and numeric features are encoded accordingly by one-hot encoding and ordinal encoding prior to model prediction. 

**Modelling**
Three prediction models were used: Lasso Regression, Lasso Regression and Ridge Regression. Each models are evaluated with one another to determined which model fits best. Out of the models used, lasso provides the best score. 

## Conclusions and Recommendations
Several features are found to be highly related to sales price. These includes `overall quality`, `exterior quality`, `above ground living area` and `kitchen quality`. It is recommend to gather information on these feature of a property to accurately evaluate the price of the property. For ongoing data collection effort, it is also worth considering assessing a property by these feature to provide a accurate prediction of the property price.

## Limitation
There are external factors that could affect the housing price and would useful to have the following data: economy of the state, demographics and housing policy. It could also be beneficial to understand how the Housing Data is collected to understand if the missing values are truly missing or if the feature does not exist. 

Another point to consider this model does not take consideration of the inflation of housing prices. For example, housing prices throughout in US has been increasing steadily over the years ever since the financial crisis in 2008. The model would need significant adjustment to predict the current house based on the latest inflation rate.