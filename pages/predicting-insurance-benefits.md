# Predicting Insurance Benefits

<p align="center">
  <img src="/images/pairplot.png"
  width="350"
  height="250"
  alt="Insurance clip art">
</p>

## Project Overview 

**Purpose**   
An imbalanced classification supervised machine learning project predicting two outomes:  
1) Whether a customer will use insurance benefits
3) How many benefits a customer will use  

**Techiniques**   
Pipelines, GridSearchCV, and SMOTE, SMOTEENN, and class weighting are applied to balance, tune, and fit binary and multi-class classifications. 

**Binary Models**   
KNN binary classification and logistic regression are fit to maximize F1 score.

**Multi-Class Models**   
KNN and random forest multi-class classification are fit to maximize macro-averaged F1 score.

## Installation and Setup

### Codes and Resources Used

  - **Editor Used**: Visual Studio Code  
  - **Python Version**: 3.10.9

### Python Packages Used

  - **General Purpose**: numpy  
  - **Data Manipulation**: pandas  
  - **Data Visualization**: matplotlib, seaborn  
  - **Machine Learning**: imblearn, sklearn  

## Data

### Data Files
**Features**
  * *gender*: customer's gender  
  * *age*: customer's age    
  * *salary*: customer's yearly income  
  * *family_members*: number of additional members in the family  
  
**Targets**
  * *insurance_benefits*: number of benefits used  
  * *received_benefits*: whether customer received benefits or not
 
### Data Acquisition

The data were provided by TripleTen's Data Science bootcamp. The full dataset is loaded into the notebook but is proprietary information and cannot be shared online.

### Data Preprocessing

Data were checked for missing values and duplicates. None were found and no imputation was necessary.
 
## Code Structure
```
  ├── LICENSE
  ├── README.md          
  │
  ├── images
  │   └── insurance_clipart.png    
  │
  └── notebooks  
      └── insurance_analysis.ipynb  
```

## Results and Evaluation

### Exploratory Analysis
 
<p align="left">
  <img src="/images/insurance-benefits/eda.png"
  width="600"
  height="600"
  alt="sns pair plot of variables colored by receiving benefits">
</p>

There is clustering in insurance benefits by age.

### Binary Classification


<p align="left">
  <img src="/images/insurance-benefits/binary_results.png" 
  width="500"
  height="250"
  alt="Results of binary classification model tuning">
</p>

The best binary classifier is a logistic regression with threshold optimized to 0.43. This model achieved an F1, ROC AUC, accuracy, precision, and recall of 1.0 on the cross-validated training data.

<p align="left">
  <img src="/images/insurance-benefits/binary_test.png"
  width="310"
  height="90"
  alt="Test results of logistic regression with threshold = 0.43">
</p>

On the test set, the logistic regression with threshold = 0.43 again achieved scores of 1.0 across the board. This model is a perfect predictor of whether a person will use insurance benefits or not.

### Multi-Class Classification

<p align="left">
  <img src="/images/insurance-benefits/multi_results.png"
  width="690"
  height="250"
  alt="Results of multi class classification model tuning">
</p>

The random forest model with SMOTEENN balanced and weighted classes achieved the best multi-class classification results, scoring a macro-averaged F1 score of 0.9894.

<p align="left">
  <img src="/images/insurance-benefits/multi_test.png"
  width="510"
  height="100"
  alt="Test results of random forest multi class classification">
</p>

The random forest model with SMOTEENN and class weighting achieved similar results on the test set, achieving an F1 macro of 0.9764. This is a well fitting model and can be trusted to predict how many benefits a customer will use.

## Conclusions

Both models proved to be excellent predictors of the benefits a customer will receive based on their gender, age, income, and family size. Sure Tomorrow can feel confident putting this models into practice to predict numbers of benefits new customers are expected to use. They can use these models to set accurate premiums and maximums for customers, based on their expected use.

[View Project on Github](https://github.com/kellyshreeve/predicting-insurance-benefits)