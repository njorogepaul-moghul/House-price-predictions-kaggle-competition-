# 🏡 House Price Prediction - Kaggle Competition

## 📌 Project Overview
This project was developed for the Kaggle competition **[House Prices: Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)**.  
The goal was to predict house sale prices based on multiple features describing the properties.

---

## 📊 Dataset
- **Train Data:** 1460 rows × 80+ features  
- **Test Data:** 1459 rows × 80+ features  
- **Target Variable:** `SalePrice`

---

## ⚙️ Models & Evaluation
We trained and compared different models on the dataset:

| Model               | Kaggle Public RMSE Score |
|----------------------|--------------------------|
| Random Forest        | 0.13342                  |
| LightGBM             | 0.12932                  |
| **Tuned LightGBM**   | **0.12796 ✅**           |

➡️ The **tuned LightGBM** model performed best and was used for our final Kaggle submission.  

---

## 🛠️ Feature Engineering
To improve model performance, several preprocessing and feature engineering steps were applied:

- **Handling Missing Values**  
  - Numerical features filled with median values  
  - Categorical features filled with the mode  

- **Encoding Categorical Variables**  
  - Ordinal features (e.g., `ExterQual`, `KitchenQual`, `BsmtQual`) were encoded numerically  
  - One-hot encoding was applied to nominal categorical features  

- **New Features Created**  
  - `TotalSF` = `TotalBsmtSF` + `1stFlrSF` + `2ndFlrSF`  
  - `Age` = `YrSold` - `YearBuilt`  
  - `RemodAge` = `YrSold` - `YearRemodAdd`  
  - `Bathrooms` = `FullBath` + 0.5 × `HalfBath`  
  - `PorchArea` = sum of all porch-related features  
  - `HasGarage` (binary feature)  
  - `HasBasement` (binary feature)  
  - `HasFireplace` (binary feature)  

- **Log Transformation**  
  - Applied log(1+x) transformation to `SalePrice` and skewed numerical features to stabilize variance.  

---

## 🔑 Insights
The most positively correlated features with `SalePrice` were:

| Feature        | Correlation |
|----------------|-------------|
| OverallQual    | 0.790982    |
| GrLivArea      | 0.708624    |
| GarageCars     | 0.640409    |
| GarageArea     | 0.623431    |
| TotalBsmtSF    | 0.613581    |
| 1stFlrSF       | 0.605852    |
| FullBath       | 0.560664    |
| TotRmsAbvGrd   | 0.533723    |
| YearBuilt      | 0.522897    |
| YearRemodAdd   | 0.507100    |

---

---

## ✅ Conclusion
Our project successfully built a predictive model for house prices.  
Among all tested models, the **tuned LightGBM** achieved the best performance with a **Kaggle public RMSE score of 0.12796**, making it our final competition submission.

---

## 🚀 Next Steps
As the next phase of this project, we plan to build an interactive **Streamlit web app** where users can adjust house features (via sliders) and instantly get price predictions using our trained LightGBM model.  

Stay tuned for deployment updates! 🔥
[view app ]


