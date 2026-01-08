# Debt & Inflation Analysis
### Applied Machine Learning for Macroeconomic Forecasting

## 📌 Problem Statement
Inflation surged globally following COVID-19, alongside record-high public debt. Policymakers and financial institutions continue to debate whether rising debt structurally drives inflation. Traditional econometric models often assume linearity — an assumption increasingly challenged in complex global economies.
This project investigates whether modern machine learning models can better capture the debt–inflation relationship using large-scale cross-country fiscal and inflation data.

## 📊 Data
- **Inflation Dataset**: Annual core inflation measures across ~200 countries (1970–2023)
- **Fiscal Space Dataset**: Government debt sustainability, balance sheet composition, and external/private debt indicators (1990–2023)
- **Final modelling window**: 2000–2023
- **Final dataset size**: ≈4–5K country-year observations

## 🧠 Methodology (End-to-End Pipeline)
### 1. Data Engineering
- Harmonised datasets across countries and years
- Converted all sources to annual frequency
- Reshaped data (wide → long) for scalable modelling
- Handled missing values via mean imputation
- Removed extreme outliers using IQR-based filtering

### 2. Feature Engineering & Selection
- Standardised features using Z-score normalization
- Reduced dimensionality via PCA (95% variance retained)
- Selected economically relevant features using:
- Random Forest feature importance
- Recursive Feature Elimination (RFE)

### 3. Modelling
- Linear Regression (econometric baseline)
- Random Forest Regression (non-linear ML model)
- 5-Fold Cross-Validation to ensure generalisability

### 4. Evaluation Metrics
- MAE, MSE, RMSE
- R² for explanatory power

## 📈 Results
- Model	              MAE	        RMSE	        R²
- Linear Regression	~0.78–0.83	~0.96–1.00	~0.03–0.07
- Random Forest	~0.50–0.58	~0.71–0.78	~0.39–0.49

## Key Insight:
While fiscal indicators alone explain only a limited share of inflation variance, Random Forest models consistently outperform linear econometric baselines, confirming the non-linear nature of macroeconomic relationships.

## 💡 Business & Policy Takeaways
- High public debt does not mechanically translate into inflation
- Linear models underestimate structural complexity
- ML models offer better risk-aware forecasting tools for:
    - Central banks
    - Financial institutions
    - Policy & macro-risk teams

## 🔧 Tools & Stack
Python, Pandas, NumPy, Scikit-learn, PCA, Random Forest, K-Fold CV, Matplotlib, Seaborn, Jupyter

## 🚀 Next Extensions (Production-Ready)
- Hyperparameter tuning (GridSearchCV)
- Time-aware validation
- Additional macro variables (rates, FX, commodities)
- Deployment as a policy-risk dashboard
