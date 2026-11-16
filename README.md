# 🧬 Cancer Data Analysis: Global Patient EDA (2015-2024)

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical-013243?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-4C8CBF)
![SciPy](https://img.shields.io/badge/SciPy-Hypothesis%20Testing-8CAAE6?logo=scipy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-Random%20Forest-F7931E?logo=scikitlearn&logoColor=white)
![Dataset](https://img.shields.io/badge/Dataset-Global%20Cancer%20Patients%202015--2024-blue)
![Records](https://img.shields.io/badge/Records-50%2C000-informational)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

An end-to-end **exploratory, statistical, and predictive analysis** of 50,000 global cancer patient records (2015-2024), built with **Python** and **Jupyter Notebook**. It covers the full analyst workflow: data inspection, descriptive analysis, risk factor analysis, hypothesis testing (correlation, Kruskal-Wallis, OLS interaction), Random Forest feature importance, and economic burden analysis across countries and age groups.

The goal is to turn raw health data into evidence-backed insights about what drives cancer severity, survival, and treatment cost, and where disparities exist.

> The full problem statement is available in [`problem_statement.md`](problem_statement.md).

---

## 📌 Table of Contents

- [Dataset](#-dataset)
- [Objectives](#-objectives)
- [Tech Stack](#-tech-stack)
- [Methodology](#-methodology)
- [Key Findings](#-key-findings)
- [Project Structure](#-project-structure)
- [How to Run](#-how-to-run)
- [Limitations](#-limitations)
- [Future Work](#-future-work)
- [Author](#-author)

---

## 📊 Dataset

- **File:** `global_cancer_patients_2015_2024.csv`
- **Size:** 50,000 patient records, 2015-2024
- **Coverage:** 10 countries/regions, 8 cancer types, stages 0-4

| Category | Features |
|---|---|
| Demographics | Age, Gender, Country_Region, Year |
| Risk factors | Genetic_Risk, Smoking, Alcohol_Use, Obesity_Level |
| Environment | Air_Pollution |
| Clinical & economic | Cancer_Type, Cancer_Stage, Treatment_Cost_USD |
| Outcomes | Survival_Years, Target_Severity_Score |

---

## 🎯 Objectives

1. **Exploratory Data Analysis:** distributions, trends, and disparities across countries, age groups, and cancer stages
2. **Inferential & predictive analytics**, answering seven questions:
   - Relationship between risk factors and cancer severity
   - Proportion of early-stage diagnoses by cancer type
   - Key predictors of severity and survival years
   - Economic burden across demographics and countries
   - Whether higher treatment cost is associated with longer survival
   - Whether higher cancer stage leads to higher cost and lower survival
   - Whether genetic risk amplifies the effect of smoking on severity
3. **Insight documentation** linked to real-world implications

---

## 🛠 Tech Stack

- **Language:** Python 3
- **Data handling:** NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn
- **Statistics:** SciPy (`linregress`, `pearsonr`, `spearmanr`, `shapiro`, `kruskal`), Statsmodels (OLS with interaction terms)
- **Machine learning:** Scikit-learn (Random Forest Regressor, GridSearchCV)
- **Environment:** Jupyter Notebook

---

## 🔬 Methodology

1. **Data inspection:** structure, data types, duplicate check
2. **Descriptive analysis:** univariate analysis of age, gender, country, cancer type, stage, and treatment cost using KDE plots, histograms, bar charts, and pie charts
3. **Risk factor analysis:** linear regression of each risk factor against severity score
4. **Early-stage diagnosis analysis:** share of Stage 0-II diagnoses for each cancer type
5. **Predictor identification:** Pearson and Spearman correlations plus Random Forest feature importance for severity and survival
6. **Economic analysis:** average treatment cost by country, age group, and gender (grouped bars and heatmaps)
7. **Hypothesis testing:**
   - Pearson/Spearman correlation: treatment cost vs. survival
   - Shapiro-Wilk normality check, then Kruskal-Wallis: cost and survival across stages
   - OLS with interaction term: Genetic Risk x Smoking on severity

---

## 💡 Key Findings

- **Balanced dataset:** the 10 countries, 8 cancer types, and 5 stages are all represented in close to equal numbers, which makes comparisons fair.
- **Severity drivers:** Smoking (r ≈ 0.48) and Genetic Risk (r ≈ 0.48) show the strongest correlation with severity score, followed by Air Pollution, Alcohol Use, and Obesity. Age shows almost no correlation.
- **Random Forest:** Smoking, Genetic Risk, and Treatment Cost are the top predictors of severity; Age and Gender contribute very little.
- **Early-stage diagnosis:** rates are fairly uniform across cancer types (about 38-41%), with Liver highest and Lung lowest.
- **Survival years:** none of the features show a meaningful relationship with survival, and the Random Forest model has near-zero predictive power (test R² ≈ 0).
- **Treatment cost vs. survival:** no significant correlation.
- **Cancer stage:** Kruskal-Wallis tests show no significant difference in treatment cost (p ≈ 0.43) or survival years (p ≈ 0.60) across stages.
- **Genetic Risk x Smoking:** the interaction effect is not statistically significant (p ≈ 0.63), so the two factors act independently.
- **Economic burden:** average treatment costs vary by country and tend to be higher for older age groups, while differences between genders are minimal.

---

## 📁 Project Structure

```
cancer-data-analysis-eda
   ├── cancer-data-analysis.ipynb          # Main analysis notebook
   ├── global_cancer_patients_2015_2024.csv # Dataset
   ├── problem_statement.md                # Project vision and objectives
   └── README.md
```

---

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/sharif-abusad/cancer-data-analysis-eda.git
cd cancer-data-analysis-eda

# 2. Install dependencies
pip install numpy pandas matplotlib seaborn scipy statsmodels scikit-learn jupyter

# 3. Launch the notebook
jupyter notebook cancer-data-analysis.ipynb
```

---

## ⚠️ Limitations

- Several variables (risk scores, severity, survival, cost) appear to be uniformly distributed with near-zero correlation to outcomes like survival, which suggests the data may be **synthetic**. Findings should be treated as an analytical exercise, not as clinical evidence.
- Correlation does not imply causation.
- Risk-factor scores are on a standardized scale rather than real-world measurements.

---

## 🚀 Future Work

- Add gradient boosting models (XGBoost/LightGBM) and compare against Random Forest
- Use SHAP for model explainability
- Build an interactive dashboard (Streamlit, Power BI, or Tableau)
- Validate the analysis on real-world cancer registry data

---

## 👤 Author

<div align="center">

**Sharif Abusad**

[![GitHub](https://img.shields.io/badge/GitHub-Sharif--Abusad-181717?style=for-the-badge&logo=github)](https://github.com/Sharif-Abusad)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sharif--Abusad-0A66C2?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/sharif-abusad)

*If you found this project useful, consider giving it a ⭐ on GitHub — it helps a lot!*

</div>
