# Ironhack - Mid-Bootcamp Project

## Business Background

**Position:** Risk Analyst  
**Business:** Bank  
**Business Services:** Banking, Loans, Credit Cards  
**Business Objective:** Understanding the demographics/characteristics of customers that accept/do not accept credit cards + adjacent findings  
**Data Gathering Process:** The bank designed a focused marketing study, with 18,000 current bank customers. This focused approach allows the bank to know who does and does not respond to the credit card offer, and to use existing demographic data already available on each customer.  

## Data Science Background

**Data**: The data set consists of information on 18,000 current bank customers in the study. 

> These are the definitions of data points provided:

> - **Customer Number**: A sequential number assigned to the customers (this column is hidden and excluded – this unique identifier will not be used directly).
> - **Offer Accepted**: Did the customer accept (Yes) or reject (No) the offer. Reward: The type of reward program offered for the card.
> - **Mailer Type**: Letter or postcard.
> - **Income Level**: Low, Medium or High.
> - **#Bank Accounts Open**: How many non-credit-card accounts are held by the customer.
> - **Overdraft Protection**: Does the customer have overdraft protection on their checking account(s) (Yes or No).
> - **Credit Rating**: Low, Medium or High.
> - **#Credit Cards Held**: The number of credit cards held at the bank.
> - **#Homes Owned**: The number of homes owned by the customer.
> - **Household Size**: Number of individuals in the family.
> - **Own Your Home**: Does the customer own their home? (Yes or No).
> - **Average Balance**: Average account balance (across all accounts over time). **Q1, Q2, Q3 and Q4**
> - **Balance**: Average balance for each quarter in the last year

**Data Science Objectives:** 
- Find the type of clients accepting credit card offers
- Build a classification model able to predict if future customers are likely to accept a credit card offer based on their characteristics (to allow targetted customer offers)
- Offer recommendations to the bank based on findings, e.g. if it should focus more on a specific type of loyalty program or client type
- Provide ideas for further exploration & analysis, e.g. which credit card customer segment is the most profitable

## Data Science Process

### [1. Initial Data Exploration (SQL)](https://github.com/sabinagio/data_mid_bootcamp_project_classification/blob/master/deliverables/1.initial-data-exploration-sql.ipynb)
The initial data exploration process involved the creation of an SQL database, followed by some basic queries to better understand the dataset.

### [2. Data Cleaning, Wrangling & Exploration (Pandas)](https://github.com/sabinagio/data_mid_bootcamp_project_classification/blob/master/deliverables/2%2C3.data-cleaning-wrangling-and-EDA.ipynb)
The data cleaning & wrangling process was minimal due to the data being relatively clean to begin with. The only notable modification was the removal of customer data where there was no average balance data recorded. 

### [3. Exploratory Data Analysis (Pandas, Tableau)](https://public.tableau.com/app/profile/sabina.firtala/viz/Credit-Card-Interest-Analysis/EDA)
During the EDA process, we were able to observe some commonalities across customers accepting credit card offers, such as lower credit ratings and lack of overdraft protection.

### [4. Data Pre-processing & Classification Model (Scikit-Learn)](https://github.com/sabinagio/data_mid_bootcamp_project_classification/blob/master/deliverables/4.data-preprocessing-and-classification-models.ipynb)
To prepare the data for modelling, the outliers were removed from numerical columns and the numerical data scaled, whereas the categorical data was encoded so it becomes a numerical feature for the prediction models.

The models used were logistic regression and K-Nearest Neighbors (with multiple neighbor values), in the presence and absence of SMOTE oversampling - which was applied only to the training dataset.

The best model in terms of prediction accuracy across both accepted & rejected offers was logistic regression where the training set was oversampled using SMOTE - 69% for rejected offers and 67% for accepted offers.

Next steps would involve choosing different models (e.g. random forest) or explore different feature selections to improve the prediction accuracy.
