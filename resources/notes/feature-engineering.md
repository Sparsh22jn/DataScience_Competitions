# Notes: Feature Engineering

Cross-competition reference guide for feature engineering techniques.

---

## Encoding Categorical Variables

### Label Encoding
- Converts categories to integers (A=0, B=1, C=2)
- **Use when:** The feature has ordinal meaning (Low < Medium < High)
- **Risk:** Tree models handle it fine; linear models will assume numeric ordering

### One-Hot Encoding
- Creates a binary column per category
- **Use when:** No ordinal relationship exists between categories
- **Risk:** High cardinality features (>20 categories) will explode dimensionality

### Target Encoding
- Replaces each category with the mean of the target for that category
- **Use when:** High-cardinality categoricals (e.g. zip codes, user IDs)
- **LEAKAGE RISK:** Must be computed inside cross-validation folds only

---

## Handling Missing Data

| Strategy | When to use |
|---|---|
| Median imputation | Skewed numerical features |
| Mean imputation | Normally distributed numerical features |
| Mode imputation | Categorical features with few nulls |
| Flag + impute | When missingness itself is informative (add `is_missing` column) |
| Drop column | When >70% missing and no domain value |
| Model-based (KNN, iterative) | When missingness pattern is complex |

---

## Date/Time Features

Extract from a datetime column:
- Year, month, day of week, hour
- Is weekend, is holiday
- Days since [reference event]

---

## Interaction Features

Multiply or combine two features when domain suggests they interact:
```python
df['Fare_per_person'] = df['Fare'] / df['FamilySize']
```

Always ask: *would a domain expert say these interact?* Don't combine blindly.
