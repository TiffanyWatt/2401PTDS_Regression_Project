# 🌍 CO₂, Agriculture & Temperature: Regression Project

![](https://img.shields.io/badge/Python-3776AB.svg?style=for-the-badge&logo=Python&logoColor=white)

<div id="main image" align="center">
  <img src="https://github.com/marcmarais/2401FTDS_Regression_Project/blob/main/agri_image.png" width="450" height="300" alt=""/>
</div>

---

## 📖 1. Project Overview  
This project applies regression analysis to FAO & IPCC data to forecast **Average_Temperature_°C**.  
The study evaluates the relationship between agricultural emissions, land use, and population indicators, with the goal of informing sustainable strategies for stakeholders.

**Objectives**:  
- Clean and prepare agricultural/climate datasets.  
- Explore patterns in emissions and temperature trends.  
- Engineer new features and reduce multicollinearity.  
- Train and compare regression models (Linear, Ridge, Lasso, Random Forest).  
- Provide actionable insights for climate and agricultural policy.  

---

## 📊 2. Dataset  
- **Source**: FAO & IPCC  
- **Rows**: ~7,000 (1990–2020)  
- **Features**: 30+ predictors  
  - Emissions: savanna fires, rice cultivation, fertilizers, packaging, processing, manure, etc.  
  - Land use: forestland, net forest conversion.  
  - Demographics: rural population, urban population, total population split.  
- **Target**: `Average_Temperature_°C` (annual change)  

*Note:* Forestland values may be negative due to carbon sequestration.

---

## ⚙️ 3. Tools & Packages  
- Python 3.11  
- `pandas`, `numpy` – data manipulation  
- `matplotlib`, `seaborn`, `plotly` – EDA and visualisation  
- `scikit-learn` – regression models (Linear, Ridge, Lasso, Random Forest)  
- `statsmodels` – OLS and VIF diagnostics  

---

## 🧹 4. Workflow  
1. **Data Cleaning**  
   - Standardised column names  
   - One-hot encoding (`Area`)  
   - Median imputation (per country, fallback to global median)  
   - Removed redundant features (e.g. gender-split populations)  

2. **EDA**  
   - Summary statistics and distributions  
   - Correlation heatmaps to reveal multicollinearity  
   - Temperature trends (1990–2020)  
   - Regional comparisons (top/bottom countries)  
   - Geographic map (choropleth)  

3. **Feature Engineering**  
   - Log transforms for skewed predictors  
   - Interaction features (e.g. Fertilizer × Precipitation)  
   - Polynomial terms (Year²)  
   - Correlation (>0.9) & VIF (>10) pruning  

4. **Modeling**  
   - **Linear Regression** (baseline)  
   - **Ridge Regression** (regularized)  
   - **Random Forest Regressor** (non-linear benchmark)  
   - **Lasso Regression** (additional regularized baseline)  
   - Metrics: R², RMSE, MAE  
   - Visuals: Actual vs Predicted, Residuals, Feature Importances  

---

## 📈 5. Results Snapshot  

| Model              | R²   | RMSE   | MAE   |
|--------------------|------|--------|-------|
| Linear Regression  | 0.521 | 0.383 | 0.283 |
| Ridge Regression   | 0.521 | 0.383 | 0.283 |
| Random Forest      | 0.641 | 0.332 | 0.242 |
| Lasso Regression   | 0.427 | 0.418 | 0.315 |

**Insights**:  
- Random Forest captured non-linear relationships best.  
- Ridge = Linear → only slight improvement via regularisation.  
- Lasso underperformed due to over-penalisation.  
- Strong predictor groups: emissions, energy use, land management.  

---

## 💻 6. Environment Setup  

```bash
# Create environment
conda create --name climate python=3.11

# Activate environment
conda activate climate

# Install dependencies
pip install -r requirements.txt

```

## 5. Team Members<a class="anchor" id="team-members"></a>

| Name                                                                                        |  Email              
|---------------------------------------------------------------------------------------------|--------------------             
| [Jana Liebenberg-Fouche](https://github.com/Jana-Liebenberg)                                | jliebenberg-fouche@sandtech.com
| [Edmund Dotsey](https://github.com/Edotsey)                                                 | edotsey@sandtech.com
| [Farayi Myambo](https://github.com/Farayi-Explore)                                          | fmyambo@sandtech.com



#### Additional Resources to create a README file:
- [Make a README](https://www.makeareadme.com/)
- [GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)
- [FreeCodeCamp](https://www.freecodecamp.org/news/how-to-write-a-good-readme-file/)
