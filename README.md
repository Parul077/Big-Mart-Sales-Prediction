# 🏪 Big Mart Sales Prediction

## 📌 Project Overview
The objective of this project is to predict **item outlet sales** for Big Mart stores based on product-level attributes and outlet-level characteristics.  
Beyond prediction, the project emphasizes **model selection, bias–variance trade-offs, and generalization performance** on noisy real-world retail data.

---

## 🎯 Problem Statement
Retail sales are influenced by multiple interacting factors such as:
- Product type and visibility
- Pricing (MRP)
- Outlet location, size, type, and age

The goal is not only to predict sales accurately, but to understand:
- Where linear models fail
- How non-linear models improve learning
- Why ensemble methods generalize better on real retail datasets

---

## 🧠 Problem Type
- **Machine Learning Task:** Regression  
- **Target Variable:** `Item_Outlet_Sales`  
- **Dataset Size:** ~8,500 records  
- **Data Nature:** Noisy, real-world retail data  

---

## 🧩 Dataset Description
The dataset contains information about:
- **Items:** weight, visibility, MRP, category
- **Outlets:** size, type, location, establishment year

Each record represents sales of a specific item in a specific outlet.

---

## ⚙️ Project Workflow
1. Problem understanding & ML task identification  
2. Baseline model development  
3. Feature engineering & preprocessing  
4. Model training and comparison  
5. Bias–variance analysis  
6. Final model selection  
7. Error and limitation analysis  

---

## 🚦 Baseline Model
A **Linear Regression** model was used as the baseline to:
- Establish a minimum performance benchmark
- Test whether linear assumptions are sufficient

### Observation
- Train R² ≈ 0.51  
- Test R² ≈ 0.49  
- High prediction error (RMSE ≈ 1256)

### Inference
Linear models are unable to fully capture the complex, non-linear interactions present in retail sales data, motivating the use of non-linear and ensemble models.

---

## 🛠 Feature Engineering
The following feature enhancements were applied:
- Outlet age derived from establishment year
- Correction of zero visibility values
- Encoding of categorical variables
- Careful preprocessing to prevent data leakage

### Key Insight
Feature engineering provided noticeable improvements, demonstrating that **data quality and representation significantly influence model performance**, often more than algorithm complexity alone.

---

## 🤖 Models Evaluated
The following regression models were trained and evaluated using the same pipeline:

- Linear Regression  
- Ridge Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- XGBoost Regressor  

---

## 📊 Model Performance Comparison

| Model              | Train R² | Test R² | RMSE ↓ |
|--------------------|----------|---------|--------|
| Linear Regression  | 0.507    | 0.489   | 1255.82 |
| Ridge Regression   | 0.507    | 0.489   | 1255.93 |
| Decision Tree      | 0.700    | 0.501   | 1241.62 |
| Random Forest      | 0.874    | 0.563   | 1161.21 |
| XGBoost            | 0.876    | 0.502   | 1240.25 |

📌 Lower RMSE indicates better predictive accuracy.

---

## 🧪 Bias–Variance Analysis
- **Linear & Ridge Regression:** High bias, underfitting complex sales patterns
- **Decision Tree:** High variance, strong training fit but weaker test generalization
- **Random Forest:** Best bias–variance balance through ensemble averaging
- **XGBoost:** High learning capacity but limited generalization without extensive tuning

This analysis highlights that **higher model complexity does not guarantee better real-world performance**.

---

## ✅ Final Model Selection
**Random Forest Regressor** was selected as the final model due to:
- Highest Test R² score
- Lowest RMSE among all evaluated models
- Strong generalization performance
- Robust handling of noisy tabular retail data

Although XGBoost achieved similar training performance, it showed inferior generalization compared to Random Forest in this setting.

---

## 📉 Error & Limitation Analysis
The model showed higher prediction errors for:
- Newly established outlets
- Rare or low-frequency item categories

**Reason:**  
Limited historical patterns for these cases indicate **data constraints rather than model weaknesses**.

---

## 🧾 Results Summary
- Final Test R² ≈ **0.56**
- RMSE reduced by ~7–8% compared to linear baseline
- Reliable predictions for most item–outlet combinations

---

## 💼 Business Impact
The model can assist retailers in:
- Forecasting item-level demand
- Improving outlet-wise inventory planning
- Understanding how outlet characteristics influence sales performance

Approximately 56% of sales variance is explained by the model, with remaining variance likely driven by external factors such as promotions, seasonality, and customer behavior not present in the dataset.

---

## 📚 Key Learnings
- Always establish a baseline before using complex models
- Linear models are insufficient for real-world retail sales prediction
- Ensemble methods outperform single models on noisy data
- Better generalization matters more than higher training accuracy
- Understanding *why* a model works is more valuable than chasing metrics

---

## 🚀 Future Improvements
- Hyperparameter tuning with cross-validation
- Advanced feature engineering
- Incorporation of seasonal and promotional data
- Deployment as a REST API or dashboard

---

## 🧑‍💻 Author
**Parul Singh**  
Machine Learning & Software Development Enthusiast

