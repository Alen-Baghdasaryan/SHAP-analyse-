Credit Risk Analysis with Logistic Regression & SHAP
A machine learning project for credit risk classification using the German Credit Dataset. The model predicts whether a bank customer is a good or bad credit risk, with SHAP (SHapley Additive exPlanations) used to interpret the model's decisions.

📋 Project Overview
This project applies Logistic Regression with L1-based feature selection and explains predictions using SHAP LinearExplainer. The goal is not only to achieve good classification accuracy but also to understand why the model makes each prediction.

📁 Repository Structure
├── regression_shap_analysis.py     # Main script: training, feature selection, SHAP analysis
├── model_summary.txt               # Model performance report (accuracy, F1, confusion matrix)
├── shap_feature_importance.csv     # Mean absolute SHAP values per feature
├── shap_values_real.xls            # Raw SHAP values for each test sample
├── shap_importance_bar.png         # Bar chart of top feature importances
├── shap_summary_beeswarm.png       # Beeswarm plot showing feature impact distribution
├── real_data_used.xlsx             # Preprocessed dataset used for training
└── German_Credit_Decoded.xlsx      # Original German Credit Dataset (decoded labels)

🤖 Model Details
ParameterValueAlgorithmLogistic Regression (L2 regularization)Feature SelectionL1 (Lasso) — top 15 featuresSolverLBFGSTest Split20%Accuracy79%AUC-ROCComputed during training
Classification Report
ClassPrecisionRecallF1-ScoreGood Credit (1)0.830.880.85Bad Credit (2)0.660.560.61Weighted Avg0.780.790.78

🔍 Top Features (SHAP)
The 15 most important features selected by the model:

Status_Checking_no checking account (most impactful)
Credit_History_critical account / other credits existing
Purpose_car (new)
Personal_Status_male: single
Installment_Rate
Duration
Credit_Amount
Other_Installment_Plans_none
Status_Checking_<0 DM
Savings_<100 DM
Age
Number_Credits
Purpose_education
Other_Debtors_guarantor
Purpose_car (used)


📊 SHAP Visualizations
Feature Importance Bar Chart
Show Image
Beeswarm Summary Plot
Show Image

🚀 How to Run
1. Install dependencies
bashpip install pandas numpy scikit-learn shap matplotlib openpyxl
2. Place your data file on the Desktop
The script automatically searches the Desktop for .csv, .xlsx, or .xls files.
3. Run the analysis
bashpython regression_shap_analysis.py
4. Results
All outputs are saved to the shap_results/ folder:

shap_importance_bar.png
shap_summary_beeswarm.png
shap_dependence_<feature>.png (top 4 features)
shap_values.csv
shap_feature_importance.csv
model_summary.txt


📦 Dataset
German Credit Dataset — 1,000 bank customers with 20 features describing personal, financial, and credit-related attributes. Target variable: 1 = Good credit, 2 = Bad credit.

🛠 Tech Stack

Python 3.10+
scikit-learn — Logistic Regression, feature selection, metrics
shap — Model interpretation (LinearExplainer)
pandas / numpy — Data processing
matplotlib — Visualization


👤 Author
Alen Baghdasaryan
GitHub: @Alen-Baghdasaryan
