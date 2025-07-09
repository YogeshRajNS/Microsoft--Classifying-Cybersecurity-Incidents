🛡️ Cybersecurity Incident Classification with Machine Learning
This repository presents a machine learning-based solution for classifying cybersecurity incidents into three categories: True Positive (TP), Benign Positive (BP), and False Positive (FP). Leveraging the Microsoft GUIDE dataset, the system is designed to assist Security Operations Centers (SOCs) in automating incident triage, reducing manual overhead, and improving threat response accuracy.

🔍 Project Highlights
🔧 Data Preprocessing & Feature Engineering
Removed features with more than 50% missing values.

Extracted temporal features such as hour, day, and month from timestamp fields.

Encoded categorical variables using LabelEncoder.

Eliminated highly correlated features to reduce redundancy.

Handled missing and duplicate entries to ensure clean and reliable datasets.

🤖 Model Development & Optimization
Baseline Models: Logistic Regression, Decision Tree.

Advanced Models: Random Forest, Gradient Boosting, XGBoost, LightGBM.

Imbalance Handling: Applied SMOTE and adjusted class weights to tackle label imbalance.

Hyperparameter Tuning: Used RandomizedSearchCV for tuning key model parameters such as max_depth, learning_rate, and n_estimators.

📈 Model Evaluation & Explainability
Evaluation Metrics: Macro F1-Score, Precision, Recall.

Feature Interpretation using SHAP (SHapley Additive exPlanations) to identify influential features.

Comparison across models to choose the best performer for deployment.

🚀 Deployment-Ready Pipeline
Final model exported using joblib for seamless deployment.

Code modularized for easy integration into SOC workflows or SIEM platforms.

💼 Real-World Applications
Security Operation Centers (SOCs)
Automates incident triage to accelerate identification and response to threats.

Incident Response Systems
Provides automated suggestions for appropriate remediation actions.

Threat Intelligence
Leverages past evidence to improve detection and alert quality.

Enterprise Security
Reduces alert fatigue by filtering false positives and prioritizing critical incidents.

📊 Dataset Overview
Source: [Microsoft GUIDE Dataset (Kaggle)]

Files: GUIDE_train.csv (2.43 GB), GUIDE_test.csv (1.09 GB)

Structure: Evidence-level, Alert-level, and Incident-level data

Labels: Incident classification - TP, BP, FP

Volume: Over 13 million evidence entries across 6,100+ organizations

Processed Files: traindata_processed.csv, testdata_processed.csv

📁 Project Structure
Data Cleaning & Preprocessing
Null removal, encoding, time-based feature extraction

Exploratory Data Analysis (EDA)
Visualized trends by hour/day/month and examined label imbalance

Model Training
Benchmarked multiple models, handled imbalance, evaluated performance

Hyperparameter Tuning
Optimized XGBoost using RandomizedSearchCV

SHAP Feature Importance
Selected top predictors to enhance performance and reduce training time

Final Model Evaluation
Achieved strong generalization on unseen test data

✅ Results
Best Performing Model: XGBoost (tuned, without SMOTE)

Macro-F1 Score:

Validation: 0.91

Test: 0.90

Top Features: OrgId, IncidentId, AlertTitle, DetectorId, etc.

Model Characteristics:

Balanced performance across all three classes (TP, BP, FP)

Efficient and explainable predictions for security analysts

🛠️ Tech Stack
Category	Tools / Libraries
Language	Python
Data Handling	pandas, numpy
Visualization	matplotlib, seaborn
ML Models	scikit-learn, XGBoost, LightGBM, RandomForest
Imbalance	imbalanced-learn (SMOTE)
Feature Analysis	SHAP
Model Persistence	joblib
