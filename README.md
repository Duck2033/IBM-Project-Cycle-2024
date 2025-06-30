# IBM X UNSW Data Science Society Project Cycle 2024  

## 📌 Overview

This project was completed as part of the **IBM Data Science Project Cycle** during 2024. It follows a structured data science methodology, of cleaning, exploratory analysis, modeling, and evaluation.

# Capital Project Failure Analysis

This repository presents a comprehensive data analysis and machine learning investigation into factors contributing to the failure of public infrastructure projects. Using a dataset sourced from the NSW Government and provided via IBM SkillsBuild, the project involves data cleaning, exploratory data analysis (EDA), and predictive modeling to identify key drivers behind project failure.

## Dataset Overview

- **Source**: NSW Government (via IBM SkillsBuild)
- **Link**: [Download CSV](https://datasocibmproject.s3.ap-southeast-2.amazonaws.com/structured_data/capital_project_schedules_and_budgets_1.csv)
- **Contents**: Project metadata including:
  - Budget estimates and actual expenditure
  - Planned and actual start/end dates
  - Project phase, school name, type, geographic district
  - Binary project failure indicator (`True` / `False`)

## Objectives

- Preprocess and clean the dataset for analysis
- Perform feature engineering to enhance model interpretability
- Explore patterns and correlations using EDA techniques
- Train classification and regression models to:
  - Predict likelihood of project failure
  - Estimate missing project durations

## Methodology

### 1. Data Cleaning and Preprocessing
- Converted date fields to proper datetime formats, handled non-standard entries (e.g., `'PNS'`, `'DOES'`, blanks)
- Removed duplicate records
- Imputed or removed missing values where appropriate
- Casted numeric fields with coercion for invalid strings

### 2. Feature Engineering
- Calculated actual and planned durations (in days)
- Computed budget variance and end-date deviations
- Encoded categorical fields such as `project_type`
- Created binary target variable `ff` for modeling (`1` = failure, `0` = success)

### 3. Exploratory Data Analysis (EDA)
- Heatmaps for feature-failure correlations
- Boxplots for expenditure distributions
- Bar charts showing failure counts by district
- Assessment of relationships between timing, budget, and project outcome

### 4. Predictive Modeling
#### Classification Models (Target: `ff`)
- **Logistic Regression**
- **Decision Tree Classifier**
- **Support Vector Machine (SVM)**
- Evaluation using accuracy, confusion matrix, and classification reports

#### Regression Model (Target: `duration`)
- **Linear Regression** to estimate missing durations based on available features

## Key Findings

- Project failure is modestly associated with longer delays and higher budget variance
- Certain project types and geographic districts show elevated failure rates
- Decision Trees provided interpretable decision paths, identifying key features such as budget overrun and start/end timing
- Linear regression successfully filled in missing duration fields for use in further analysis


## Technologies Used

- Python (Pandas, NumPy)
- Data Visualization: Seaborn, Matplotlib
- Modeling: Scikit-learn (LogisticRegression, DecisionTreeClassifier, SVC, LinearRegression)
