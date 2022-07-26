# NYC Housing Price Prediction
A Supervised Machine Learning Project: 

## Overview
Talk about why I wanted to do this project

A summary of what I did, and what model I ended up using, what variables are included in the model, what is the accuracy of the model

## [Dataset Used](https://www1.nyc.gov/site/finance/taxes/property-rolling-sales-data.page)
Link the dataset from Kaggle here, state the origin and the description: what are the variables

## Detailed Steps
**1. Understand the dataset**
- the number of data entries and the number of variables
- check the data type and null counts
- what are the numerical variables and what are the categorical variables
- for numerical variables, use `.describe()` to understand the central tendencies

**2. Data Cleaning**
- delete rows with invalid values

**3. Data Exploration**
- sepaprate the numerical and categorical variables
- for numerical varriables
   - understand the distribution of numerical variables using histogram
   - check the correlation among numerical variables in order to avoid multicollinearity for regression model
   - understand categorical variables better by ploting bar plots
   
   **Things I did:**
      - *LAND SQUARE FEET* and *GROSS SQUARE FEET*
         - drop unreasonable values and outliers
         - log tranformation to normalize them

**4. Feature Engineering**
- create new variables from existing variables
- data tranformation for skewed numerical variables 
- feature scaling
- for categorical variables that have too many categories, create new variables so that it has less categories

   **Things I did:**
      - among *BOROUGH, NEIGHBORHOOD, BLOCK, LOT, ZIP CODE* I chose to work with ZIP CODE because ZIP CODE gives more granularity than BOROUGH and it can be reduced to [42 neighborhoods](https://storage.googleapis.com/plos-corpus-prod/10.1371/journal.pone.0194799/1/pone.0194799.s001.pdf?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=wombat-sa%40plos-prod.iam.gserviceaccount.com%2F20220715%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20220715T143032Z&X-Goog-Expires=86400&X-Goog-SignedHeaders=host&X-Goog-Signature=020e10b73f2e9f42564fd7fd53cf0e0b69688ef5e6bc88ae53341746c081227647b2be9aa327feaadc432db5c267364261f5659de907c7b2e2b4c1fc42660c6549bf7f241a6a8b298aa99adc245322e5a2bc5be2c6083f92d9563add62440840cc04a327d8f9a4254011728aec3bf541408f116d22a195c9338cce747bf89c52310c32a47c35423da104569ad1fa4331fe21ca564d941c51290aa2dc0a2e2eb43102a071ed519fba6fa781517bab8f75823fd70192817b62cf140ed6c9330e34b64c405297bfff2a135e310a32a61dd6b6a5a3f583c2adde1d7a9914ab7320a0aee9298794b56b8897a55c8c2fdc479c8a5c081d5c7eeb42f15c2d84347365f6) which can be used as a categorical variable.


**5. Feature Selection**
*Need to look into this more*

   **Things I realized while doing features selection:**
      - I think I over did this, I should've kept some variables even though there is strong correlation because later on the models that I will use sometime can helo with overfitting
      
**6. Data Prepricessing for Model**
- include only relevant variables
- impute data with mean/median if necessary
- create dummies for categorical variables
- create X-train, y_train, X_cv, y_cv, X_test, y_test

**6. Model Buidling**
*Need to choose models to work with*
*Gradient Descent*
*Random Forest: scaled data or non-scaled data*

**7. Learning Curve**
- use learning curve to check for underfitting and overfitting

**8. Results**
