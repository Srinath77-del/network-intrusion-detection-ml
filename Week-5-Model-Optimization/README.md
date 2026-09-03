# Week 5 – Model Optimization

## Objective

The objective of Week 5 is to optimize the Random Forest model developed for the UNSW-NB15 network intrusion detection project. The optimization process focuses on testing different hyperparameter configurations and identifying a configuration that provides strong classification performance while maintaining good generalization.

## Dataset

The UNSW-NB15 testing dataset contains 82,332 records and 45 columns.

For binary classification:

- Input features: 42
- Numerical features: 39
- Categorical features: 3
- Categorical columns: `proto`, `service`, `state`
- Normal traffic: 37,000
- Attack traffic: 45,332

The `id`, `attack_cat`, and `label` columns were excluded from the input features.

## Experimental Setup

The dataset was divided using an 80/20 stratified train-test split.

- Training samples: 65,865
- Testing samples: 16,467

Categorical features were processed using OneHotEncoder, while numerical features were passed through unchanged. The preprocessing and Random Forest classifier were implemented using a scikit-learn Pipeline.

## Baseline Random Forest

The baseline Random Forest used 100 trees.

| Metric | Score |
|---|---:|
| Accuracy | 0.9752 |
| Precision | 0.9830 |
| Recall | 0.9718 |
| F1-Score | 0.9774 |
| ROC-AUC | 0.9971 |

## Optimization Methods

Three common hyperparameter optimization approaches were considered:

### Grid Search

Grid Search evaluates every combination from a predefined parameter grid. It provides systematic coverage but can require a large amount of computation.

### Random Search

Random Search evaluates randomly selected configurations from a defined parameter space. It can explore a wider range of configurations with a fixed computational budget.

### Bayesian Optimization

Bayesian Optimization uses the results of previous experiments to select promising configurations for subsequent trials. It can be useful when model training is computationally expensive.

## Controlled Experiments

Four Random Forest configurations were evaluated using a validation subset.

| Experiment | n_estimators | max_depth | min_samples_split | min_samples_leaf | max_features | Validation F1 |
|---|---:|---:|---:|---:|---|---:|
| Baseline | 100 | Default | 2 | 1 | Default | 0.9774 |
| Experiment 1 | 100 | 15 | 2 | 1 | sqrt | 0.9707 |
| Experiment 2 | 100 | 20 | 2 | 1 | sqrt | 0.9788 |
| Experiment 3 | 150 | 20 | 2 | 1 | sqrt | 0.9790 |
| Experiment 4 | 150 | 25 | 2 | 2 | sqrt | 0.9780 |

## Best Configuration

Experiment 3 achieved the highest validation F1-Score of **0.9790**.

The selected configuration was:

- `n_estimators = 150`
- `max_depth = 20`
- `min_samples_split = 2`
- `min_samples_leaf = 1`
- `max_features = sqrt`

The validation F1-Score improved from the baseline value of 0.9774 to 0.9790.

## Analysis

Experiment 1 produced a lower F1-Score of 0.9707, indicating that restricting the tree depth to 15 was not suitable for this configuration.

Experiment 2 improved the result to 0.9788 by increasing the maximum depth to 20.

Experiment 3 further improved the result to 0.9790 by increasing the number of trees from 100 to 150.

Experiment 4 produced 0.9780. The additional depth and larger minimum leaf size did not provide an improvement over Experiment 3.

These results demonstrate that increasing model complexity does not automatically improve performance. Hyperparameters must be evaluated experimentally.

## Overfitting and Generalization

The final test set was kept separate from hyperparameter selection. The validation subset was used to compare configurations, while the test set was reserved for final evaluation.

This approach helps reduce the risk of selecting a model based on test-set performance and provides a more reliable estimate of generalization.

## Challenges

The main challenge during Week 5 was computational cost. An initial RandomizedSearchCV experiment with 15 candidates and 3-fold cross-validation required 45 model fits and took a long time to execute.

To make the experimentation more practical, four controlled configurations were tested individually using a validation subset.

## Reproducibility

The experiments can be reproduced using:

- Python
- pandas
- scikit-learn
- UNSW-NB15 dataset
- `random_state = 42`

The same preprocessing pipeline, train-test split, feature selection, and hyperparameter configurations should be used to reproduce the reported results.

## Files

- `UNSW_NB15_Week5_Model_Optimization.ipynb` – Week 5 implementation and experiments
- `Srinath_week-05.docx` – Week 5 report

## Status

**Week 5 – Model Optimization: Completed**
