# Banking Risk Analytics Dashboard (Power BI)

## Project Overview

This project analyzes banking customer data to understand **loan exposure, deposit distribution, and customer engagement patterns** using Power BI.

The objective is to demonstrate how financial institutions can use data analytics to **monitor lending risk, evaluate customer profiles, and identify high-value clients through interactive dashboards**.

The dashboard provides a centralized view of financial metrics including **loan distribution, deposits, credit exposure, and customer engagement**, helping support data-driven decision-making in the banking sector.

---

# Business Problem

Banks face significant financial risk when approving loans without analyzing customer financial behavior.

Without proper insights, banks may:

* Approve loans for high-risk customers
* Misjudge credit exposure
* Fail to identify profitable client segments
* Miss opportunities to optimize deposit strategies

This project demonstrates how **data visualization and financial analytics can help banks better understand their customers and reduce lending risk.**

---

# Dataset Description

The dataset contains banking client information stored across multiple relational tables.

These tables are connected using **primary keys and foreign keys**, enabling structured financial analysis.

### Key Tables

* Clients Banking
* Banking Relationship
* Gender
* Investment Advisor
* Period

### Key Fields

* Client ID
* Estimated Income
* Bank Loans
* Business Lending
* Credit Card Balance
* Bank Deposits
* Savings Accounts
* Checking Accounts
* Foreign Currency Accounts
* Client Joining Date

The dataset enables analysis of **customer financial activity, loan exposure, and deposit behavior.**

---

# Data Preparation & Feature Engineering

### Engagement Duration

A calculated column was created to measure how long a client has been associated with the bank.

```
Engagement Days =
DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)
```

### Income Segmentation

Customers were categorized into income groups to analyze financial behavior.

| Income Range | Category    |
| ------------ | ----------- |
| < 100K       | Low Income  |
| 100K – 300K  | Mid Income  |
| > 300K       | High Income |

This segmentation helps identify **which income groups contribute most to lending and deposits.**

### Processing Fee Estimation

A calculated column was created to estimate processing fees based on the fee structure applied to financial products.

---

# Data Modeling

A relational data model was built in Power BI connecting multiple tables.

This model enables:

* Cross-table financial analysis
* Customer segmentation
* Aggregated financial metrics
* Interactive filtering within dashboards

---

# Key Performance Indicators (KPIs)

The dashboard tracks several banking performance metrics.

| KPI                 | Description                                                                   |
| ------------------- | ----------------------------------------------------------------------------- |
| Total Clients       | Number of banking customers                                                   |
| Total Loan          | Combined value of bank loans, business lending, and credit card balances      |
| Total Deposit       | Total funds deposited across savings, checking, and foreign currency accounts |
| Total Fees          | Estimated banking fees generated from lending activities                      |
| Bank Loan           | Personal loan exposure                                                        |
| Business Lending    | Loans issued to businesses                                                    |
| Credit Card Balance | Outstanding credit card liabilities                                           |

---

# Key DAX Measures

### Total Clients

```
Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])
```

### Total Loan

```
Total Loan = [Bank Loan] + [Business Lending] + [Credit Cards Balance]
```

### Total Deposit

```
Total Deposit =
[Bank Deposit] +
[Savings Account] +
[Foreign Currency Account] +
[Checking Accounts]
```

### Total Fees

```
Total Fees =
SUMX(
'Clients - Banking',
[Total Loan] * 'Clients - Banking'[Processing Fees]
)
```

---

# Dashboard Components

## Loan Analysis

This section analyzes loan distribution across different dimensions.

Insights include:

* Loan distribution by income band
* Loan distribution by nationality
* Total credit exposure across loan types

These insights help banks understand **which customer groups contribute the most to lending risk.**

---

## Deposit Analysis

This section analyzes how customers allocate their funds across different banking accounts.

Metrics include:

* Savings accounts
* Checking accounts
* Foreign currency accounts
* Total bank deposits

This helps banks understand **deposit concentration and customer financial behavior.**

---

## Executive Summary Dashboard

The summary dashboard provides a high-level overview of the banking dataset including:

* Total clients
* Total loan exposure
* Total deposits
* Total banking fees
* Customer engagement duration

This allows decision-makers to quickly evaluate **overall financial performance and credit exposure.**

---

# Key Insights

* Mid-income clients contribute the largest share of total loan exposure.
* Total loan value exceeds total deposits, indicating higher credit exposure.
* Savings accounts represent the largest share of deposited funds.
* Customer engagement duration varies significantly across client groups.
* Loan distribution varies across geographic regions and income segments.

These insights help financial institutions **better understand lending behavior and customer financial patterns.**

---

# Tools & Technologies

* Power BI
* DAX (Data Analysis Expressions)
* Data Modeling
* Data Cleaning
* Financial Data Analysis
* Interactive Dashboard Design

---

# Project Structure

```
Banking-Risk-Analytics-Dashboard
│
├── Banking Dashboard.pbix
├── datasets
│   ├── banking_clients.csv
│   ├── banking_relationships.csv
│   └── gender.csv
│
├── images
│   ├── dashboard_home.png
│   ├── loan_analysis.png
│   └── deposit_analysis.png
│
└── README.md
```

---

# Future Improvements

Possible enhancements for this project include:

* Credit risk prediction models
* Loan default probability analysis
* Customer segmentation using machine learning
* Time-series analysis of financial trends
* Integration with real-time financial data pipelines

---

# Learning Outcome

This project demonstrates practical experience in:

* Financial data analysis
* Power BI dashboard development
* Data modeling using relational datasets
* Creating actionable insights from financial data
* Designing dashboards for business decision-makers

---

# Disclaimer

This project is developed for **data analytics learning purposes** using publicly available banking datasets.


Lakshay Pandey