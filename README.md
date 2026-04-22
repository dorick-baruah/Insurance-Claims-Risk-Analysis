# Insurance Claims Risk Analysis
### Identifying High-Cost Policyholder Segments & Underwriting Insights

---

## Business Problem

An insurance firm wants to understand what drives high claims costs 
across its portfolio. Identifying high-risk customer segments early 
allows underwriters to price policies more accurately and design 
targeted risk mitigation strategies.

This project answers three questions a risk team actually asks:
- Which policyholders are driving disproportionate claims costs?
- Which risk factors matter most — and by how much?
- What should underwriting do differently as a result?

---

## Key Findings

| Finding | Result |
|---|---|
| Portfolio mean annual claim | ~$13,270 |
| High-cost threshold (90th percentile) | ~$34,000 |
| Smokers vs non-smokers mean claim | 3–4x higher |
| Obese smoker vs healthy non-smoker | 5–6x higher |
| Linear Regression R² | 0.80+ |
| Gradient Boosting R² | 0.88–0.91 |

**The single most important finding:** Smoker status is not a 
pricing add-on — it is a segmentation boundary. Smokers and 
non-smokers form structurally distinct cost cohorts with 
non-overlapping distributions. Models that treat smoking as 
a continuous variable will systematically underprice tail risk.

---

## Recommendations to Underwriting

1. **Separate underwriting tracks** — smokers and non-smokers 
   should be priced on distinct base rate schedules, not a 
   unified table with a loading factor
2. **Mandatory individual review** for any applicant who is 
   both a smoker and has BMI ≥ 30 — automated pricing will 
   underprice this cohort by a significant margin
3. **Per-year age loading above 45** — current 5-year band 
   practice blunts the pricing signal in the highest-cost age group
4. **High-cost watch list** — top 10% of policyholders account 
   for a disproportionate share of total claims; proactive renewal 
   review is more effective than reactive claims management

---

## Project Structure

insurance-claims-risk-analysis/
│
├── notebooks/
│   └── analysis.ipynb          ← complete analysis containing 5 sections
├── outputs/
│   └── *.png                   ← All charts and visualisations
├── data/
│   └── source_link.txt         ← Dataset source (Kaggle)
└── report/
└── business_summary.pdf    ← 2-page non-technical summary

---

## Methodology

Data Understanding → Claims Distribution → Risk Driver Analysis → Customer Segmentation (K-Means, k=4) → Regression Modelling

| Section | Business Question |
|---|---|
| 1. Data Understanding | What does our portfolio look like? |
| 2. Claims Distribution | What is a typical vs high-cost claim? |
| 3. Risk Driver Analysis | Which factors drive high claims costs? |
| 4. Customer Segmentation | What distinct risk profiles exist? |
| 5. Regression + Recommendations | How much does each factor cost — and what do we do about it? |

---

## Tools

Python 3 · Pandas · NumPy · Scikit-learn · Matplotlib · Seaborn

---

## Dataset

Medical Cost Personal Dataset — [Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance)  
1,338 policyholders · 7 variables · No missing values

---

*Analysis by Dorick Baruah*  
*MBA - Business Management XIMB · B.Sc. Statistics, Cotton University*  
*[LinkedIn](https://linkedin.com/in/dorick-baruah)*