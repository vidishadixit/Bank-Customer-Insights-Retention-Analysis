# Bank Customer Insights & Retention Analysis

## 1. Project Overview

### Goal:
To analyze customer behavior and retention patterns using transaction and profile data from a mid-sized retail bank. 
The aim was to identify key factors leading to customer churn, uncover revenue-impacting inactivity, and recommend strategies to improve retention.

### Key Outcomes:

## 2. Data Description (Kaggle-sourced Dataset)

https://www.kaggle.com/datasets/saurabhbadole/bank-customer-churn-prediction-dataset/discussion/532881

100k rows.

### Table: 

A) Churn_Modelling

1. Row Number
2. CustomerID
3. Surname
4. CreditScore
5. Geography
6. Gender
7. Age
8. Tenure
9. Balance
10. NumofProducts
11. HasCrCard
12. IsActiveMember
13. EstimatedSalary
14. Exited

B) Products

1. CustomerId
2. Product_type
3. Enrollment_Date
4. Status

C) Transactions

1. Transaction_id
2. Customer_id
3. Transaction_date
4. Transaction_Type
5. Amount

## 3. Data Cleaning & Transformation

### Tools: Python (Pandas, NumPy) + SQL

### Python Cleaning Steps:


### SQL Cleaning Steps:

-- Remove duplicate records

-- Handle null regions


## 4. Exploratory Data Analysis (EDA)

### Key EDA Questions:

** What’s the distribution of customer age, account types, and regions?

** Which regions have the highest inactive accounts?

** How does transaction frequency correlate with account balance?

** What proportion of customers use multiple products?

Python EDA:


Insights:



## 5. KPI & Dashboard Design (Power BI)

## KPIs:



### Power BI Visuals:



## 6. Insights & Business Recommendations

Findings:



Recommendations:



## 7. Discussion Points

Technical Angle:

Talk about Python + SQL for cleaning and joining large datasets.

Explain your EDA and visualization logic (why you chose those KPIs).

Discuss how you validated your findings (cross-verification in Excel/Power BI).

Analytical / Business Angle:

Highlight how you translated data into actions (customer retention strategy).

Quantify your impact (15% retention improvement).

Show structured problem-solving — identifying churn → measuring loss → proposing solutions.
