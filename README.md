# SaniHassanMuhammad_P25EGCP8021_Project
COEN807 Term Project

Credit Card Fraud Detection Using Machine Learning

    

📌 Project Overview

This project develops and evaluates multiple machine learning models for detecting fraudulent credit card transactions. Fraud detection is a critical challenge in the financial sector due to the highly imbalanced nature of transaction datasets, where fraudulent activities represent only a tiny fraction of all transactions.

The project applies data preprocessing, feature scaling, class balancing using SMOTE, model training, hyperparameter optimization, and performance evaluation to identify the most effective fraud detection model. The models compared include:

Logistic Regression

Support Vector Machine (SVM)

Random Forest

XGBoost


The implementation includes visualization of class distribution, feature correlations, confusion matrices, ROC curves, feature importance analysis, and comparative performance evaluation. 


---

🎯 Objectives

Detect fraudulent credit card transactions accurately.

Handle severe class imbalance using SMOTE.

Compare multiple machine learning algorithms.

Optimize model performance using GridSearchCV.

Evaluate models using industry-standard metrics.

Identify the most important fraud indicators.



---

📂 Dataset

The project uses the Credit Card Fraud Detection Dataset (creditcard.csv).

Dataset Characteristics

Contains credit card transactions made by European cardholders.

Highly imbalanced dataset.

Target Variable:

Class = 0 → Legitimate Transaction

Class = 1 → Fraudulent Transaction



Features

Time

Amount

V1 – V28 (PCA-transformed confidential features)

Class (Target Variable)



---

🛠️ Technologies Used

Programming Language

Python


Libraries

pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
xgboost


---

🔄 Project Workflow

1. Data Exploration

Dataset inspection

Statistical summaries

Missing value analysis

Fraud distribution visualization

Transaction amount distribution


2. Data Preprocessing

Standardization of:

Transaction Amount

Transaction Time


Removal of original Time and Amount columns


3. Train-Test Split

train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42,
    stratify=y
)

4. Handling Class Imbalance

SMOTE (Synthetic Minority Oversampling Technique) is used to balance the training data.

smote = SMOTE(random_state=42)
X_train_smote, y_train_smote = smote.fit_resample(X_train, y_train)

5. Model Training

Logistic Regression

LogisticRegression()

Support Vector Machine

SVC(kernel='rbf', probability=True)

Random Forest

RandomForestClassifier(
    n_estimators=100,
    random_state=42
)

XGBoost

XGBClassifier(
    eval_metric='logloss',
    random_state=42
)

6. Hyperparameter Optimization

Random Forest Grid Search

{
 'n_estimators':[100,200],
 'max_depth':[5,10,None],
 'min_samples_split':[2,5]
}

XGBoost Grid Search

{
 'n_estimators':[100,200],
 'learning_rate':[0.01,0.1],
 'max_depth':[3,5,7]
}


---

📊 Evaluation Metrics

The following metrics are used to evaluate model performance:

Accuracy

Precision

Recall

F1 Score

ROC-AUC Score


accuracy_score()
precision_score()
recall_score()
f1_score()
roc_auc_score()


---

📈 Visualizations

The project generates:

Data Analysis

Fraud vs Non-Fraud Distribution

Transaction Amount Distribution

Correlation Heatmap


Model Evaluation

Confusion Matrices

Classification Reports

ROC Curve Comparison


Model Interpretation

Feature Importance Analysis

F1 Score Ranking



---

📋 Expected Output

A comparison table similar to:

Model	Accuracy	Precision	Recall	F1 Score	ROC-AUC

Logistic Regression	-	-	-	-	-
SVM	-	-	-	-	-
Random Forest	-	-	-	-	-
XGBoost	-	-	-	-	-


The final ranking is based on F1 Score, which is especially important for fraud detection problems.


---

🔍 Feature Importance

The project uses XGBoost feature importance scores to identify the most influential variables contributing to fraud prediction.

importance = pd.DataFrame({
    'Feature': X.columns,
    'Importance': xgb.feature_importances_
})


---

🚀 Installation

Clone Repository

git clone https://github.com/yourusername/credit-card-fraud-detection.git
cd credit-card-fraud-detection

Create Virtual Environment

python -m venv venv

Activate Environment

Windows:

venv\Scripts\activate

Linux/Mac:

source venv/bin/activate

Install Dependencies

pip install -r requirements.txt


---

▶️ Running the Project

Ensure the dataset is placed in the project directory:

creditcard.csv

Run:

python fraud_detection.py


---

📁 Project Structure

credit-card-fraud-detection/
│
├── creditcard.csv
├── fraud_detection.py
├── requirements.txt
├── README.md
│
├── outputs/
│   ├── confusion_matrices/
│   ├── roc_curves/
│   ├── feature_importance/
│   └── model_comparison/
│
└── notebooks/
    └── analysis.ipynb


---

🔑 Key Features

✅ Fraud detection using multiple ML algorithms

✅ Class imbalance handling with SMOTE

✅ Hyperparameter tuning using GridSearchCV

✅ Comprehensive performance evaluation

✅ ROC Curve comparison

✅ Feature importance analysis

✅ Model ranking and benchmarking


---

📚 Future Improvements

Deep Learning Models (ANN, LSTM)

Ensemble Stacking Methods

Real-time Fraud Detection Pipeline

Explainable AI (SHAP, LIME)

Deployment using Flask/FastAPI
