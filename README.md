# Pump-It-Up
Github Link: https://github.com/KrishRN/Pump-It-Up

Competition Link: https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/

This Approach is based on feature engineering and usage of Boosting algorithm bases Model Catboost for classification of Wells in the Tanzania

**Accuracy of best model  : 0.8239**

**Final Rank              : 441**


***

## 1) Exploratory Data Analysis
Data was explored initally using the *Pandas Profiling* library. It revealed that some columns have a high cardinality, and some have a very high missing value count.
Then the data was plotted and explored columnwise as well as pairwise to get the correlation between the columns.
- It was found that the target values are highly imbalanced mainly the target class "functional needs repair"
- Some Columns almost contained the same information and some other columns were of hierachchy.
   1. extraction_type, extrcation_type_group and extraction_type_class
   2. source, source_type and source_class
   3. scheme_management, management and management_group
   4. quantity and quantity_group
   5. water_quality and quality_group
   6. payment and pay
- District code and region code have a strong positive correlation as well as the Construction year and gps height 
- One Column Contained only one distinct value for all columns : 'recorded_by'
- Installer and funder column had a lot of incorrect data/ spelling mistakes
- Some Columns contained a lot of zero and null values

***
## 2) Outliers Identification
When exploring the Latitude and longitude columns identified outliers in both the columns. as some of the coordinates were outside the country tanzania and some were in the ocean.
SO Had to change the value of those by finding the mean of true values.

***

## 2) Pre-processing and Feature selection

- Outlier identification and fixing those error data by replacing with the means.
- With the help of EDA dropped the similar columns
- Handling of missing values and Zero values by replacing them with mean or value==1 as well as with value='missing'
- Construction year was transformed into decades as added to the same column and missing values are specified as missing
- Installer and funder column spleeing mistakes and zero values were changed and explored and reduced their cardinality by taking first few values with high values and changed others as value="Others"

***

## 3) Model
i have used CatBoost encoding also carried out by the model i tried to use Optuna a hyperparamter tuning model of catboost to get the Model pbest params but couldn't run due to high load of data. Also Used Sequential Feature selection to select the best features for the model and encoded the values using TargetEncoder and RobustScaler for categorical and numerical data.

***

## Proof of submission

DrivenData username: Krishanthan

![Rank](https://github.com/KrishRN/Pump-It-Up/blob/main/Rank.PNG)

![Submissions](https://github.com/KrishRN/Pump-It-Up/blob/main/Submissions.png)


