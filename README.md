# Machine-Learning---Classification

# Prediction of Product Sales
## Sales prediction for food items sold at various stores

**Author**: Carla Cloete

### Business problem:

A retailer would like to understand the properties of products and outlets that play crucial roles in increasing sales.


### Data:

Outlet Sales Data: https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view?usp=sharing

For this dataset, there were 8523 rows and 12 columns

**Data Dictionary**

<img width="342" alt="Sales Prediction Data Dictionary" src="https://github.com/Carla9711/Prediction-of-Product-Sales/assets/138701194/bd530738-c9e2-41ff-8740-12d7ebb0fd61">


## Methods
- The following steps were taken to clean the dataset:
  -  Duplicate values were evaluated 
  -  Inconsistent categorical values were evaluated and replaced
  -  Impossible numerical values were evaluated and replaced
    
- Next, each feature was explored:
  - Boxplots and histograms were ploted for numerical data
  - Countplots were plotted for categorical data

- After the exploratory analysis, an explanatory analysis was done on each feature in relation to the target:
  - For numerical features a regression plot was plotted
  - 
<img width="500" alt="Figure 1- Stroke vs Age" src="https://github.com/Carla9711/Machine-Learning---Classification/assets/138701194/086e70b7-0903-43dd-85a9-8021ec493ea3">

  - For categorical features bar plots and strip plots were plotted
<img width="313" alt="Figure 2 - Heart Disease vs Stroke" src="https://github.com/Carla9711/Machine-Learning---Classification/assets/138701194/a5b4444a-b4db-498e-9800-1b745db3617a">



  
- Each feature was assessed in terms of cardinality, the business case and the relation to the target. The following features were dropped from the dataset
  - Outlet_Identifier is not a property of the outlet and was therefore dropped.
  - Item_Type had a high cardinality of 16 and each item type had a similar distribution of sales and was therefore dropped.
 
- The following steps were taken to prepare the data for modeling
  - Numerical Columns
    - Missing values were imputed with the median
    - Columns were scaled   
  - Ordinal
    - Columns were ordinal encoded and scaled
  - Nominal
    - Columns were hot one encoded        

## Results
- Two models were fitted and evaluated:
  - Logistic Regression
  - K Nearest Neighbors

The final results of each model is displayed below

<img width="346" alt="Model Results" src="https://github.com/Carla9711/Prediction-of-Product-Sales/assets/138701194/1e83c1d8-aea6-4877-a7d2-096482bb1410">

## Model

The recommened model is the tuned Random Forest model as it provided the best evaluation scores.

The R squared value for this model is 0.6 which is above 0.5 and is acceptable but not ideal. A R squared value closer to 1 would be more favourable.

Furthermore, the MAE for the model indicates that the predicted target can be expected to be about 734.6 units away from the actual target. This is about 34% of the average target price.

## Recommendations:

To achive higher R squared values and lower MAE, MSE and RSME values the dataset should be evaluated again. Columns that have little affect on the target should be dropped and new features that have better correlations to the target should be sourced.

## Limitations & Next Steps

The analysis and modeling was limited to the dataset provided. Next step would be to consult the retailer to see if there's additional data points (i.e. features) that can be used for modeling.


### For further information


For any additional questions, please contact CLTCAR010@myuct.ac.za
