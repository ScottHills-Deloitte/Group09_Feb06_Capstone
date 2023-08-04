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
We used a Classification type, Random Forest Model as our final predictor for our Future Business Health target variable.

*Success Criteria:* 
Can we predict with an acceptable level of accuracy the business health target variable for an individual public company using the reported year-end financial data from the prior year?


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

![Code_Creating_Ratio_Fields](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/cb667a2d-7918-449d-bc60-449f607501bb)

![Code_dropping_Columns](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/d6d630e8-ca4d-4520-9213-635ebc81ef19)

![Code_solvency_rating](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/12fa08d5-ac85-4c06-9678-6f5051ba67e8)
![Code_Liq_prof_ratings](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/c125de9d-d6b8-4fb9-bffb-f96664efae58)
![Code_BusHealth_calc](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/303e1d8d-791b-4939-a4be-0680a1f63ba9)

![code_train_test_split](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/774b0108-56f4-4c2c-aa8e-264075b07ee0)
![code_LinearSVC1](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/88b25b52-0ca3-4f08-a29d-813cd0a35913)
![code_LinearSVC2](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/d7a1e052-1ef2-4ae1-8a27-acbcbcc319be)
![code_LinearSVC3](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/39958e06-6d59-438f-9e3e-ba8d60c0b633)

![code_RandomForestModel1](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/029b139d-fc6a-4f79-b59f-f8c536a3b66e)
![code_RandomForestModel2](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/90547aad-55d0-429b-a30f-bc291ffcd819)
![code_RandomForestModel3](https://github.com/ScottHills-Deloitte/Group09_Feb06_Capstone/assets/125297528/ab0d7b57-f9e0-4626-b839-c2d67c505280)


## Conclusion 
   
#### Future Work

1. Refresh the dataset to obtain financial information for the current period from 2019-2022
2. Review for changes in predictive modeling around impactful business events (pre and post-Covid, recessionary periods, etc.)
3. Obtain industry data for companies to review how the models are affected when used for specific industry categories.
4. Include outstanding stock and price of stock at YE to review any effects on the model as build.

#### For More Information
Please review the full analysis in our [Jupyter Notebook](Group9_FinalNotebook.ipynb) or [presentation deck](Group 09_Final Capstone Presentation.pptx).

## Repository Navigation

```
MAIN
├── DATA                                          <- Kaggle repository download for American Companies Financial Report Data
│   ├── american_bankruptcy.csv                        <- American Companies Financial Data
│   ├── american_bankruptcy_datafile_original.zip      <- Downloaded zip file of dataset from Kaggle.com
│   ├── american_bankruptcy_updated.csv                <- American Companies Financial Data (**working version used in final notebook**)
├── IMAGES                                        <- file containing any visualizations found throughout the project
├── GROUP 9_JUNE 23.pdf                           <- PDF version of project proposal. 
├── README.md                                     <- Project README file
├── GROUP 9_FINAL_NOTEBOOK.ipynb                  <- Technical and narrative documentation in Jupyter Notebook
├── GROUP 09_Final Capstone Presentation.pdf      <- PDF version of final project presentation
├──(Branches)                                     <- Individual Branches for each project member
│   ├── DATA
│   ├── IMAGES
│   notebookname.ipynb                                 <- Individual notebooks each project member
```
