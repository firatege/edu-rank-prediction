---

# edu-rank-prediction

This project predicts the rankings of universities based on various features.

## Problem Description

- **Rank Categories**:
  - **1-2092**: Total number of universities in the ranking.
  - **1500+**: Universities ranked 1-1500 are categorized as top universities.
  - **1500-**: Universities ranked beyond 1500.

## Model: Random Forest

The Random Forest model was trained with the following hyperparameters:

```python
{
   'n_estimators': 1000,
    'min_samples_split': 4,
    'min_samples_leaf': 2,
    'max_features': 8,
    'max_depth': 100,
    'bootstrap': True,
    'random_state': 42,
    'verbose': 1,
    'class_weight': 'balanced'
}
```

## Model Performance
- **Accuracy**: 72.90%

### Classification Report

 ## Model Performance Metrics

| Rank Category | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 1-300         | 0.96      | 0.94   | 0.95     | 90      |
| 301-400       | 0.84      | 0.90   | 0.87     | 90      |
| 401-700       | 0.74      | 0.66   | 0.69     | 90      |
| 701-900       | 0.64      | 0.68   | 0.66     | 90      |
| 901-1100      | 0.67      | 0.60   | 0.63     | 90      |
| 1101-1200     | 0.75      | 0.84   | 0.79     | 90      |
| 1201-1300     | 0.78      | 0.62   | 0.69     | 90      |
| 1301-1400     | 0.69      | 0.71   | 0.70     | 90      |
| 1401-1500     | 0.65      | 0.82   | 0.73     | 90      |
| 1501-1600     | 0.76      | 0.72   | 0.74     | 90      |
| 1601-1700     | 0.70      | 0.68   | 0.69     | 90      |
| 1701-1800     | 0.74      | 0.71   | 0.72     | 90      |
| 1801+         | 0.60      | 0.59   | 0.59     | 90      |

### Overall Performance

| Metric        | Value |
|---------------|-------|
| Accuracy      | 0.73  |
| Macro Avg     | 0.73  |
| Weighted Avg  | 0.73  |


---


## Insights

- **High Precision and Recall in Top Ranks:** The model performs exceptionally well in the **1-300** category, with an F1-score of 0.95. This indicates strong reliability for top-ranking instances.
- **Middle Ranks Performance:** Categories such as **1101-1200** and **1401-1500** show balanced precision and recall, suggesting consistent performance.
- **Lower Ranks (1801+):** Precision and recall drop significantly for lower-ranked categories, with an F1-score of only 0.59. This could indicate difficulty in distinguishing these instances or data imbalance.
- **Macro vs. Weighted Avg:** Similar values for macro and weighted averages show that the dataset is relatively balanced in terms of category distribution.
- **Areas for Improvement:** Focus on enhancing performance in the **401-700** and **1801+** categories by exploring better feature engineering, resampling, or advanced models.




