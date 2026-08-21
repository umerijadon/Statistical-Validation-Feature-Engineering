# Statistical-Validation-Feature-Engineering

**AnalystLab Africa Consulting | Data Science Internship Programme**
**Client (fictional): ABC Manufacturing Ltd**

## Project Overview

ABC Manufacturing Ltd is exploring an employee wellness and occupational
health screening initiative. This project uses the IBM/Kaggle Heart
Disease Prediction dataset as a stand-in for real patient data to
validate an analytical approach: can a patient's clinical measurements
flag meaningfully higher risk of heart disease early enough to act on it?

Nothing in this repository should be read as actual medical guidance —
it is a data science internship exercise using a public dataset.

> **Note on project history:** Week 1 of this internship explored a
> different dataset (IBM HR Analytics — employee attrition) for a
> different business question. Week 2's brief allowed a free choice of
> dataset for the feature-engineering exercise, and the heart disease
> dataset was selected instead. Weeks 2–3 (this repository, from Week 2
> onward) continue that wellness-screening thread.

## Week 3: Advanced Analysis, Statistical Validation & Feature Engineering

Week 3 picks up directly from Week 2's cleaned dataset and goes deeper,
without repeating the cleaning work already done:

- **Advanced EDA** — 15 visualisations covering distribution shape, skew,
  bivariate and multivariate relationships, and target-variable analysis.
- **Six statistical hypothesis tests** — Mann-Whitney U, Chi-square, and
  Kruskal-Wallis tests, each with a stated business question, hypotheses,
  test statistic, p-value, and business interpretation. All six came back
  statistically significant.
- **Five engineered features** — three retained (`ChestPainRiskRank`,
  `ExertionRiskFlag`, `BPCategory`), two built, tested, and honestly
  dropped once the evidence showed they added no independent value
  (`HRReserveDeficit`, `CholesterolAgeRatio`).
- **Evidence-based feature evaluation** — correlation screening, Random
  Forest importance ranking, and a data-leakage check, with every
  retain/remove decision documented.
- **Final modelling dataset** — `heart_final_modelling_dataset.csv`,
  ready for Week 4 model development.

### Key Findings

- Chest pain presentation type is the single strongest categorical
  predictor of heart disease found (13.9%–79.0% rate across categories,
  Cramer's V = 0.54).
- Max heart rate and ST depression (Oldpeak) both differ sharply between
  patients with and without heart disease (p < 10⁻³³ for both).
- A combined "double warning sign" of exercise-induced angina + high ST
  depression flags an 89.5% heart disease rate, vs. 40.0% otherwise.
- Re-encoding chest pain type as a single ordinal risk score
  (`ChestPainRiskRank`) outperformed the original one-hot encoding —
  ranking 3rd of 14 candidate features by Random Forest importance.

See `reports/Week3/Business_Insights_and_Recommendations_Report.docx`
for the full write-up.

## Tools & Libraries

Python 3, Jupyter Notebook, pandas, NumPy, Matplotlib, Seaborn,
scikit-learn, SciPy. See `requirements.txt` for pinned versions.

## How to Reproduce

1. Install dependencies: `pip install -r requirements.txt`
2. Open `notebooks/Week3_Statistical_Validation_Feature_Engineering.ipynb`
3. Run all cells — the notebook reads `data/heart_cleaned.csv` (Week 2's
   output) and produces `data/heart_week3_refined.csv` and
   `data/heart_final_modelling_dataset.csv`.

## Author

Data Scientist, AnalystLab Africa Consulting — Data Science
Internship Programme, Week 3.

#AnalystLabAfrica

