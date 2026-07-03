# 🤖 Machine Learning Basics

A hands-on collection of end-to-end machine learning projects covering real-world datasets — from raw data exploration to trained, evaluated models.

---

## 📁 Repository Structure

```
Machine_Learning_basics/
│
├── ML_basics_insurance.ipynb     # Insurance EDA & preprocessing (regression)
├── ML_Insurance_updated.ipynb    # Insurance charges prediction w/ Linear Regression
├── insurance.csv                 # Medical insurance dataset (1,338 records)
│
├── ML_basics_heart.ipynb         # Heart disease EDA & preprocessing (classification)
├── ML_heart_disease.ipynb        # Heart disease prediction w/ multiple ML models
├── heart.csv                     # Heart disease dataset
│
├── tittanic_survival.ipynb       # Titanic survival prediction (classification)
│
└── README.md
```

---

## 📓 Projects

### 1. 💰 Insurance Charges Prediction (Regression)

**Notebooks:** `ML_basics_insurance.ipynb`, `ML_Insurance_updated.ipynb`
**Dataset:** `insurance.csv`

Predicts individual medical insurance charges using patient attributes like age, BMI, smoking status, and region.

#### Dataset Overview

| Feature | Type | Description |
|---|---|---|
| `age` | int | Age of the policyholder |
| `sex` | categorical | Gender (male / female) |
| `bmi` | float | Body Mass Index |
| `children` | int | Number of dependents |
| `smoker` | categorical | Smoking status (yes / no) |
| `region` | categorical | US region (northeast / northwest / southeast / southwest) |
| `charges` | float | Medical insurance cost billed (**target variable**) |

**Records:** 1,338 rows × 7 columns

#### Pipeline Walkthrough

**EDA**
- Distribution plots (histplot with KDE) for `age`, `bmi`, `children`, `charges`
- Count plots for categorical features: `sex`, `smoker`, `children`
- Box plots for outlier detection
- Correlation heatmap (Pearson) across numeric features

**Data Cleaning & Preprocessing**
- Removed duplicate rows
- Label encoded binary categories: `sex` → `is_female`, `smoker` → `is_smoker`
- One-hot encoded `region` using `pd.get_dummies` (drop_first=True)

**Feature Engineering**
- Created `bmi_category` using `pd.cut` with clinically standard bins:
  - Underweight (< 18.5) · Normal (18.5–24.9) · Overweight (25–29.9) · Obese (≥ 30)
- One-hot encoded `bmi_category` (drop_first=True)

**Feature Scaling**
- Applied `StandardScaler` to continuous features: `age`, `bmi`, `children`

**Feature Selection**
- Pearson correlation for numeric features vs `charges`
- Chi-square test (`chi2_contingency`) for categorical features vs binned charges
- Final selected features: `age`, `is_female`, `bmi`, `children`, `is_smoker`, `region_southeast`, `bmi_category_obese`

**Modeling**
- Trained a **Linear Regression** model on selected features
- Evaluated using **R²** and **Adjusted R²** scores

---

### 2. ❤️ Heart Disease Prediction (Classification)

**Notebooks:** `ML_basics_heart.ipynb`, `ML_heart_disease.ipynb`
**Dataset:** `heart.csv`

Predicts presence of heart disease from clinical measurements.

#### Pipeline Walkthrough

**EDA**
- Distribution plots for `Age`, `RestingBP`, `Cholesterol`, `MaxHR`
- Count plots of `HeartDisease` vs `Sex`, `FastingBS`
- Box plot (`Cholesterol` vs `HeartDisease`) and violin plot (`Age` vs `HeartDisease`)
- Correlation heatmap across numeric features

**Data Cleaning & Preprocessing**
- Identified invalid zero values in `Cholesterol` and `RestingBP` (data entry anomalies) and imputed them with the mean of valid values
- One-hot encoded all categorical columns (`pd.get_dummies`, drop_first=True)
- Applied `StandardScaler` to `Age`, `RestingBP`, `Cholesterol`, `MaxHR`, `Oldpeak`

**Modeling & Evaluation**
- Trained and compared 5 classifiers: **Logistic Regression, KNN, Naive Bayes, Decision Tree, SVM (RBF kernel)**
- Evaluated using Accuracy and F1-score (chosen for balanced precision/recall)
- Best-performing model (**KNN**) serialized with `joblib` (`KNN_heart.pkl`, `scaler.pkl`, `columns.pkl`) for reuse/deployment

---

### 3. 🚢 Titanic Survival Prediction (Classification)

**Notebook:** `tittanic_survival.ipynb`
**Dataset:** Seaborn's built-in `titanic` dataset

Predicts passenger survival based on demographic and travel details.

#### Pipeline Walkthrough

**Data Cleaning**
- Dropped high-missing/redundant columns: `class`, `who`, `adult_male`, `deck`, `embark_town`, `alive`
- Imputed missing `age` values with the column mean
- Dropped rows with missing `embarked` values
- Label encoded `sex` and `embarked`

**Modeling & Evaluation**
- Trained and compared 5 classifiers: **Logistic Regression, KNN, Naive Bayes, Decision Tree, SVM (linear kernel)**
- Evaluated using Accuracy Score, Confusion Matrix, and Classification Report
- Applied **Feature Scaling** (StandardScaler) for distance-based models (KNN, SVM)
- Validated model robustness with **5-fold Cross-Validation**

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, transformation |
| `numpy` | Numerical operations |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical plots (histplot, boxplot, heatmap, countplot, violinplot) |
| `scikit-learn` | Preprocessing, model training, evaluation, cross-validation |
| `scipy` | Pearson correlation, Chi-square feature selection |
| `joblib` | Model & preprocessing object serialization |

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/AYUSHGUPTA9506/<repo-name>.git
cd Machine_Learning_basics
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy joblib
```

### 3. Run the notebooks

Open in Jupyter or VS Code:

```bash
jupyter notebook ML_Insurance_updated.ipynb
jupyter notebook ML_heart_disease.ipynb
jupyter notebook tittanic_survival.ipynb
```

> **Note:** `insurance.csv` and `heart.csv` must be in the same directory as their respective notebooks. `tittanic_survival.ipynb` loads its dataset directly via `seaborn.load_dataset("titanic")`, so no CSV is required for that project.

---

## 📊 Key Insights

- **Smoking** is the strongest predictor of insurance charges — smokers are charged significantly more
- **BMI ≥ 30 (Obese)** is a key engineered feature that correlates strongly with high insurance charges
- **Age** shows a consistent positive correlation with charges across both insurance and heart disease datasets
- **Region** has relatively low predictive power for insurance charges compared to lifestyle factors
- **Cholesterol = 0** and **RestingBP = 0** in the heart dataset were data entry errors, not true missing values — corrected via mean imputation
- **KNN** performed best for heart disease classification among the tested models
- For Titanic survival, **sex** and **passenger class** are among the strongest predictors; feature scaling notably improves KNN/SVM performance

---

## 👤 Author

**Ayush Gupta**
Data Science & AI | ML · Deep Learning · Generative AI · MLOps
[GitHub](https://github.com/AYUSHGUPTA9506)
