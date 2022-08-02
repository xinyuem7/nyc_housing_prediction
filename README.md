# NYC Housing Price Prediction
A Supervised Machine Learning Project: 

## Overview
As I was making plans to move to NYC, I was wondering the price of NYC's residential properties and how it would change with respect to locations, gross square feet, year built, and many other factors.

On [the Official Website of the City of New York](https://www1.nyc.gov/), I found data sets that contained [NYC properties sale data from July 2021 to June 2022](https://www1.nyc.gov/site/finance/taxes/property-rolling-sales-data.page).

## Detailed Steps
**1. Understand the dataset and Data Cleaning**
- checked the number of data entries and the number of variables
- checked the variable types and null counts for each variables
- dropped rows with null values
- dropped unseasonable values, such as SALE PRICE = 0
- categorized numerical variables and categorical variables

**2. Data Exploration**
- understand the distribution of numerical variables using histogram
   - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/land%20square%20feet%20og.png?raw=true)
   - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/residential%20unit%20og.png?raw=true)
   - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/year%20built%20og.png?raw=true)
- used `.describe()` to learn about the quantiles and outliers
- understand categorical variables better by ploting bar plots
   - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/building%20class%20vs%20mean%20price.png?raw=true)
   - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/tax%20class%20vs%20mean%20price.png?raw=true)

**3. Feature Selection**
- for numerical varriables
   - check the correlation among numerical variables in order to avoid multicollinearity for regression model: turned out TOTAL UNITS, RESIDENTIAL UNITS, GROSS SQUARE FEET are highly corelated, thus TOTAL UNITS and GROSS SQUARE FEET were not be included in the model.
      - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/heat%20map.png?raw=true)

**4. Feature Engineering**
- filtered out outliers from LAND SQUARE FEET and RESIDENTIAL UNITS
- applied log tranformation to LAND SQUARE FEET and RESIDENTIAL UNITS, but will only use log(LAND SQUARE FEET) and not log(RESIDENTIAL UNITS)
   - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/land%20square%20feet%20log.png?raw=true)
   - ![](https://github.com/xinyuem7/nyc_housing_price_prediction/blob/main/images/residential%20units%20log.png?raw=true)
- converted RESIDENTIAL UNITS to a categorical variable
- among *BOROUGH, NEIGHBORHOOD, BLOCK, LOT, ZIP CODE* I chose to work with ZIP CODE because ZIP CODE gives more granularity than BOROUGH and it can be reduced to [42 neighborhoods](https://storage.googleapis.com/plos-corpus-prod/10.1371/journal.pone.0194799/1/pone.0194799.s001.pdf?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=wombat-sa%40plos-prod.iam.gserviceaccount.com%2F20220715%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20220715T143032Z&X-Goog-Expires=86400&X-Goog-SignedHeaders=host&X-Goog-Signature=020e10b73f2e9f42564fd7fd53cf0e0b69688ef5e6bc88ae53341746c081227647b2be9aa327feaadc432db5c267364261f5659de907c7b2e2b4c1fc42660c6549bf7f241a6a8b298aa99adc245322e5a2bc5be2c6083f92d9563add62440840cc04a327d8f9a4254011728aec3bf541408f116d22a195c9338cce747bf89c52310c32a47c35423da104569ad1fa4331fe21ca564d941c51290aa2dc0a2e2eb43102a071ed519fba6fa781517bab8f75823fd70192817b62cf140ed6c9330e34b64c405297bfff2a135e310a32a61dd6b6a5a3f583c2adde1d7a9914ab7320a0aee9298794b56b8897a55c8c2fdc479c8a5c081d5c7eeb42f15c2d84347365f6) which can be used as a categorical variable.
- did features scaling
      
**5. Data Prepricessing for Model**
- include only relevant variables
- create dummies for categorical variables
- create X_train_scaled, y_train_scaled, X_train, y_train, X_test_scaled, y_test_scaled, X_test, y_test

**6. Model Performance (base line)**
- Linear Regression (R^2): 0.37

**7. Model Performance (after variable tunning)**
- Linear Regression (R^2): 0.63
