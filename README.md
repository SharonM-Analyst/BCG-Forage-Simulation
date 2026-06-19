# PowerCo Customer Churn Analysis

---

## Overview

**Client:** PowerCo a major gas and electricity utility supplying small and medium-sized enterprises (SMEs).

**Problem Statement:**
The energy market has grown increasingly competitive, giving customers more options than ever before. PowerCo began experiencing elevated **customer churn** — the loss of customers who switch to rival energy providers. PowerCo engaged BCG's Data Science team to diagnose the root cause of this churn.

**Core Hypothesis:**
The Associate Director (AD) of the Data Science team proposed that churn may be driven by **price sensitivity** — how much pricing is a factor in a customer's decision to stay with or leave PowerCo.

**Objective:**
Test the hypothesis that churn is driven by customers' price sensitivity by modelling churn probabilities and deriving the effect of prices on churn rates.

<!-- MLOps Workflow -->
<p align="center">
  <a href="chustomer_churn.html">
    <img src="https://img.shields.io/badge/PowerCo%20Customer Churn-Prediction Model-blue?style=for-the-badge" />
  </a>
</p>

![Customer Churn](https://github.com/SharonM-Analyst/BCG-Forage-Simulation/blob/3910bb50c1e6c2cc59572d0bb1a317ef0738a6a1/2.%20Project%20Planning/Screenshot%202026-06-19%20053627.png)

---

## Datasets Required

To build the models, three key data sources were identified:

| Dataset | Description |
|---|---|
| **Customer Data** | Client characteristics:industry, historical electricity consumption, date joined, etc. |
| **Churn Data** | Binary indicator of whether a customer has churned |
| **Historical Price Data** | Prices charged to each customer for electricity and gas at granular time intervals |

---

## Methodology & Approach

The case study followed a structured five-step analytical workflow:

### Step 1: Define Price Sensitivity
- Establish a clear, quantifiable definition of price sensitivity
- Calculate price sensitivity metrics per customer using the historical price data

### Step 2: Data Preparation & Feature Engineering
- Clean and merge the customer, churn, and pricing datasets
- Engineer relevant features including price change rates, consumption patterns, contract duration, and customer segments
- Handle missing values, outliers, and class imbalance in the churn target variable

### Step 3: Hypothesis Testing via Binary Classification
- Frame churn prediction as a **binary classification problem** (churned = 1, retained = 0)
- Train and evaluate multiple models:
  - **Logistic Regression**- interpretable baseline
  - **Random Forest**- captures non-linear relationships and feature interactions

### Step 4: Model Selection
- Evaluate models on accuracy metrics: AUC-ROC, precision, recall, F1-score
- Factor in **explainability** alongside performance- critical for client-facing recommendations
- Select the best-performing model that balances predictive power with interpretability

### Step 5: Quantify Price Sensitivity's Effect on Churn
- Use the trained model to extrapolate the extent to which price sensitivity drives churn
- Derive feature importance scores and partial dependence plots to isolate the price signal
- Translate model outputs into actionable business insights for PowerCo

---

## Key Insights & Findings

- **Price sensitivity was identified as a measurable and significant driver of churn**, supporting the core hypothesis
- Customers with higher exposure to price fluctuations showed elevated churn probabilities
- **Random Forest outperformed Logistic Regression** on discriminative metrics while retaining sufficient explainability via feature importance
- Feature engineering of price deltas and consumption volatility were among the most predictive signals
- The analysis provided PowerCo with a prioritised list of at-risk customers, enabling targeted retention interventions (e.g. personalised discount offers)

---

## Tools & Technologies Used

| Category | Tools |
|---|---|
| **Language** | Python |
| **Data Manipulation** | pandas, NumPy |
| **Machine Learning** | scikit-learn (Logistic Regression, Random Forest, model evaluation) |
| **Exploratory Data Analysis** | matplotlib, seaborn, plotly |
| **Feature Engineering** | Custom price sensitivity metrics, rolling statistics |
| **Model Evaluation** | AUC-ROC, confusion matrix, classification report |
| **Notebook Environment** | Jupyter Notebook / Databricks |
| **Version Control** | Git |

---

## Summary

> This case study investigated whether **price sensitivity is a primary driver of customer churn** at PowerCo, a gas and electricity utility for SMEs. Using customer, churn, and historical pricing data, price sensitivity features were engineered and fed into binary classification models. A **Random Forest classifier** delivered the best performance and confirmed that price sensitivity is a statistically meaningful predictor of churn. The final model enables PowerCo to identify at-risk customers proactively and deploy targeted retention strategies — directly addressing the business problem that motivated the engagement.

---

*Case study completed as part of BCG Data Science virtual experience program.*
