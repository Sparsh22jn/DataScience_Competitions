# Approach Log — Titanic

> This document records every key decision made during this competition. See `.github/copilot-instructions.md` for how Copilot was directed at each step.

---

## Step 1 — Problem Understanding

**Date:**

**What I understood:**
This is a binary classification problem. I need to predict `Survived` (0 or 1) for each passenger in the test set. The evaluation metric is raw accuracy — the percentage of predictions that are correct.

**Why accuracy here:**
The class split is roughly 62% didn't survive / 38% survived — moderately imbalanced but not extreme. Accuracy is the competition's official metric so we optimise for it, but we'll also monitor AUC-ROC internally for a fuller picture.

**Initial hypotheses (before looking at data):**
1. Sex will be the most predictive feature — historical accounts confirm women were evacuated first
2. Pclass will matter — 1st class passengers had better access to lifeboats
3. Age may matter — children may have been prioritised
4. Family size could be relevant — very large families may have struggled

---

## Step 2 — EDA

**Date:**

**Copilot prompt I used:**
```
Run a complete EDA on the Titanic training data.
For each column, tell me: the data type, the number and % of missing values, the distribution (histogram for numeric, value counts for categorical), and its preliminary correlation with the Survived target.
Explain what you observe before writing any code. Highlight anything unexpected.
```

**Key findings:**
> Fill in after running EDA notebook

**Surprises:**

**Decisions made:**
- [ ] Impute `Age` with: [median / mean / model-based — decide after EDA]
- [ ] Handle `Cabin`: drop or extract deck letter (A–G)
- [ ] Fill 2 missing `Embarked` with most frequent value (S)
- [ ] Drop `Name`, `Ticket`, `PassengerId` from features

---

## Step 3 — Baseline Model

**Date:**

**Model chosen:** Logistic Regression

**Why this as the baseline:** No tuning required, coefficients are interpretable, fast to train. Gives us a meaningful floor to beat.

**Copilot prompt I used:**
```
Build a baseline Logistic Regression model for the Titanic problem.
- Use only the most obvious features: Sex, Pclass, Age (imputed with median), Embarked
- One-hot encode categorical features
- Use 5-fold stratified cross-validation and report mean accuracy
- Explain what each step does before writing the code
```

**Baseline score:** CV = — | LB = —

---

## Step 4 — Feature Engineering

**Date:**

**Copilot prompt I used:**
```
Suggest domain-driven feature engineering ideas for the Titanic dataset.
For each idea, explain the rationale and whether there is any leakage risk.
Don't write any code yet — I want to review the ideas first.
```

**Features to add:**
| Feature | Rationale | Leakage risk? |
|---|---|---|
| `FamilySize` = SibSp + Parch + 1 | Larger families may have had coordination issues | No |
| `IsAlone` = 1 if FamilySize == 1 | Lone passengers may have different survival patterns | No |
| `Title` extracted from Name | Mr/Mrs/Miss/Master encode age+sex information | No |
| `Deck` extracted from Cabin | Proximity to lifeboats | No — but 77% missing |

---

## Step 5 — Model Selection

**Date:**

**Models to compare:**
- Logistic Regression (baseline)
- Random Forest
- XGBoost

---

## Steps 6–8

> Fill in as you progress.
