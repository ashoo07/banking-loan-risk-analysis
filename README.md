## **banking-loan-deposit-risk-analysis**

Banking Loan, Deposit & Risk Analysis

## Overview

A banking analytics portfolio project built with **Python,
PostgreSQL/SQL, and Power BI**. The project analyzes 3,000 customer
records across lending, deposits, income, occupation, banking
relationships, and the dataset's Risk Weighting field.

> **Important:** The dataset contains `Risk Weighting` but does not
> contain a separate observed default/non-default flag. Therefore, this
> project should be described as **risk segmentation / risk analysis**

## Project Objectives

-   Explore customer and financial characteristics
-   Clean and transform banking data
-   Create income bands and readable categorical fields
-   Store/query the dataset using PostgreSQL
-   Build DAX measures for loan, deposit and customer KPIs
-   Build an interactive Power BI dashboard
-   Analyze loan exposure by occupation and banking relationship
-   Examine risk weighting across income and financial variables

## Tools

-   Python: pandas, NumPy, Matplotlib, Seaborn
-   PostgreSQL / SQL
-   Power BI Desktop / DAX
-   Jupyter Notebook

## Dataset

-   Records: 3,000
-   Columns: 26
-   Missing values: 0
-   Main lending fields: Bank Loans, Business Lending, Credit Card
    Balance
-   Main deposit fields: Bank Deposits, Checking Accounts, Saving
    Accounts, Foreign Currency Account
-   Risk field: Risk Weighting (1--5 in the supplied data)

## Key DAX Measures

``` dax
Total Clients = DISTINCTCOUNT(banking[Client ID])

Total Loan =
SUM(banking[Bank Loans])
+ SUM(banking[Business Lending])
+ SUM(banking[Credit Card Balance])

Total Deposit =
SUM(banking[Bank Deposits])
+ SUM(banking[Checking Accounts])
+ SUM(banking[Saving Accounts])
+ SUM(banking[Foreign Currency Account])
```

## Key Findings

-   Risk Weighting **2** is the largest segment: **1,222 customers (40.7%)**.
-   Risk Weighting **5** contains **160 customers (5.3%)**.
-   The correlation between Risk Weighting and Estimated Income is
    **0.665**. This is descriptive correlation, not causation.
-   The largest Bank Loan totals by occupation in the supplied data
    include **Account Coordinator**, **Database Administrator III**, and
    **Office Assistant III**.
-   The Power BI report includes HOME, LOAN ANALYSIS, DESPOSIT ANALYSIS,
    and SUMMARY pages.

## Dashboard

The Power BI dashboard includes:

Key performance indicators
Loan analysis
Deposit analysis
Customer and banking relationship filters
Summary insights

screenshots/ <img width="887" height="499" alt="home-dashboard" src="https://github.com/user-attachments/assets/07b13a2b-7e50-4918-8963-94246105caac" />

screenshots/<img width="884" height="499" alt="loan-analysis" src="https://github.com/user-attachments/assets/2fd218fd-c489-4b55-99d2-51908ea23ebe" />

screenshots/<img width="767" height="430" alt="deposit-analysis" src="https://github.com/user-attachments/assets/88bf647c-15ef-48d3-a123-675e6ba26aef" />

<img width="753" height="425" alt="summary-dashboard" src="https://github.com/user-attachments/assets/088f7cf0-4283-444b-b313-7d6d55b19c23" />



## Repository Structure

``` text
banking-loan-risk-analysis/
├── data/
│   └── Banking(1).csv
├── notebooks/
│   └── Banking_EDA.ipynb
├── sql/
│   └── banksql.sql
├── powerbi/
│   └── Banking Dashboard 1.pbix
├── report/
│   └── Banking_Loan_Risk_Analysis_Report.pdf
└── README.md
```

## How to Reproduce

1.  Open `Banking_EDA.ipynb` in Jupyter Notebook.
2.  Install the required Python packages.
3.  Load the CSV and perform the EDA/feature engineering.
4.  Create/import the `banking` table in PostgreSQL.
5.  Run the SQL queries in `banksql.sql`.
6.  Open the PBIX file in Power BI Desktop.
7.  Refresh the data/model if required.

## Portfolio Note

For a stronger future version, add a real default target and a
classification model (for example, logistic regression or tree-based
classification) with appropriate validation metrics. Do not label the
current project as a predictive default model because the supplied data
does not include a default outcome.
