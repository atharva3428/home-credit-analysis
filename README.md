# Home Credit Default Risk Analysis

## 📝 Project Overview

This project explores the Home Credit Default Risk dataset to identify customer attributes linked to higher loan default risk. As a data analyst, the focus is on exploratory data analysis (EDA), feature engineering, and deriving actionable insights—without building predictive machine learning models.

The dataset contains approximately 300,000 loan applications with a mix of numerical and categorical variables, covering demographics, financial details, and behavioral patterns.

## 📂 Dataset

- **Source**: Home Credit Default Risk (Kaggle)
- **File Used**: `application_train.csv`
- **Rows**: ~307,511
- **Columns**: 100+ raw features (cleaned and reduced to ~20 relevant features)

### Key Columns
- **TARGET**: Loan default indicator (1 = default, 0 = repaid)
- **Demographics**: `DAYS_BIRTH`, `CODE_GENDER`, `NAME_EDUCATION_TYPE`, `NAME_FAMILY_STATUS`
- **Financials**: `AMT_CREDIT`, `AMT_ANNUITY`, `AMT_GOODS_PRICE`, `AMT_INCOME_TOTAL`
- **Employment**: `DAYS_EMPLOYED`, `OCCUPATION_TYPE`, `ORGANIZATION_TYPE`
- **Risk Scores**: `EXT_SOURCE_2`, `EXT_SOURCE_3`
- **Ratios (Engineered)**: `CREDIT_INCOME_RATIO`, `ANNUITY_INCOME_RATIO`, `CREDIT_GOODS_RATIO`

## 🛠️ Data Preparation

- Dropped columns with >50% missing values.
- Imputed missing values with median (numeric) and mode (categorical).
- Converted days into years (`AGE_YEARS`, `YEARS_EMPLOYED`).
- Engineered financial ratios for improved risk profiling.
- Created a reduced EDA DataFrame with ~20 relevant features + ratios.

## 🔍 Exploratory Data Analysis (EDA)

### 1. Univariate Analysis
- Examined distribution of numerical features (income, credit, annuity, age, ratios).
- Visualized categorical distributions (gender, education, family status, housing type, occupation).
- Applied log scales to handle skewed features like income and credit.

### 2. Bivariate Analysis
- Explored relationships of features with `TARGET` (default indicator).
- **Key Findings**:
  - Younger borrowers have higher default rates.
  - Debt-to-Income ratio shows a strong link to default.
  - External credit bureau scores strongly separate defaulters vs. non-defaulters.
- Used barplots, boxplots, and kdeplots with `hue=TARGET`.

### 3. Multivariate Analysis
- Combined multiple features to detect higher-risk cohorts.
- **Examples**:
  - Education × Gender → some groups show elevated risk.
  - Family Status × Income Type → self-employed single applicants show higher default rates.
  - Age × Credit Amount × TARGET → younger borrowers taking large loans are riskier.

### 4. Stratified Analysis
- Compared default rates across subgroups:
  - Gender × Education
  - Occupation × Gender
  - Housing Type × Debt-to-Income bands
- Helped identify who defaults more under what conditions.

### 5. Correlation Analysis
- Used Spearman correlation (better for skewed data).
- Built heatmaps and clustered maps to group related features.
- **Insights**:
  - `AMT_CREDIT`, `AMT_ANNUITY`, `AMT_GOODS_PRICE` are tightly correlated.
  - Ratios (`CREDIT_INCOME_RATIO`, `ANNUITY_INCOME_RATIO`) provide additional independent risk signals.
  - External scores (`EXT_SOURCE_2`, `EXT_SOURCE_3`) correlate moderately with each other and negatively with default.

### 6. Target-Focused Analysis
- Directly compared default rates across groups.
- Default rate by:
  - Categoricals: Occupation, Education, Family, Housing.
  - Numeric bins: Age, Loan amount, Ratios, `EXT_SOURCE` scores.
- **Deciles**: Clear ranking—applicants in bottom deciles of `EXT_SOURCE_2` had ~20% default vs. ~3% in top deciles.

### 7. Outlier / Tail Analysis
- Detected outliers using IQR rule + visualized with boxplots and log histograms.
- **Key Findings**:
  - ~4.5% of applicants have extremely high incomes, but they default less (5.8% vs. 8.2%).
  - Outliers in Debt-to-Income ratio default more often, confirming high financial stress risk.
  - Loan outliers (very large credits) show mixed results.

## 📌 Key Insights

- Younger borrowers and those with shorter employment history are more likely to default.
- Debt-to-Income and Annuity-to-Income ratios are strong predictors of risk—higher ratios = higher default.
- External bureau scores (`EXT_SOURCE_2`, `EXT_SOURCE_3`) are highly protective; low scores = high risk.
- Certain occupations (laborers, drivers) and income types (self-employed) default more frequently.
- Wealthy outliers (very high income) are less risky, while debt-ratio outliers are more risky.

## 🛠️ Tools & Libraries

- **Programming Language**: Python
- **Libraries**:
  - Data Manipulation: `pandas`, `numpy`
  - Visualization: `seaborn`, `matplotlib`
  - Feature Selection: Spearman correlation, Chi-square, LightGBM (for validation)
  - Statistics: Chi-square tests, ANOVA

## 🚀 How to Use

1. Clone the repository: `git clone <repository-url>`
2. Install dependencies: `pip install -r requirements.txt` (create a `requirements.txt` file with necessary packages like `pandas`, `numpy`, `seaborn`, `matplotlib`, `scipy`, `lightgbm`).
3. Run the Jupyter notebook or Python scripts in the repository to reproduce the analysis.

## 📅 Last Updated
August 21, 2025