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
