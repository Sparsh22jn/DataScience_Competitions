# Titanic — Machine Learning from Disaster

> **Kaggle link:** [kaggle.com/c/titanic](https://www.kaggle.com/c/titanic)
> **Type:** Binary Classification
> **Evaluation metric:** Accuracy (% of passengers correctly predicted)
> **Dates:** Started — | Finalized —

---

## Problem Summary

Predict whether a passenger survived the Titanic sinking based on features like age, sex, ticket class, and cabin. Each row is one passenger. The target is `Survived` (1 = survived, 0 = did not).

This is the canonical beginner competition on Kaggle. The goal here is not to win — it's to build a clean, documented baseline workflow that can be reused on harder problems.

---

## Data Overview

| File | Rows | Columns | Notes |
|---|---|---|---|
| train.csv | 891 | 12 | Includes `Survived` label |
| test.csv | 418 | 11 | No label — this is what we predict |

**Target:** `Survived` — 1 if the passenger survived, 0 if they did not

**Key features:**
- `Pclass` — ticket class (1st/2nd/3rd), proxy for socioeconomic status
- `Sex` — binary, historically one of the strongest predictors
- `Age` — continuous, ~20% missing
- `SibSp` / `Parch` — number of siblings/spouses and parents/children aboard
- `Fare` — ticket price
- `Embarked` — port of embarkation (C, Q, S)

**Missing data:**
- `Age` — ~20% missing in train
- `Cabin` — ~77% missing, likely to drop or extract deck letter only
- `Embarked` — 2 missing values in train

---

## Approach Summary

_See [approach.md](approach.md) for the full decision log._

> Fill this in as you progress through the competition.

---

## Results

| Model | CV Score | LB Score | Notes |
|---|---|---|---|
| Baseline | — | — | — |
| Final model | — | — | — |

---

## Key Learnings

_See [learnings.md](learnings.md) for full personal notes._

> Fill this in after completing the competition.

---

## Files

| File | Description |
|---|---|
| `notebooks/01_eda.ipynb` | Exploratory data analysis |
| `notebooks/02_baseline.ipynb` | Logistic Regression baseline |
| `notebooks/03_feature_engineering.ipynb` | Feature creation |
| `notebooks/04_final_model.ipynb` | Final submission pipeline |
