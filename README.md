# 🤖 Machine Learning Projects

<<<<<<< HEAD
A hands-on collection of end-to-end machine learning projects covering real-world datasets — from raw data exploration to trained, evaluated models.
=======
A comprehensive collection of hands-on Machine Learning projects covering the complete ML workflow—from Exploratory Data Analysis (EDA) and feature engineering to regression, classification, ensemble learning, and hyperparameter tuning.

This repository is designed for beginners and intermediate learners who want practical implementations of machine learning algorithms using real-world datasets.
>>>>>>> e697c66 (your commit message)

---

# 📂 Repository Structure

```
Machine_Learning_Projects/
│
<<<<<<< HEAD
├── ML_basics_insurance.ipynb     # Insurance EDA & preprocessing (regression)
├── ML_Insurance_updated.ipynb    # Insurance charges prediction w/ Linear Regression
├── insurance.csv                 # Medical insurance dataset (1,338 records)
│
├── ML_basics_heart.ipynb         # Heart disease EDA & preprocessing (classification)
├── ML_heart_disease.ipynb        # Heart disease prediction w/ multiple ML models
├── heart.csv                     # Heart disease dataset
│
├── tittanic_survival.ipynb       # Titanic survival prediction (classification)
=======
├── ML_basics_insurance.ipynb
├── insurance.csv
│
├── ML_basics_heart.ipynb
├── heart.csv
│
├── ford_car_price_prediction_regression.ipynb
├── ford_car_price_prediction_regression.csv
│
├── Ensemble_learning.ipynb
├── Grid_Search.ipynb
>>>>>>> e697c66 (your commit message)
│
└── README.md
```

---

# 📚 Projects Included

<<<<<<< HEAD
### 1. 💰 Insurance Charges Prediction (Regression)

**Notebooks:** `ML_basics_insurance.ipynb`, `ML_Insurance_updated.ipynb`
**Dataset:** `insurance.csv`
=======
## 1️⃣ Insurance Charges Prediction

**Problem Type:** Regression
>>>>>>> e697c66 (your commit message)

Predict medical insurance charges using demographic and health-related features.

### Topics Covered

- Exploratory Data Analysis (EDA)
- Data Cleaning
- Feature Engineering
- Feature Scaling
- Feature Selection
- Regression Pipeline

### Dataset

- 1,338 records
- 7 features

<<<<<<< HEAD
**EDA**
- Distribution plots (histplot with KDE) for `age`, `bmi`, `children`, `charges`
- Count plots for categorical features: `sex`, `smoker`, `children`
- Box plots for outlier detection
- Correlation heatmap (Pearson) across numeric features
=======
### Libraries
>>>>>>> e697c66 (your commit message)

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

**Modeling**
- Trained a **Linear Regression** model on selected features
- Evaluated using **R²** and **Adjusted R²** scores

---

<<<<<<< HEAD
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
=======
## 2️⃣ Heart Disease Prediction

**Problem Type:** Classification

Binary classification project predicting the presence of heart disease.

### Topics Covered

- Data Cleaning
- EDA
- Correlation Analysis
- Feature Scaling
- Classification Preparation
>>>>>>> e697c66 (your commit message)

---

## 3️⃣ Ford Car Price Prediction

<<<<<<< HEAD
| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, transformation |
| `numpy` | Numerical operations |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical plots (histplot, boxplot, heatmap, countplot, violinplot) |
| `scikit-learn` | Preprocessing, model training, evaluation, cross-validation |
| `scipy` | Pearson correlation, Chi-square feature selection |
| `joblib` | Model & preprocessing object serialization |
=======
**Problem Type:** Regression

Predict used Ford car prices using vehicle specifications.

### Topics Covered

- Data Cleaning
- Missing Value Handling
- Feature Encoding
- Feature Scaling
- Regression Models
- Model Evaluation

### Evaluation Metrics

- MAE
- MSE
- RMSE
- R² Score
>>>>>>> e697c66 (your commit message)

---

## 4️⃣ Ensemble Learning

Learn powerful ensemble algorithms used in industry.

### Algorithms Covered

- Random Forest
- Bagging
- AdaBoost
- Gradient Boosting
- Voting Classifier
- Stacking

### Concepts

- Bias vs Variance
- Bootstrap Aggregation
- Weak Learners
- Feature Importance

---

## 5️⃣ Hyperparameter Tuning using GridSearchCV

Learn model optimization techniques.

### Topics Covered

- GridSearchCV
- Cross Validation
- Parameter Tuning
- Best Parameter Selection
- Performance Comparison

---

# 🛠 Tech Stack

| Category | Libraries |
|-----------|-----------|
| Data Processing | pandas, numpy |
| Visualization | matplotlib, seaborn |
| Machine Learning | scikit-learn |
| Statistics | scipy |
| Hyperparameter Tuning | GridSearchCV |
| Ensemble Learning | Random Forest, AdaBoost, Gradient Boosting |

---

# 📈 Machine Learning Workflow

```
Raw Dataset
      │
      ▼
Data Cleaning
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Feature Engineering
      │
      ▼
Feature Selection
      │
      ▼
Train-Test Split
      │
      ▼
Feature Scaling
      │
      ▼
Model Training
      │
      ▼
Hyperparameter Tuning
      │
      ▼
Model Evaluation
      │
      ▼
Final Prediction
```

---

# 🚀 Installation

Clone the repository

```bash
<<<<<<< HEAD
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
=======
git clone https://github.com/AYUSHGUPTA9506/<repository-name>.git
```

Move into the project directory

```bash
cd Machine_Learning_Projects
```

Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

Launch Jupyter Notebook

```bash
jupyter notebook
```
>>>>>>> e697c66 (your commit message)

---

# 📊 Skills Demonstrated

<<<<<<< HEAD
- **Smoking** is the strongest predictor of insurance charges — smokers are charged significantly more
- **BMI ≥ 30 (Obese)** is a key engineered feature that correlates strongly with high insurance charges
- **Age** shows a consistent positive correlation with charges across both insurance and heart disease datasets
- **Region** has relatively low predictive power for insurance charges compared to lifestyle factors
- **Cholesterol = 0** and **RestingBP = 0** in the heart dataset were data entry errors, not true missing values — corrected via mean imputation
- **KNN** performed best for heart disease classification among the tested models
- For Titanic survival, **sex** and **passenger class** are among the strongest predictors; feature scaling notably improves KNN/SVM performance
=======
- Data Cleaning
- Data Visualization
- Exploratory Data Analysis
- Feature Engineering
- Feature Scaling
- Feature Selection
- Regression
- Classification
- Ensemble Learning
- Hyperparameter Tuning
- Cross Validation
- Model Evaluation
>>>>>>> e697c66 (your commit message)

---

# 📖 Libraries Used

<<<<<<< HEAD
**Ayush Gupta**
Data Science & AI | ML · Deep Learning · Generative AI · MLOps
[GitHub](https://github.com/AYUSHGUPTA9506)
=======
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- scikit-learn

---

# 🎯 Learning Outcomes

After completing these notebooks, you'll understand:

- End-to-end machine learning workflow
- Regression techniques
- Classification techniques
- Ensemble methods
- Hyperparameter optimization
- Model evaluation metrics
- Feature engineering
- Cross-validation
- Best practices in ML pipelines

---

# 👨‍💻 Author

**Ayush Gupta**

Data Science | Machine Learning | Deep Learning | Generative AI | MLOps

GitHub: https://github.com/AYUSHGUPTA9506

---

⭐ If you found this repository useful, consider giving it a star!
>>>>>>> e697c66 (your commit message)
