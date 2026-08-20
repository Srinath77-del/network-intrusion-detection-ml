# Machine Learning-Based Network Intrusion Detection System

## Project Overview

This project focuses on developing a machine learning-based Network Intrusion Detection System (NIDS) to identify whether network traffic is normal or malicious.

The project is being completed as part of the **Machine Learning Engineer Internship at YuvaIntern**.

## Objective

The main objective is to develop a machine learning pipeline that can analyze network traffic features and classify network connections into:

- Normal traffic
- Attack / malicious traffic

The project covers data preprocessing, feature engineering, machine learning model implementation, evaluation, validation, and model optimization.

## Dataset

The project uses the **UNSW-NB15 dataset**, created by the Australian Centre for Cyber Security (ACCS) at UNSW Canberra.

For the current analysis, the `UNSW_NB15_testing-set.csv` file is used.

Dataset details from the analyzed file:

- Records: 82,332
- Columns: 45
- Numerical columns: 41
- Categorical columns: 4
- Missing values: 0
- Duplicate rows: 0

The `id` column is excluded from machine learning features because it is a unique identifier.

The `attack_cat` column is also excluded from the binary classification features because it directly describes the attack category and would cause target leakage.

## Project Pipeline

```text
UNSW-NB15 Dataset
        ↓
Data Understanding
        ↓
Data Quality Analysis
        ↓
Data Cleaning
        ↓
Feature Selection
        ↓
Feature Engineering
        ↓
Categorical Encoding
        ↓
Feature Preprocessing
        ↓
Model Training
        ↓
Model Evaluation
        ↓
Validation
        ↓
Hyperparameter Optimization
        ↓
Final Analysis
## Internship Progress

### Week 2 – Data Preprocessing and Feature Engineering

Week 2 focuses on understanding and preparing the UNSW-NB15 dataset for machine learning.

#### Completed Analysis

- Dataset structure and feature analysis
- Missing-value analysis
- Duplicate-row analysis
- Target variable analysis
- Categorical feature analysis
- Numerical feature analysis
- Outlier analysis
- Correlation analysis
- Feature redundancy analysis
- Target leakage prevention
- Feature selection
- One-hot encoding
- Preprocessing pipeline

#### Week 2 Files

- [Week 2 Preprocessing Notebook](./UNSW_NB15_Preprocessing.ipynb)
- [Week 2 Report](./Srinath_week-02.docx)
- [Week 2 Documentation](./Week-2-Data-Preprocessing/README.md)

### Project Status

| Week | Status |
|---|---|
| Week 1 – Project Planning | Completed |
| Week 2 – Data Preprocessing | Completed |
| Week 3 – Model Implementation | Upcoming |
| Week 4 – Model Evaluation | Upcoming |
| Week 5 – Model Optimization | Upcoming |
| Week 6 – Final Report | Upcoming |
