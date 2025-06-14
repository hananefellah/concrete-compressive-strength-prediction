# 🏗️ concrete-compressive-strength-prediction
Predict concrete compressive strength from mix design using ML

Predicts the compressive strength (MPa) of new concrete mixes using machine learning.

## 📂 Files & Their Purpose
| File | Description |
|------|-------------|
| `concrete_strength.ipynb` | Main Jupyter notebook with EDA, model training, and predictions |
| `Concrete_Data.xlsx` | Original dataset (mix designs + measured strengths) |
| `concrete_strength_xgb.pkl` | Trained XGBoost model (save/load with `joblib`) |
| `scaler.pkl` | Feature scaler for preprocessing new data |
| `concrete_strength_pipeline.pkl` | Complete prediction pipeline (model + scaler + config) |

## 🛠️ Tools & Techniques Used

#### **Programming & ML**
- **Python 3** (Core language)
- **Jupyter Notebook** (Interactive analysis)
- **Scikit-learn** (Regression, Random Forest, Gradient Boosting, PCA)
- **XGBoost** (Optimized gradient boosting)
- **Statsmodels** (OLS regression, VIF analysis)
- **Joblib** (Model persistence)

#### **Data Handling**
- **Pandas** 
- **NumPy**
- **ELI5** 

#### **Visualization**
- **Matplotlib/Seaborn**
- **Statsmodels.graphics** 
- **Plotly**

#### **Modeling Techniques**
1. **Regression**

2. **Feature Engineering**

3. **Validation**

#### **Key Findings**
- **Top Predictors**: Age, water-cement ratio, cement  
- **Best Model**: XGBoost (R²=0.934, MAE=2.82 MPa)  
- **Critical Insight**: Strength-age relationship is nonlinear

## 📬 Contact  
Created by FELLAH HANANE
📧 Email: hananefellah35@gmail.com
🌐 GitHub: hananefellah

## 📄 License  
MIT License  

## 🛠️ How to Use
**For new predictions**:

```python
import joblib
pipeline = joblib.load('concrete_strength_pipeline.pkl')  # Load everything
new_mix = {'Cement': 350, 'Water': 180, ...}  # Your values
strength = pipeline['model'].predict([pipeline['scaler'].transform([new_mix])])
