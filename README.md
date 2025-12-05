# 🏠 Real Estate Price Analysis & Prediction in Egypt (Dubizzle Properties)

## 🌟 Project Overview

This project aims to build a high-accuracy **Machine Learning model** to predict residential property prices in the Egyptian market, using data collected from real-estate listing platforms.

* **Main Objective:** Identify the key factors influencing property prices and build a reliable **Regression model**.  
* **Languages & Tools:** Python (Pandas, NumPy, Matplotlib/Seaborn, Scikit-learn, XGBoost).  
* **Current Model Status:** Achieved **moderate accuracy** (**R² ≈ 0.51** after feature engineering), indicating that the most critical improvements depend on **increasing dataset size** and **adding missing features**.

---

## 💾 Dataset and Features

The dataset was collected from real-estate listings and contains **4,500 rows** (before cleaning).

| Feature (English) | Description | Example |
|-------------------|-------------|---------|
| `price` | Property price (the **target** variable) | 4,492,000 EGP |
| `area` | Property area (m²) | 151 m² |
| `beds` | Number of bedrooms | 3 |
| `baths` | Number of bathrooms | 3 |
| `compound` / `location` | Compound or neighborhood name | First Settlement / Diar1 |

---

## 🧹 Data Preprocessing Methodology

Several advanced data cleaning and feature engineering steps were applied to improve model stability:

1. **Initial Cleaning:** Removed symbols, normalized values, and converted numeric columns using `Numeric` types.  
2. **Outlier Removal (IQR):** Applied to all numerical features (`price`, `area`, `baths`, `beds`).  
3. **Advanced Location Encoding (Target Encoding):**  
   * The categorical `compound` feature was replaced with a new numeric feature: **`Compound_Value`**.  
   * This represents the **average property price per compound**, making it the strongest predictor.

---

## 🤖 Modeling and Performance

Three regression models were tested:

| Model | R² Score | Notes |
|-------|----------|-------|
| **Linear Regression** | 0.27 | Weak performance (relationships are not linear). |
| **Random Forest Regression** | **0.51** | Best-performing and most stable. |
| **XGBoost Regressor** | 0.45 | Less stable and requires tuning. |

### Feature Importance Analysis

The model clearly shows the top factors affecting price:

| Feature | Importance | Conclusion |
|---------|------------|------------|
| **`Compound_Value`** | **66.7%** | Strongest driver — location dominates pricing. |
| **`area`** | **24.4%** | Second most important feature. |
| `baths` / `beds` | < 6% | Minor impact. |

---

## 🚀 Future Work (Target: R² > 0.80)

To reach a professional accuracy level:

* **Increase the dataset size:** Expand to **10,000+ rows** for better generalization.  
* **Add missing critical features:** Such as finishing quality, floor number, delivery status (ready / under construction).  
* **Hyperparameter Tuning:** Use advanced techniques such as **Randomized Search** to improve Random Forest performance.

---
