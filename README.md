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

A) Customers

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

### Insights after cleaning:
1. During data validation, I identified 322 records where the customer’s tenure implied they opened accounts as minors (Age–Tenure < 18). I confirmed this wasn’t a known business scenario, so I removed those rows to maintain data integrity. I also noted it in my data quality report to ensure transparency.
2. Removed the "Row number"  and "Surname" columns cause they felt unnecessary for the analysis.
3. Checked for null, unique, and duplicate values.
4. Geography imbalance: Only 3 countries' data is there. France 50%, Germany 25% and Spain 24%. The dataset is heavily skewed.
5. Roughly 54% males, 46% females — not severe but relevant if analyzing gender-based churn trends.
6. Customers under 20 are 4, and over 60 are 464
7. While analyzing customer financial data, I discovered that ~35% of customers had a recorded balance of zero, including 1,700+ with high income. Since most were still active, I inferred this was a data capture or product-specific issue rather than true inactivity. Instead of dropping them, I flagged and treated zero balances as missing values to preserve integrity while still being able to analyze churn drivers accurately.
8. Capped outliers in Age, CreditScore, and EstimatedSalary.
9. Created derived features:
    Balance_to_Salary_Ratio
    Product_Engagement_Score = NumOfProducts + IsActiveMember + HasCrCard
10. I performed a detailed anomaly and data integrity check on the product dataset. It showed balanced distribution across five product types, no duplicates or missing data, and around 4,000 inactive product records. However, I identified 822 customers with all products inactive — a key retention risk segment that I flagged for targeted engagement strategies.
11. 

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
