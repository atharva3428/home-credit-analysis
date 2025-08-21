# 🏦 Home Credit Default Risk – EDA Project

## 📌 Overview
This project explores the **Home Credit Default Risk dataset** to understand factors that drive loan defaults.  
The analysis focuses on **demographics, employment, housing, financial indicators, derived ratios, and external risk scores**.

Through **exploratory data analysis (EDA)**, we uncover key insights about default patterns and lay the foundation for predictive modeling.

---

## 🔑 Key Steps in the Analysis
1. **Data Cleaning & Preparation**  
   - Selected ~20 relevant features  
   - Created derived ratios (`CREDIT_INCOME_RATIO`, `ANNUITY_INCOME_RATIO`, `CREDIT_GOODS_RATIO`)  
   - Handled missing values  

2. **Feature Selection**  
   - Identified important predictors (external scores, ratios, credit amounts, age)  

3. **Univariate & Bivariate Analysis**  
   - Explored distributions of financial/demographic variables  
   - Compared default vs non-default groups  

4. **Correlation Analysis**  
   - Detected multicollinearity among credit/annuity/goods price  
   - Strong predictive power in external risk scores  

5. **Stratified Analysis**  
   - Combined age with housing, occupation, education, family status → clear risk patterns  

6. **Target-Focused Analysis**  
   - Direct comparison of default rates across categories (gender, income type, family, occupation, ratios, risk scores)  

7. **Outlier Analysis**  
   - Found wealthy outliers tend to be safe  
   - Extreme credit/income ratios flag high-risk applicants  

---

## 📊 Key Insights
- **Younger, male, single, low-education applicants** have higher default rates.  
- **Unemployed, self-employed, and low-skill occupations** are high-risk groups.  
- **Renters** are riskier than homeowners.  
- **External risk scores** are among the strongest predictors.  
- **Derived ratios** (credit-to-income, credit-to-goods) highlight risky borrowers better than raw amounts.  
- Outliers reveal both **very safe (wealthy)** and **very risky (over-leveraged)** groups.  

---

