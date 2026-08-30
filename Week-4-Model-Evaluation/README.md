# Week 4 – Model Evaluation and Validation

## Overview

Week 4 focuses on evaluating and validating the Random Forest model developed for the Machine Learning-Based Network Intrusion Detection System using the UNSW-NB15 dataset.

The main objective of this week is to measure model performance, check its generalization ability, identify prediction errors, and validate the stability of the model using appropriate evaluation and validation techniques.

## Objectives

- Evaluate the trained Random Forest classification model.
- Calculate Accuracy, Precision, Recall, and F1-Score.
- Generate and analyze the confusion matrix.
- Identify False Positives and False Negatives.
- Calculate False Positive Rate and False Negative Rate.
- Evaluate the model using ROC-AUC.
- Perform 5-Fold Stratified Cross-Validation.
- Check for possible overfitting.
- Compare Week 3 and Week 4 model performance.
- Analyze the overall reliability and stability of the model.

## Dataset

The project uses the UNSW-NB15 dataset.

For this evaluation, the `UNSW_NB15_testing-set.csv` dataset was used.

### Dataset Details

- Total records: 82,332
- Total columns: 45
- Training records: 65,865
- Testing records: 16,467
- Numerical features: 39
- Categorical features: 3
- Categorical features: `proto`, `service`, `state`

The `id` column was excluded because it is a unique identifier.

The `attack_cat` column was excluded from binary classification to prevent target leakage.

## Model

The model evaluated during Week 4 is:

**Random Forest Classifier**

The model classifies network traffic into two classes:

- Normal
- Attack

## Evaluation Metrics

The following metrics were used:

### Accuracy

Measures the overall percentage of correctly classified records.

### Precision

Measures how many records predicted as attacks were actually attacks.

### Recall

Measures how many actual attacks were correctly detected.

### F1-Score

Provides a balanced measure between Precision and Recall.

### ROC-AUC

Measures the model's ability to distinguish between Normal and Attack traffic across different classification thresholds.

## Test Set Results

| Metric | Score |
|---|---:|
| Accuracy | 97.63% |
| Precision | 98.44% |
| Recall | 97.24% |
| F1-Score | 97.84% |
| ROC-AUC | 99.71% |

## Confusion Matrix

The confusion matrix produced the following results:

| | Predicted Normal | Predicted Attack |
|---|---:|---:|
| Actual Normal | 7,260 | 140 |
| Actual Attack | 250 | 8,817 |

### Error Analysis

- True Negatives: 7,260
- False Positives: 140
- False Negatives: 250
- True Positives: 8,817
- False Positive Rate: 1.89%
- False Negative Rate: 2.76%

False negatives are particularly important in intrusion detection because they represent malicious traffic that was incorrectly classified as normal.

## 5-Fold Stratified Cross-Validation

Five-fold stratified cross-validation was performed to evaluate model stability.

### Fold F1-Scores

- Fold 1: 0.9783
- Fold 2: 0.9791
- Fold 3: 0.9789
- Fold 4: 0.9801
- Fold 5: 0.9803

### Cross-Validation Results

| Metric | Mean Score |
|---|---:|
| Accuracy | 97.74% |
| Precision | 98.41% |
| Recall | 97.47% |
| F1-Score | 97.93% |
| F1 Standard Deviation | 0.07% |

The low F1-score standard deviation indicates that the model produced consistent results across the five validation folds.

## Overfitting Analysis

The model achieved:

- Training Accuracy: 100.00%
- Testing Accuracy: 97.63%
- Accuracy Difference: 2.36 percentage points

The difference between training and testing accuracy indicates some degree of overfitting. However, the high testing performance and stable cross-validation results indicate that the model still generalizes well to unseen data.

Further optimization will be considered in Week 5.

## Week 3 vs Week 4 Comparison

| Metric | Week 3 | Week 4 |
|---|---:|---:|
| Accuracy | 97.69% | 97.63% |
| Precision | 98.40% | 98.44% |
| Recall | 97.39% | 97.24% |
| F1-Score | 97.89% | 97.84% |

The Week 3 and Week 4 results are very similar, showing that the model maintains consistent performance during evaluation.

## Work Completed

The following Week 4 tasks were completed:

- Model evaluation on the test dataset
- Accuracy calculation
- Precision calculation
- Recall calculation
- F1-Score calculation
- Confusion matrix generation
- False Positive analysis
- False Negative analysis
- ROC-AUC evaluation
- ROC curve analysis
- Precision-Recall analysis
- 5-Fold Stratified Cross-Validation
- Overfitting analysis
- Week 3 vs Week 4 comparison
- Final evaluation summary

## Conclusion

The Week 4 evaluation demonstrates that the Random Forest model performs strongly on the UNSW-NB15 network intrusion detection task.

The model achieved 97.63% accuracy, 98.44% precision, 97.24% recall, 97.84% F1-Score, and 99.71% ROC-AUC on the test dataset.

Five-fold stratified cross-validation produced a mean F1-Score of 97.93% with a standard deviation of only 0.07%, indicating stable performance across different validation folds.

The evaluation also identified a 2.36 percentage-point difference between training and testing accuracy, suggesting some overfitting. This will be investigated further during the Week 5 model optimization stage.

## Week 4 Status

**Completed**

## Next Step

**Week 5 – Model Optimization**
