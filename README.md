# Sparsh Jain — Kaggle Portfolio

> A documented journey through Kaggle competitions — every decision recorded, every lesson captured.

This repo is not just about scores. It's about showing **how I think** through data problems: the hypotheses I form, the tools I choose, why I guided the model the way I did, and what I learned from each mistake.

---

## Competition Log

| Competition | Type | Metric | CV Score | LB Score | Rank | Status |
|---|---|---|---|---|---|---|
| [Titanic - ML from Disaster](competitions/titanic/) | Binary Classification | Accuracy | — | — | — | 🔄 In Progress |

> CV = Cross-validation score on training data. LB = Leaderboard score after submission.

---

## Repository Structure

```
SparshJain_Kaggle/
│
├── README.md                        ← You are here — portfolio hub
├── SETUP.md                         ← How to connect Kaggle API + GitHub sync
├── requirements.txt                 ← Common packages across all competitions
│
├── .github/
│   └── copilot-instructions.md      ← How I use GitHub Copilot as a pair-programmer
│
├── templates/
│   ├── COMPETITION_README.md        ← Template: copy this when starting a new competition
│   ├── approach.md                  ← Template: document Copilot guidance + decisions
│   └── learnings.md                 ← Template: personal learning log
│
├── competitions/
│   └── <competition-slug>/
│       ├── README.md                ← Problem summary, approach overview, final score
│       ├── approach.md              ← Step-by-step decisions and Copilot prompts used
│       ├── learnings.md             ← What I personally understood from this problem
│       └── notebooks/
│           └── *.ipynb              ← Notebooks synced from Kaggle
│
└── resources/
    └── notes/
        └── *.md                     ← Cross-competition topic notes (e.g. feature engineering)
```

---

## How I Work

Each competition follows a fixed workflow before I write a single line of code:

1. **Understand the problem** — metric, data structure, domain context
2. **EDA** — distributions, nulls, correlations, class balance
3. **Baseline** — simplest possible model to set a benchmark
4. **Feature Engineering** — domain-informed, leakage-checked
5. **Model Selection** — 2–3 algorithms compared via cross-validation
6. **Tuning** — only after selecting the best architecture
7. **Error Analysis** — understand *where* and *why* the model fails
8. **Submission** — reproducible pipeline with fixed seed

The `approach.md` in each competition folder shows exactly how this played out — including wrong turns.

---

## Copilot as a Pair Programmer

I use GitHub Copilot as a teaching partner, not an answer machine. The `.github/copilot-instructions.md` file instructs Copilot to:
- Explain reasoning before writing code
- Surface trade-offs between approaches
- Flag potential data leakage
- Prompt me to document decisions in `approach.md`

This means my notebooks reflect **my understanding**, not just generated code.

---

## Contact

- **Kaggle:** [kaggle.com/your-username](https://kaggle.com/your-username) ← update this
- **LinkedIn:** [linkedin.com/in/your-profile](https://linkedin.com/in/your-profile) ← update this
