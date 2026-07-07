# Diabetes Risk Prediction
This data analysis project examining which clinical and lifestyle factors are most strongly associated with diabetes risk, using the Pima Indians Diabetes dataset.

## 📌Case Study Overview 
This project explores 768 patient records to identify patterns and risk factors associated
with diabetes onset. The analysis moves from data quality checks through univariate and
bivariate analysis, correlation analysis, and clinically-informed risk groupings

## 📊Data Set Description 

* Source: [Pima Indians Diabetes Dataset](http://kaggle.com) 
* Size: 768
* Column Description:
|Column                  |Description                                |
|------------------------|-------------------------------------------|
|Pregnancies             |Number of times pregnant                   |
|Glucose                 |Plasma glucose concentration               |
|BloodPressure           |Diastolic blood pressure (mm Hg)           |
|SkinThickness           |Triceps skinfold thickness (mm)            |
|Insulin                 |2-Hour serum insulin (mu U/ml)             |
|BMI                     |Body mass index                            |
|DiabetesPedigreeFunction|Diabetes likelihood based on family history|
|Age                     |Age in years                               |
|Outcome                 |0 = No diabetes, 1 = Diabetes              |

## 🚧Project Structure

```
diabetes-risk-prediction-ml-eda/
├── diabetes.csv
├── Diabetes.ipynb
├── images/
│   ├── outcome_distribution.png
│   ├── feature_distributions.png
│   ├── feature_by_outcome.png
│   ├── correlation_heatmap.png
│   ├── diabetes_by_age_group.png
│   ├── diabetes_by_bmi_category.png
│   └── diabetes_by_glucose_category.png
├── README.md
```

## 🧰 Tools and Libraries

* Python 3.12
* NumPy
* Pandas
* Matplotlib
* Seaborn
* joblib


# 🔄 Project Workflow

## 📊 Data loading and initial inspection
```python
diabetes = pd.read_csv("Diabetes.csv")
```
## 🧹 Data Quality Checks
* Check for missing values
* Fixed inconsistent enteries
* Identifying biologically implausible zero values (treated as
   missing data) in Glucose, BloodPressure, SkinThickness, Insulin, and BMI

## ✅ Exploratory Data Analysis (EDA)
. **Target variable distribution** — checking class balance
. **Univariate analysis** — distribution of each clinical/lifestyle feature
. **Bivariate analysis** — comparing each feature across diabetic vs. non-diabetic groups
. **Correlation analysis** — identifying linear relationships between features and outcome
. **Clinical risk groupings** — diabetes rate by Age group, BMI category (WHO cutoffs), and Glucose category (clinical thresholds)

 ## 🚧 Key EDA Findings
**Glucose** is the strongest single factor associated with diabetes risk (r = 0.49), with
  diabetes prevalence rising from ~9% (Normal glucose) to ~59% (Diabetic range glucose).
**BMI** shows a similarly strong pattern — diabetes rate rises from ~6% (Normal weight) to
  ~46% (Obese).
**Age** is associated with increased risk up to the 50–60 bracket; the apparent decline in
  the 60+ group (n=27) is likely a small-sample artifact rather than a true reversal.
**BloodPressure** and **DiabetesPedigreeFunction** were the weakest linear predictors in
  this dataset.
**Insulin (48.7%) and SkinThickness (29.6%) had substantial missing data (recorded as zeros),
  which limits confidence in findings involving these two features.

## 📌 Limitations
* Correlation only captures linear relationships; some features may still hold predictive
  value through non-linear patterns.
* High missingness in Insulin and SkinThickness limits conclusions involving those features.
* Small subgroup sizes (e.g. 60+ age group, Underweight BMI category) limit reliability of
  findings in those specific segments.

## 💡 Conclusion: What Next? 
* Handle missing data through imputation strategies
* Address class imbalance (e.g. class weighting, SMOTE)
* Build and compare classification models (Logistic Regression, Random Forest, XGBoost) to
  predict diabetes risk




Implement regular reviews of pay and performance equity
