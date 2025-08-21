# Home Credit Default Risk – Exploratory Data Analysis (EDA)

## 📌 Introduction
This project analyzes the **Home Credit Default Risk dataset** with the goal of understanding which customer attributes and financial behaviors are linked to higher loan default risk.  

The dataset includes **demographics, employment, housing, financial information, and external risk scores** for over 300,000 loan applicants.  

Through this exploratory analysis, we:
- Cleaned and pre-processed the dataset  
- Performed **feature selection** to retain important variables  
- Explored the data using **univariate, bivariate, multivariate, stratified, and target-focused analyses**  
- Conducted **correlation analysis** to understand feature relationships  
- Investigated **outliers** and their impact on default risk  

---

## 1. Data Cleaning & Preparation
- Selected relevant **20+ features** (demographics, income, credit, annuities, ratios, housing, occupation, external scores).  
- Created useful **financial ratios**:  
  - `CREDIT_INCOME_RATIO = AMT_CREDIT / AMT_INCOME_TOTAL`  
  - `ANNUITY_INCOME_RATIO = AMT_ANNUITY / AMT_INCOME_TOTAL`  
  - `CREDIT_GOODS_RATIO = AMT_CREDIT / AMT_GOODS_PRICE`  
- Handled missing values and ensured consistent feature naming.  

📊 *Prepared `eda` dataset for structured analysis.*  

---

## 2. Feature Selection
- Checked **correlations with TARGET**.  
- Identified top predictors: `EXT_SOURCE_2`, `EXT_SOURCE_3`, `DAYS_BIRTH (AGE)`, `AMT_CREDIT`, `AMT_ANNUITY`, `CREDIT_INCOME_RATIO`, `CREDIT_GOODS_RATIO`.  
- Ratios and external risk scores showed strong predictive power.  

📊 *Confirmed that derived ratios and external scores are highly valuable for modeling risk.*  

---

## 3. Univariate Analysis
Explored **individual feature distributions** (continuous & categorical).  

- **Age Distribution**: Most applicants are 30–50 years.  
- **Income & Credit Amounts**: Right-skewed, with few extremely high values.  
- **Housing Types**: Majority live in apartments/houses; few in municipal housing.  
- **Occupation Types**: Laborers & core staff are the largest segments.  

📊 *Identified skewed distributions & presence of outliers across financial variables.*  

---

## 4. Bivariate Analysis
Examined how **two variables interact**, often with **TARGET as hue**.  

- **Housing Type vs Default**: Rented apartments & living with parents have higher default rates.  
- **Organization Type vs Default**: Self-employed & business entities riskier than government/medicine/schools.  
- **Income vs Credit**: Larger credit amounts usually tied to higher income, but ratios differentiate risky borrowers.  

📊 *Showed socio-economic factors (housing, job type) significantly impact default risk.*  

---

## 5. Correlation Analysis
Explored **relationships between all features** (not just with target).  

- Strong positive correlation between `AMT_CREDIT`, `AMT_ANNUITY`, and `AMT_GOODS_PRICE`.  
- Age (`DAYS_BIRTH`) negatively correlated with default → older clients default less.  
- External risk scores (`EXT_SOURCE_2`, `EXT_SOURCE_3`) negatively correlated with default → higher scores = safer clients.  
- Ratios (`CREDIT_INCOME_RATIO`, `CREDIT_GOODS_RATIO`) highlight risky borrowers better than raw amounts.  

📊 *Clustered heatmap revealed meaningful feature groupings for risk modeling.*  

---

## 6. Multivariate Analysis
Studied **multiple variables together**.  

- **3D scatterplots** (e.g., Credit vs Income vs Default) highlighted clusters of risky clients.  
- **Boxplots with hue** (e.g., `AGE_BIN vs CREDIT_INCOME_RATIO` colored by TARGET) showed compounding effects of multiple attributes.  

📊 *Certain combinations (young + high credit/income ratio) signal particularly high risk.*  

---

## 7. Stratified Analysis
Grouped default rates across **multiple categorical dimensions**:  

- **Age × Housing**: Younger renters default the most, older homeowners default the least.  
- **Age × Occupation**: Young laborers & service workers are highest risk.  
- **Age × Education**: Low education + young age strongly linked to higher defaults.  
- **Age × Family Status**: Young singles/civil marriages riskier than older married/widows.  

📊 *Age stratification consistently shows risk decreases with maturity across housing, job, education, and family status.*  

---

## 8. Target-Focused Analysis
Direct focus on **default vs non-default groups**.  

- **Gender**: Men default more (10%) vs women (7%).  
- **Income Type**: Unemployed & maternity leave → extremely high default rates (>35%).  
- **Family Status**: Married/widows safer; singles/civil marriage riskier.  
- **Occupation**: Low-skill laborers, drivers, waiters most risky.  
- **Age**: Clear negative trend — younger = higher default.  
- **Credit Amount**: Medium loans riskier; very high loans safer (banks selective).  
- **Ratios**: Credit/Income ratio shows non-linear risk (peaks at mid levels).  
- **External Risk Scores**: Strong monotonic decline in default rates across deciles (higher scores = safer).  

📊 *Default risk aligns strongly with demographics, employment type, and derived ratios.*  

---

## 9. Outlier Analysis
Analyzed extreme values in financial variables.  

- **Income / Credit / Annuity** outliers → **lower default rates** (wealthy clients, selective approvals).  
- **CREDIT_INCOME_RATIO** outliers → **higher risk** (excessive borrowing vs income).  
- **ANNUITY_INCOME_RATIO** outliers → similar risk to average.  
- **CREDIT_GOODS_RATIO** outliers → **much higher default risk** (possible fraud/irregular applications).  

📊 *Outliers reveal hidden safe vs risky borrower groups. Ratios provide stronger red flags than absolute financial values.*  

---

## 📌 Conclusion & Next Steps
- **Key Drivers of Default**:  
  - Demographics: Younger, male, single, low education.  
  - Employment: Unemployed, self-employed, low-skill occupations.  
  - Housing: Renters riskier than homeowners.  
  - Ratios: High credit/income and credit/goods ratios increase risk.  
  - External Scores: Strong predictors of default probability.  

- **Recommendations**:  
  - Use derived ratios + external scores for risk scoring models.  
  - Treat socio-demographic segments differently in credit policy.  
  - Flag extreme ratio outliers as high-risk applicants.  

📊 This EDA lays the foundation for **predictive modeling (logistic regression, tree-based methods, ensemble models)** to better classify default vs non-default clients.

---

