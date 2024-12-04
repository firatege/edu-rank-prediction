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
    'n_estimators': 1400,
    'min_samples_split': 2,
    'min_samples_leaf': 1,
    'max_features': 'auto',
    'max_depth': 100,
    'bootstrap': True
}
```

## Model Performance
- **Accuracy**: 73.99%

### Classification Report

| Rank Category   | Precision | Recall | F1-Score | Support |
|-----------------|-----------|--------|----------|---------|
| **0-600**       | 0.97      | 0.95   | 0.96     | 130     |
| **1101-1300**   | 0.31      | 0.39   | 0.35     | 28      |
| **1301-1400**   | 0.78      | 0.28   | 0.41     | 25      |
| **1401-1500**   | 0.50      | 0.29   | 0.36     | 14      |
| **1501-1600**   | 0.00      | 0.00   | 0.00     | 21      |
| **1601-1700**   | 0.00      | 0.00   | 0.00     | 25      |
| **1700+**       | 0.61      | 0.95   | 0.75     | 80      |
| **601-1100**    | 0.79      | 0.92   | 0.85     | 96      |

**Overall Accuracy**: 73.99%

- **Macro Average**: Precision = 0.49, Recall = 0.47, F1-Score = 0.46
- **Weighted Average**: Precision = 0.68, Recall = 0.74, F1-Score = 0.69

## Insights
- The model performs exceptionally well for universities ranked **0-600**, with a precision of 0.97 and recall of 0.95.
- The model struggles with rankings in the **1501-1600** and **1601-1700** categories, achieving 0 precision and recall. These categories may require more targeted data or a different model approach for better performance.

---




