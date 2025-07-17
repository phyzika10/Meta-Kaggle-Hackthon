
# 📊 Kaggle Notebook Popularity Predictor

Predict the **popularity and leaderboard score** of Kaggle notebooks using metadata from the [Meta-Kaggle dataset](https://www.kaggle.com/datasets/kaggle/meta-kaggle). This project was developed for the **Meta-Kaggle Hackathon 2025**.

![notebooks](https://img.shields.io/badge/Meta--Kaggle--2025-Project-blue.svg)
![Python](https://img.shields.io/badge/Language-Python-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

---

## 📁 Project Structure

```
📦 Kaggle-Notebook-Popularity
│
├── notebook_popularity_analysis.ipynb  # Full modeling pipeline
├── notebook_predictions_production.csv # Exported predictions
├── README.md                           # Project overview
├── LICENSE                             # License file
```

---

## 🚀 Objective

Build a **regression model** to predict how popular a Kaggle notebook will become, using engineered features like:

- Author’s performance tier
- Time and date of publication
- Weekend vs weekday publishing
- Leaderboard scores of associated submissions (when available)

---

## 🔧 Features Used

- **TenureDays**: Days between author registration and notebook creation  
- **PerformanceTier**: User's Kaggle tier  
- **CreationHour**: Hour of day the notebook was published  
- **WeekendCreation**: Was the notebook published on a weekend?  
- **HighPerformer / EliteUser**: Based on user tier  
- **PeakHour**: Whether it was posted during high engagement hours  
- **LeaderboardScore (Log-transformed)**: Used as target variable  

---

## 🔍 Workflow

1. **Data Loading** from Meta-Kaggle CSVs  
2. **Feature Engineering** with temporal and user metrics  
3. **Regression Models**:
   - LightGBM  
   - RandomForest  
   - Ridge  
   - GradientBoosting  

4. **Ensemble Averaging**
5. **Model Evaluation** using RMSE, MAE, R²  
6. **Explainability** using SHAP values  
7. **Leaderboard Rank Simulation**  
8. **Predictions Saved to CSV**

---

## 📊 Results

| Metric        | Value   |
|---------------|---------|
| RMSE (val)    | ~0.42   |
| MAE (val)     | ~0.31   |
| R² (val)      | ~0.79   |

- Ensemble predictions improved stability.
- SHAP plots provided strong model explainability.
- Simulated ranks helped visualize competitive potential.

---

## 📦 Requirements

Install dependencies (for local use):

```bash
pip install pandas numpy seaborn matplotlib scikit-learn lightgbm shap
```

This project was run in a **Kaggle kernel environment**.

---

## 📁 Dataset

- Source: [Meta-Kaggle](https://www.kaggle.com/datasets/kaggle/meta-kaggle)
- Required files:
  - `Kernels.csv`
  - `KernelVersions.csv`
  - `KernelTags.csv`
  - `Users.csv`
  - `Competitions.csv`
  - `Submissions.csv`

---

## 🤝 Acknowledgments

Built as part of the **Meta-Kaggle Hackathon 2025** by **Mohamed Zakaria**.

Thanks to the Kaggle community and the maintainers of the Meta-Kaggle dataset.

---

## 📃 License

This project is licensed under the MIT License.
