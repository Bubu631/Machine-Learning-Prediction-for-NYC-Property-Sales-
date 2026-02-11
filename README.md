# NYC Property Sales — Predicting Real Estate Prices with Machine Learning

This project builds an end-to-end **machine learning pipeline** to analyze and predict **New York City property sale prices** using historical transaction data across all five boroughs.

The workflow covers **data cleaning, feature engineering, exploratory data analysis (EDA), model training, evaluation, and interpretation**, with a focus on understanding what drives real estate prices in NYC.

Dataset source (Kaggle):  
https://www.kaggle.com/datasets/new-york-city/nyc-property-sales

---

## Project Objective

The primary goal of this project is to:

- Develop a **predictive framework** for NYC property sale prices
- Compare a **baseline Linear Regression model** with a **non-linear Random Forest Regressor**
- Evaluate model performance using standard regression metrics
- Identify **key features** that drive property values using feature importance analysis

This project emphasizes **real-world data challenges**, including noisy transactions, skewed price distributions, and heterogeneous property types.

---

## Repository Contents

- `New_York_City_Property_Sales.ipynb`  
  Main notebook containing data preprocessing, modeling, evaluation, and visualization.
- `requirements.txt`  
  Python dependencies required to run the notebook.
- `README.md`  
  Project overview and conclusions.

---

## Technologies & Tools Used

### Programming Language
- **Python 3**

### Core Libraries
- **pandas** – data cleaning and transformation  
- **numpy** – numerical computation  
- **matplotlib / seaborn** – data visualization  
- **scikit-learn** – modeling, preprocessing, and evaluation  

### Machine Learning Techniques
- Linear Regression (baseline model)
- Random Forest Regression (non-linear ensemble model)
- Train / test split
- Feature scaling
- Model evaluation with MAE, RMSE, and R²
- Feature importance extraction

---

## Project Workflow

### 1. Data Preparation & Cleaning
Key steps include:
- Converting numeric and date fields to correct data types
- Removing invalid or non-informative sale prices
- Handling missing values and inconsistent entries
- Encoding categorical variables (e.g., borough, building class)
- Scaling numerical features for regression models

These steps are necessary due to the **highly skewed and noisy nature** of real estate transaction data.

---

### 2. Modeling Approach

Two models were trained and compared:

#### Baseline Model
- **Linear Regression**
- Serves as a simple, interpretable benchmark

#### Advanced Model
- **Random Forest Regressor**
- Captures non-linear relationships and feature interactions

Both models were evaluated on the same held-out test set.

---

## Model Performance Comparison

| Model              | MAE (Mean Absolute Error) | RMSE (Root Mean Squared Error) | R² Score |
|-------------------|---------------------------|--------------------------------|----------|
| Linear Regression | 1,306,329.32              | 6,478,766.37                   | 0.2494   |
| Random Forest     | **744,481.23**            | 7,208,175.18                   | 0.0708   |

<img width="1389" height="590" alt="image" src="https://github.com/user-attachments/assets/f99bb8e0-2d6c-4a95-9ab8-6a340ce7b964" />

### Interpretation
- **Random Forest significantly reduces MAE**, indicating better average prediction accuracy.
- Linear Regression achieves a **higher R²**, suggesting it explains variance better under a linear assumption.
- The divergence between MAE and R² highlights:
  - Extreme price outliers
  - Strong non-linearity
  - Structural heterogeneity in NYC real estate markets

---

## Predictions vs. Actual Prices

Scatter plots comparing predicted vs. actual sale prices show:
- Both models perform reasonably for **lower-priced properties**
- Errors grow substantially for **high-value transactions**
- Random Forest reduces systematic underestimation in some ranges but still struggles with extreme outliers

These results visually confirm the **high volatility and heavy-tailed nature** of NYC property prices.

---

## Feature Importance Analysis (Random Forest)

The Random Forest model provides insight into which variables most strongly influence predictions.

### Top Influential Features
<img width="1278" height="547" alt="image" src="https://github.com/user-attachments/assets/92c84a3d-7bfc-4db2-a9ea-e12f0acd8e9a" />

### Key Insight
Property **size and age** overwhelmingly drive price variation, while **location and usage type** provide important secondary signals.  
This aligns well with real-world real estate valuation principles.

---

## Final Conclusions

- NYC property prices are **highly skewed and volatile**, making prediction challenging.
- Simple linear models capture broad trends but miss complex interactions.
- Ensemble methods like Random Forest:
  - Improve average error (MAE)
  - Reveal meaningful feature importance
  - Still struggle with extreme outliers
- Careful **data cleaning and segmentation** are as important as model choice.

Overall, this project demonstrates that **machine learning can meaningfully improve price prediction accuracy over naive approaches**, while also providing interpretable insights into real estate dynamics.

---

