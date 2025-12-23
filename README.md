# What Drives Customer Churn?
### Exploratory & Predictive Analysis of Telecom Customers

**Interactive Tableau Dashboard:**  
https://public.tableau.com/views/WhatDrivesCustomerChurn/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link



## Project Overview

This project analyzes customer churn in a telecom dataset to identify the key factors associated with customers leaving the service. The analysis combines **exploratory data analysis (EDA)** using Tableau with a **logistic regression model** built in Python to validate and quantify churn drivers.

The goal is to answer three main questions:
1. How prevalent is customer churn?
2. Which customer characteristics are associated with higher churn?
3. Which factors are the strongest predictors of churn?

---

## Tools & Technologies

- **Tableau Public** – Interactive dashboards and exploratory analysis  
- **Python** – Data cleaning and predictive modeling  
- **Pandas & NumPy** – Data manipulation  
- **scikit-learn** – Logistic regression modeling and evaluation  

---

## Interactive Dashboard

The Tableau dashboard explores churn patterns across multiple customer attributes, including:
- Contract type
- Tenure group
- Monthly charges
- Internet service type
- Support and add-on services

The dashboard is designed to move from high-level churn metrics to deeper insights about *why* customers churn.

---

## Dataset

The analysis uses a cleaned version of the Telco Customer Churn dataset, containing:
- Demographic information
- Service subscription details
- Billing behavior
- Customer tenure
- Target variable indicating whether a customer churned

Rows with missing billing information (e.g., tenure = 0) were removed, and categorical variables were grouped where appropriate for clearer analysis.

---

## Exploratory Data Analysis (Tableau)

Key findings from exploratory analysis include:

- **Month-to-month contracts** have significantly higher churn rates than one- or two-year contracts.
- Customers with **shorter tenure** are much more likely to churn.
- **Higher monthly charges** are associated with increased churn risk.
- Customers with **additional support services** (e.g., tech support, online security) churn less frequently.

These insights are visualized using bar charts, box plots, and heatmaps in Tableau.

---

## Predictive Modeling (Python)

A **logistic regression model** was trained to predict customer churn and quantify the importance of different features.

### Model Details
- **Target:** Customer churn (Yes / No)
- **Evaluation Metric:** AUC (Area Under the ROC Curve)

### Model Performance
- **AUC = 0.83**

An AUC of 0.83 indicates strong ability to distinguish between customers who churn and those who do not.

Logistic regression and random forest models were considered for churn analysis. Logistic regression was selected as the primary model because it provides interpretable coefficients that clearly indicate the direction and relative strength of each churn driver. While random forests can capture non-linear relationships and interactions, their feature importance scores do not indicate whether features increase or decrease churn risk. Given the strong performance of logistic regression (AUC = 0.83), interpretability was prioritized over marginal gains in predictive accuracy.

---

## Feature Importance & Key Predictors

Model coefficients were used to interpret feature importance:

- **Tenure** is the strongest predictor of churn — longer tenure greatly reduces churn risk.
- **Contract type** is highly influential — long-term contracts significantly reduce churn.
- **Monthly charges** increase churn likelihood, particularly for newer customers.
- **Internet service type** (e.g., fiber optic) and lack of support services are associated with higher churn.

These results confirm and extend the patterns observed during exploratory analysis.

---

## Conclusions

- Customer churn is primarily driven by **tenure and contract structure**.
- Pricing factors such as monthly charges play a meaningful but secondary role.
- Retention strategies should focus on **new customers**, **month-to-month contracts**, and **high-cost plans**.
- Combining Tableau-based EDA with predictive modeling provides both intuitive and quantitative insights.



This project demonstrates an end-to-end analytics workflow:
- Data cleaning
- Exploratory visualization
- Predictive modeling
- Model interpretation
- Business-focused conclusions

The Tableau dashboard serves as the primary visualization tool, while Python is used for statistical validation and feature importance analysis.
