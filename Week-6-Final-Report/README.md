# Week 6 – Final Report and Comprehensive Analysis

## Objective

The objective of Week 6 is to consolidate the complete six-week Machine Learning Engineer internship project and present the final analysis of the Machine Learning-Based Network Intrusion Detection System.

The project focuses on classifying network traffic into:

- Normal traffic
- Attack / Malicious traffic

The final report summarizes the complete machine learning workflow, including data preprocessing, feature engineering, model implementation, model evaluation, validation, optimization, results, challenges, and future improvements.

## Project Overview

The project uses the UNSW-NB15 dataset to develop a machine learning-based Network Intrusion Detection System.

The complete workflow followed:

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
Model Training  
↓  
Model Evaluation  
↓  
Validation  
↓  
Hyperparameter Optimization  
↓  
Final Analysis

## Dataset

The project uses the UNSW-NB15 dataset.

For the current project analysis, the following testing-set file was used:

`UNSW_NB15_testing-set.csv`

### Dataset Details

| Property | Value |
|---|---:|
| Records | 82,332 |
| Columns | 45 |
| Missing Values | 0 |
| Duplicate Rows | 0 |
| Normal Traffic | 37,000 |
| Attack Traffic | 45,332 |

The `id` column was excluded because it is a unique identifier.

The `attack_cat` column was excluded from binary classification because it directly describes the attack category and could cause target leakage.

After removing these columns, 42 input features were used:

- 39 numerical features
- 3 categorical features

Categorical features:

- `proto`
- `service`
- `state`

## Data Preprocessing

The following preprocessing and analysis tasks were completed:

- Dataset structure analysis
- Data type analysis
- Missing-value analysis
- Duplicate-row analysis
- Target distribution analysis
- Numerical feature analysis
- Categorical feature analysis
- Outlier analysis
- Correlation analysis
- Feature redundancy analysis
- Target leakage prevention
- Feature selection
- One-hot encoding
- Preprocessing pipeline

One-hot encoding was applied to the categorical features.

The preprocessing stage produced 190 transformed features.

## Model Implementation

Two tree-based machine learning models were considered during the project:

1. Decision Tree
2. Random Forest

### Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Decision Tree | 95.97% | 97.52% | 95.10% | 96.30% |
| Random Forest | 97.69% | 98.40% | 97.39% | 97.89% |

Random Forest produced better overall performance and was selected as the main model for further evaluation and optimization.

## Model Evaluation

The Random Forest model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- ROC-AUC
- Stratified 5-Fold Cross-Validation
- False Positive Rate
- False Negative Rate

### Evaluation Results

| Metric | Result |
|---|---:|
| Accuracy | 97.63% |
| Precision | 98.44% |
| Recall | 97.24% |
| F1-Score | 97.84% |
| ROC-AUC | 99.71% |

### Confusion Matrix

|  | Predicted Normal | Predicted Attack |
|---|---:|---:|
| Actual Normal | 7,260 | 140 |
| Actual Attack | 250 | 8,817 |

The model correctly identified 7,260 normal connections and 8,817 attack connections.

There were:

- 140 False Positives
- 250 False Negatives

## Cross-Validation

Stratified 5-fold cross-validation was used to check model stability.

The F1-scores obtained were:

- 0.9783
- 0.9791
- 0.9789
- 0.9801
- 0.9803

### Cross-Validation Summary

| Measure | Result |
|---|---:|
| Mean F1-Score | 0.9793 |
| Standard Deviation | 0.0007 |

The small standard deviation indicates stable performance across the validation folds.

## Model Optimization

Week 5 focused on Random Forest hyperparameter optimization.

The parameters investigated included:

- `n_estimators`
- `max_depth`
- `min_samples_split`
- `min_samples_leaf`
- `max_features`

Controlled experiments were performed using a validation subset.

### Optimization Results

| Configuration | Trees | Depth | Leaf | Features | Validation F1 |
|---|---:|---:|---:|---|---:|
| Baseline | 100 | None | 1 | Default | 0.9774 |
| Experiment 1 | 100 | 15 | 1 | sqrt | 0.9707 |
| Experiment 2 | 100 | 20 | 1 | sqrt | 0.9788 |
| Experiment 3 | 150 | 20 | 1 | sqrt | 0.9790 |
| Experiment 4 | 150 | 25 | 2 | sqrt | 0.9780 |

### Best Configuration

The best validation configuration was:

```text
n_estimators = 150
max_depth = 20
min_samples_split = 2
min_samples_leaf = 1
max_features = sqrt
