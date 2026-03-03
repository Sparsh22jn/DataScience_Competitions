# Approach Log — [Competition Name]

> This document records **every key decision** made during this competition — why I chose each approach, what alternatives existed, and what Copilot was instructed to do at each step. This is the most important file in the repo for showing engineering judgment.

---

## Step 1 — Problem Understanding

**Date:** YYYY-MM-DD

**What I understood:**
<!-- What type of ML problem is this? What does success look like? -->

**Evaluation metric:** [metric name]
- Why this metric matters: [brief explanation]
- How it differs from accuracy / MSE: [if relevant]

**Initial hypotheses:**
<!-- What do you expect to matter before looking at any data? Think domain knowledge. -->
1.
2.
3.

---

## Step 2 — EDA

**Date:** YYYY-MM-DD

**Copilot prompt I used:**
```
[paste the exact prompt you gave Copilot, e.g. "Run a full EDA on the Titanic training data. Check for nulls, class balance, distributions, and correlations. Explain what you observe before writing any code."]
```

**Key findings:**
- [Finding 1 — e.g. "Age has 177 missing values (~20%). Will need imputation."]
- [Finding 2 — e.g. "Survival rate is 38% — imbalanced but not severely so."]
- [Finding 3 — e.g. "Pclass and Sex are strongly correlated with survival."]

**Surprises:**
<!-- Anything the EDA revealed that you didn't expect -->

**Decisions made:**
<!-- What will you do as a result of the EDA? -->
- [ ] Handle nulls in: [columns]
- [ ] Encode categoricals: [columns]
- [ ] Drop columns: [columns and why]

---

## Step 3 — Baseline Model

**Date:** YYYY-MM-DD

**Model chosen:** [e.g. Logistic Regression / Random Forest]
**Why this as the baseline:** [e.g. "Simple, interpretable, no tuning required"]

**Copilot prompt I used:**
```
[paste the exact prompt]
```

**Baseline score:** CV = [score] | LB = [score]

**What this tells me:**
<!-- Is this good/bad? What's the ceiling? What's the main source of error? -->

---

## Step 4 — Feature Engineering

**Date:** YYYY-MM-DD

**Features added:**

| Feature | Rationale | Leakage risk? |
|---|---|---|
| [feature name] | [why you created it] | No / Review |

**Copilot prompt I used:**
```
[paste the exact prompt]
```

**Score after feature engineering:** CV = [score] (Δ [+/- change from baseline])

**What worked / what didn't:**

---

## Step 5 — Model Selection

**Date:** YYYY-MM-DD

**Models compared:**

| Model | CV Score | Training time | Notes |
|---|---|---|---|
| [Model 1] | | | |
| [Model 2] | | | |
| [Model 3] | | | |

**Winner:** [model] — because [reason]

---

## Step 6 — Hyperparameter Tuning

**Date:** YYYY-MM-DD

**Tuning method:** [Grid Search / Random Search / Optuna / manual]

**Key parameters tuned:** [list them]

**Score after tuning:** CV = [score] (Δ [+/- change])

---

## Step 7 — Error Analysis

**Date:** YYYY-MM-DD

**Where is the model failing?**
<!-- Look at examples the model got wrong. Is there a pattern? -->

**Hypothesis for failures:**

**Attempted fixes:**

---

## Step 8 — Final Submission

**Date:** YYYY-MM-DD

**Final model config:**
```python
# Paste the final model instantiation here, e.g.
# model = XGBClassifier(n_estimators=300, max_depth=4, learning_rate=0.05, seed=42)
```

**Final CV score:** [score]
**Final LB score:** [score]
**Final rank:** [rank] / [total teams]

**What I would do with more time:**
1.
2.
