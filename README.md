# 🛡️ Cybersecurity Incident Classification Using Machine Learning

This project implements a robust machine learning pipeline to classify cybersecurity incidents into three classes: **True Positive (TP)**, **Benign Positive (BP)**, and **False Positive (FP)**. It leverages the Microsoft GUIDE dataset to support **Security Operation Centers (SOCs)** in automating incident triage and improving threat detection workflows.

---

## 📌 Overview

- **Dataset**: Microsoft GUIDE dataset (processed into `traindata_processed.csv` and `testdata_processed.csv`)
- **Goal**: Accurately classify incident outcomes to reduce false positives and streamline security operations.
- **Tech Stack**: Python, Scikit-learn, XGBoost, LightGBM, SHAP, Pandas, Seaborn, Matplotlib

---

## 🔄 Workflow

### 1. 📊 Data Preprocessing
- Removed features with >50% missing values.
- Converted timestamp into `hour`, `day`, and `month` features.
- Encoded categorical variables using `LabelEncoder`.
- Dropped highly correlated features to improve model performance.
- Cleaned missing values and removed duplicates.

### 2. 📈 Exploratory Data Analysis (EDA)
- Visualized class distributions by time (hour, day, month).
- Identified and visualized class imbalance in TP/BP/FP labels.
- Created a correlation heatmap to identify redundant features.

### 3. 🧠 Model Development
- **Baseline Models**: Logistic Regression, Decision Tree
- **Advanced Models**: Random Forest, Gradient Boosting, XGBoost, LightGBM
- **Imbalance Handling**: SMOTE and class-weight adjustments
- **Hyperparameter Tuning**: Used `RandomizedSearchCV` for XGBoost

### 4. 🧠 Feature Importance
- Applied **SHAP** to determine key influencing features.
- Selected top 11 features (e.g., `OrgId`, `IncidentId`, `AlertTitle`, `DetectorId`) to improve efficiency.

### 5. ✅ Final Evaluation
- Achieved **Macro-F1 Score**:
  - Validation Set: **0.91**
  - Test Set: **0.90**
- Balanced precision and recall across all three classes.
- Saved the final model using `joblib` for easy deployment.

---

## 📁 Dataset Details

- **Source**: Microsoft GUIDE (via Kaggle)
- **Files**: 
  - `GUIDE_train.csv` (2.43 GB)
  - `GUIDE_test.csv` (1.09 GB)
- **Scope**:
  - Over 13 million evidence entries
  - Includes 1M+ labeled incidents across 6,100+ organizations
  - 441 MITRE ATT&CK techniques tracked

---

## 📦 Technologies Used

| Category           | Tools & Libraries                                 |
|--------------------|--------------------------------------------------|
| Programming        | Python                                           |
| Data Handling      | pandas, numpy                                    |
| Visualization      | seaborn, matplotlib                              |
| Machine Learning   | scikit-learn, XGBoost, LightGBM, imbalanced-learn |
| Model Tuning       | RandomizedSearchCV                               |
| Feature Analysis   | SHAP                                             |
| Model Persistence  | joblib                                           |

---

## 🚀 Use Cases

- **Security Operations Centers (SOCs)**: Automate triage and prioritize high-risk incidents.
- **Incident Response**: Suggest appropriate remediation strategies.
- **Threat Intelligence**: Improve detection using historical patterns.
- **Enterprise Security**: Reduce analyst fatigue by minimizing false positives.

---
