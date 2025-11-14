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

1. Count, Unique, Top, Frequency, Mean, STD, Min, 25%, 50%, 75%, Max
2. Null Ratio
3. Unique Counts
4. Is Duplicated
5. Remove unnecessary rows
6. Check logical anomalies.

### SQL Cleaning Steps:

1. Remove duplicate records
2. Handle null regions

### Insights after cleaning:
1. During data validation, I identified 322 records where the customer’s tenure implied they opened accounts as minors (Age–Tenure < 18). I confirmed this wasn’t a known business scenario, so I removed those rows to maintain data integrity. I also noted it in my data quality report to ensure transparency.
2. Removed the "Row number"  and "Surname" columns cause they felt unnecessary for the analysis.
3. Checked for null, unique, and duplicate values.
4. Geography imbalance: Only 3 countries' data is there. France 50%, Germany 25% and Spain 24%. The dataset is heavily skewed.
5. Roughly 54% males, 46% females — not severe but relevant if analyzing gender-based churn trends.
6. Customers under 20 are 4, and over 60 are 464
7. While analyzing customer financial data, I discovered that ~35% of customers had a recorded balance of zero, including 1,700+ with high income. Since most were still active, I inferred this was a data capture or product-specific issue rather than true inactivity. Instead of dropping them, I flagged and treated zero balances as missing values to preserve integrity while still being able to analyze churn drivers accurately.
8. Created derived features:
    Balance_to_Salary_Ratio
    Product_Engagement_Score = NumOfProducts + IsActiveMember + HasCrCard
9. I performed a detailed anomaly and data integrity check on the product dataset. It showed balanced distribution across five product types, no duplicates or missing data, and around 4,000 inactive product records. However, I identified 822 customers with all products inactive — a key retention risk segment that I flagged for targeted engagement strategies.

## 4. Exploratory Data Analysis (EDA)

### Key EDA Questions:

** What’s the distribution of customer age, account types, and regions?

** Which regions have the highest inactive accounts?

** How does transaction frequency correlate with account balance?

** What proportion of customers use multiple products?

### Python EDA:

### Insights:
1. When I analyzed correlations between customer activity and churn, I observed that transactional metrics such as frequency and average transaction amount had negligible correlation with churn (|r| < 0.01). However, account balance showed a weak positive correlation (r ≈ 0.12), indicating that high-value customers are slightly more prone to exit — possibly due to unmet service expectations. This finding led me to recommend targeted retention programs for premium customers and further analysis into non-transactional churn drivers.
2. When analyzing customer engagement by region, I found that average transaction frequency was nearly identical across France, Spain, and Germany (~12 transactions each). This suggests geography does not meaningfully drive customer behavior in this dataset, so it is not a strong feature for segmentation or churn prediction. Instead, I focused on behavioral features such as product engagement, tenure, and balance to derive actionable insights.
3. When I analyzed customer activity by geography, both transaction frequency and average transaction value were nearly identical across France, Spain, and Germany. This indicates that geography does not meaningfully influence customer behavior in this dataset. Therefore, I deprioritized geography as a segmentation and predictive feature, focusing instead on behavioral factors such as product engagement, tenure, and balance.
4. My analysis showed that both transaction frequency and average transaction amount were almost identical for churned and retained customers. This indicates that transactional activity does not meaningfully explain churn behavior in this dataset. Therefore, I focused my modeling and retention strategy on product engagement, tenure, credit score, and balance, which showed much stronger relationships with churn.
5. Age-wise analysis showed that both transaction frequency and average transaction amount vary only slightly across age groups, with all customers averaging around 12 transactions. This indicates that age does not meaningfully influence customer activity in this dataset. As a result, I did not use age as a primary segmentation or predictive feature, and instead focused on behavioral and financial metrics such as product engagement, tenure, and account balance.

### The Real Causes of Churn
1. Low Product Engagement
Customers with:
Only 1 product = 28% churn
Low engagement score = 35% churn

** They are not tied to the bank → leave easily.

2. Forced or Wrong Product Cross-Sell
Customers with:
3 products = 83% churn
4 products = 100% churn
Engagement score of 5–6 = 82–100%

** They feel overloaded or mis-sold → churn extremely high.

3. Inactive Customers
Inactive: 27.45% churn
Active: 14.55% churn

** Engagement is the strongest indicator of loyalty.

4. Low-Balance Customers Leave More
0–50k balance → 35% churn

** No financial stake → easy exit.

6. Low-Credit Customers Churn More

Poor credit → 24% churn
Excellent credit → 19% churn

** Credit constraints → dissatisfaction.

6. Tenure Effects

New customers churn early
Very old customers churn somewhat
Middle-tenure customers stay

** Onboarding & re-engagement required.

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
