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
   
*** Things I did: ***
- *LAND SQUARE FEET* and *GROSS SQUARE FEET*
   - drop unreasonable values and outliers
   - log tranformation to normalize them

**4. Feature Engineering**
- create new variables from existing variables
- data tranformation for skewed numerical variables 
- feature scaling
- for categorical variables that have too many categories, create new variables so that it has less categories

**5. Feature Selection**
*Need to look into this more*

**6. Data Prepricessing for Model**
- include only relevant variables
- impute data with mean/median if necessary
- create dummies for categorical variables
- create X-train, y_train, X_cv, y_cv, X_test, y_test

**6. Model Buidling**
*Need to choose models to work with*
*Gradient Descent*

**7. Learning Curve**
- use learning curve to check for underfitting and overfitting

**8. Results**
