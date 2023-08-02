![Header_Image](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/01a5268d-841a-4149-a972-7d5215233da8)
# Predicting the future health and investability of public companies using published financial data.
_Using standard released financial data along with machine learning classification models to predict an overall health/investment rating for a business_

## Business Problem 
There needs to be more comprehensive and reliable tools for individual investors to assess a company's financial stability and potential for sustainable growth. 
When relying on traditional financial metrics and analysis, many investors need help identifying healthy companies to invest in.  
This is because these metrics only partially capture the entire picture of a company's long-term viability.

## The Solution

*Objective:* Our Focus is to assist individual investors by building a predictive machine learning model (**Business Health Predictor**) to rate individual companies with a business health grade as a suggestive indicator for investment worthiness. 

*Method:*

*Success Criteria:* 


## Data Understanding and Preparation
The data source for this project is a Kaggle.com repository for American companies listed on the New York Stock Exchange and NASDAQ. The dataset comprises financial data from 8,000+ distinct companies recorded during the period spanning from 1999 to 2018. 

###### Source of Data
https://www.kaggle.com/datasets/utkarshx27/american-companies-bankruptcy-prediction-dataset

###### Data Dictionary
![dataset_datadictionary](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/8aab8553-551d-4d75-82ec-fab4313a5009)

###### Data Investigation Findings
- That data is anonymized so that we don't know the actual names of the companies.
- There are no industry categories or stock history data provided.
- There are 8,262 distinct companies in the dataset.
- There are no null values in the dataset to discard. 
- All data features are in numeric format except for the company name and status label fields. These must either be removed from the model or converted to a numeric value using an encoding process.
- All numeric monetary features are in the same format and rounded to the same precision.

## Modeling and Evaluation

![code_python_libraries](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/ca9c8349-29a5-420b-9584-cd051521c542)

![Code_Data_load](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/011b0eae-f129-431c-8c1a-807c96d91241)

_Data required minimal cleanup and preparation_ 
 - We renamed most column headings to be clear and understand what is contained in each column._
 - Dropping the categorical columns that do not effect the performance of the dataset as well as dropping the columns that were used to find the ratios that determine the necessary ratings.

###### Creating Ratios to use for Targe Prediction
Creating ratios and rating that are built from financial data listed in the dataset. We determined these rations to cover three major aspects of business, Solvency, Liquidity, Profitability. These ratings were determined by comparing the results to that of other businesses. The solvency, liquidity, and profitability ratings are then added up to get the overall business health of the organization. This overal business helath is what will be used as the target variable for the model.




## Conclusion 
   
#### Future Work

1. Refresh the dataset to obtain financial information for the current period from 2019-2022
2. Review for changes in predictive modeling around impactful business events (pre and post-Covid, recessionary periods, etc.)
3. Obtain industry data for companies to review how the models are affected when used for specific industry categories.
4. Include outstanding stock and price of stock at YE to reviw any affects on the model as build.

#### For More Information
Please review the full analysis in our [Jupyter Notebook](MainNotebook.ipynb) or [presentation deck](Group 09_Final Presentation.pptx).

## Repository Navigation

```
├── DATA                         <- Kaggle repository download for American Companies Financial Report Data
│   ├── american_bankruptcy.csv                    <- American Companies Financial Data
│   ├── american_bankruptcy_datafile_original.zip  <- Downloaded zip file of dataset from Kaggle.com
│   ├── american_bankruptcy_updated.csv            <- American Companies Financial Data (**working version used in final notebook**)
├── IMAGES                        <- file containing any visualizations found throughout the project
├── GROUP 9_JUNE 23.pdf           <- PDF version of project proposal. 
├── README.md                     <- Project README file
├── GROUP 9_FINAL_NOTEBOOK.ipynb  <- Technical and narrative documentation in Jupyter Notebook
├── project_presentation.pdf      <- PDF version of final project presentation
```
