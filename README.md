# Stroke Prediction
## Predicting whether a patient is likely to have a stroke or not

**Author**: Carla Cloete

### Business problem:

A hospitals' board of directors would like to predict whether a patient is likely to have a stoke or not based on demographic and health-related data

### Data:

Stroke Prediciton Dataset: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

For this dataset, there were 5110 rows and 11 columns

**Data Dictionary**

* id: unique identifier
* gender: "Male", "Female" or "Other"
* age: age of the patient
* hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
* heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
* ever_married: "No" or "Yes"
* work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
* Residence_type: "Rural" or "Urban"
* avg_glucose_level: average glucose level in blood
* bmi: body mass index
* smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
* stroke: 1 if the patient had a stroke or 0 if not


## Methods
- The following steps were taken to clean the dataset:
  -  Duplicate values were evaluated 
  -  Inconsistent categorical values were evaluated and replaced
  -  Impossible numerical values were evaluated and replaced
  -  Unwanted columns were dropped
    
- Each feature was explored:
  - Boxplots and histograms were ploted for numerical data
  - Countplots were plotted for categorical data

- After the exploratory analysis, an explanatory analysis was done on each feature in relation to the target:
  
  - The bar plot below shows that the average age of people who had strokes are higher than the average age of people who did not have strokes
    
<img width="500" alt="Figure 1- Stroke vs Age" src="https://github.com/Carla9711/Machine-Learning---Classification/assets/138701194/086e70b7-0903-43dd-85a9-8021ec493ea3">

  - The count plot below shows that 4.2% of people that do not have a heart disease are likely to have a stoke
  - This percentace increases to 17% for people who do have a heart disease

<img width="500" alt="Figure 2 - Heart Disease vs Stroke" src="https://github.com/Carla9711/Machine-Learning---Classification/assets/138701194/a5b4444a-b4db-498e-9800-1b745db3617a">

- The following steps were taken to prepare the data for modeling
  - Numerical Columns
    - Missing values were imputed with the median
    - Columns were scaled   
  - Ordinal
    - Columns were binary encoded and scaled
  - Nominal
    - Columns were hot one encoded        

## Results
- Three models were fitted and evaluated:
  - Logistic Regression
  - K Nearest Neighbors
  - XGBoost Classifier
- Various forms of undersampling, oversampling, tuning and feature engineering were applied to each model

The Logistic Regression model with Undersampling performed the best. The results for this model are displayed below:

<img width="668" alt="Best Model_Confusion Matrix" src="https://github.com/Carla9711/Machine-Learning---Classification/assets/138701194/a445b21c-0e9d-4745-a2fa-68511f870fba">


<img width="275" alt="Best Model_Classification Report" src="https://github.com/Carla9711/Machine-Learning---Classification/assets/138701194/e4b6801a-38db-4a82-938f-55b3e27fa30e">

Key Metrics:
* Recall (Test) = 0.82
* Accuracy (Test) = 0.71 

## Summary of Results

The Logistic Regression model with Undersampling performed the best as it achieved the best recall value on the test data without sacrificing precision too much.

In this task we are trying to predict a health condition and therefore the priority was to achieve the best recall value as it's more costly to predict someone not having a stroke when they actually do have a stroke. 

However, a low precision value could also be harmful because we could be giving a patient who will not have a stroke the wrong medication.


## Recommendations:

To achieve better precision and recall values, additional feature engineering steps can be applied to the data.
Additionally, features with better correlations to the target should be sourced.


### For further information

For any additional questions, please contact CLTCAR010@myuct.ac.za
