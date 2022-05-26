## Problem Statment:

- Ames Assessor’s Office asked me to find good predictive Linear Regression model that would be able to assist them in setting a responsible price for their next purchase. My analysis will find housing features that correlate to Sale prices using past Ames Assessor’s Office housing purchase data. I will build a model that will help assist Ames Assessor’s Office on setting a responsible initial bid for their next house purchased.

## Data Dictionary:

- http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

## Quick Analysis Process Summary:

`EDA:`

1. I started out by cleaning all the data.

- I split the data into 2 categories numerical and categorical lists.
- I then split those into 5 sub categories lists id, numerical, numerical with missing, categorical, categorical with missing.

2. After analyzing "numerical with missing" list and "categorical with missing" list I decided to group them into smaller lists based on how many values were missing: If missing more then 50% of inputs, If missing less then 20% of inputs, and inbetween that.
3. I assumed many of these rows were misinputs for example, not every house is going to have a pool.
4. After fixing the missing data I converted all features to numerical values(OnehotEncode, astype).
5. I then ran a Correlation anlysis on SalesPrice to find features with high correlations (>.4).
6. I removed all outliers observations from numerical features.
7. Graphed all scatter plots with high correlations for 'saleprice'
8. Extracted those high correlations and created a graphics to convey my findings.

`Model:`

1. Cleaned data in the same process as I did my EDA.
2. Found High correlated features.
3. Combined features such as (totrms_abvgrd, full_bath), (garage_area, gr_liv_area), (1st_flr_sf, total_bsmt_sf).
4. Found my X and y and ran train test split.
5. I made a Column Transform with PolynomialFeatures for numeric and used StandardScaler to scale them, and OneHotEncoder for categorical features
6. I continously passed that Transformed data into a Pipline and tested lasso regression, ridge regression, and elastic_net regression using a GridsearchCV to fine tune parameters until I found the best fit and score.

## Conclusion:

- In Conclusion I believe my model was not amazing but good I had a Mean Squared Error of `32848.07` and the percent of variance present in the data that my model predicted was `0.85`. As compared to my baseline that had a mean Squared Error of `83671.64` and the percent of variance present in the data that the baseline model predicted was `-0.00460`. I suggest Ames Assessor’s Office to give me more housing data so I can improve my model’s performance as well as look add additional distance features such as distance from coast, distance from school, buyer type, etc.

### Sources:

- Gomez, Joe. “8 critical factors that influence a home’s value.” Opendoor. March 27, 2019.
  https://www.realtor.com/realestateandhomes-search/Ames_IA/overview

- Home values in Ames, IA
  https://www.opendoor.com/w/blog/factors-that-influence-home-value
