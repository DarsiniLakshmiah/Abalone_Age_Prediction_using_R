# Abalone Age Prediction Using Machine Learning

## 1. Introduction

### Overview
The **Abalone Age Prediction** project aims to predict the age of abalones using physical and biological features, leveraging machine learning techniques to create accurate and interpretable models. The project addresses key challenges such as multicollinearity, heteroscedasticity, and influential data points. By implementing multiple linear regression and decision tree models, we explore data-driven approaches to automate age prediction, which traditionally requires time-consuming manual methods.

### Importance
Accurate age prediction is crucial for marine biologists and fisheries. Sustainable harvesting and conservation efforts depend on understanding the age distribution of abalone populations. This project contributes to the sustainable management of marine resources by automating age prediction.

---

## 2. Dataset Description

### Source
The dataset is obtained from the **UCI Machine Learning Repository**, containing **4,177 observations** and **9 features**.

### Features
- **Sex**: Categorical (F = Female, M = Male, I = Infant).
- **Length**: Continuous, longest shell measurement (in mm).
- **Diameter**: Continuous, perpendicular to length (in mm).
- **Height**: Continuous, shell height (in mm).
- **Whole_weight**: Continuous, whole abalone weight (in grams).
- **Shucked_weight**: Continuous, weight of meat (in grams).
- **Viscera_weight**: Continuous, gut weight after bleeding (in grams).
- **Shell_weight**: Continuous, shell weight after drying (in grams).
- **Rings**: Integer, number of shell rings (used to calculate age as `Age = Rings + 1.5`).

---

  ## 3. Objectives
- Develop predictive models to estimate abalone age.
- Address and resolve challenges such as:
  - Multicollinearity between predictors.
  - Heteroscedasticity in residuals.
  - Outliers and influential observations.
- Compare the performance of multiple machine learning models.

---

## 4. Methodology

### 4.1 Data Preprocessing
#### Data Cleaning
- Identified and handled missing or extreme values.
- Removed influential points using Cook’s Distance, leverage, and studentized residuals.

#### Feature Engineering
- Applied log transformations to stabilize variance and reduce skewness.
- Addressed multicollinearity using Variance Inflation Factor (VIF) analysis and removed redundant variables.

### 4.2 Model Development
#### 4.2.1 Multiple Linear Regression
- Built a baseline regression model with all predictors.
- Iteratively refined the model by addressing multicollinearity and heteroscedasticity.
- Evaluated model assumptions:
  - Residuals vs. fitted values for homoscedasticity.
  - Q-Q plot for normality of residuals.

#### 4.2.2 Log-Transformed Regression
- Applied log transformation to the dependent variable and predictors to improve model fit.
- Reassessed model assumptions post-transformation.

#### 4.2.3 Decision Tree Regression
- Built a decision tree model to explore non-linear relationships and interactions.
- Pruned the tree to prevent overfitting and improve generalization.
  

  ### 4.3 Model Evaluation
Metrics used for evaluation:
- **Root Mean Squared Error (RMSE)** for prediction accuracy.
- **R-Squared** for variance explained by the model.
- **Cross-validation (10-fold)** to ensure robustness.

---
## 5. Results

| Model                      | Train RMSE | Test RMSE | R-Squared |
|----------------------------|------------|-----------|-----------|
| Multiple Linear Regression | 2.18       | 2.23      | 0.52      |
| Log-Transformed Regression | 1.66       | 2.41      | 0.64      |
| Decision Tree              | 2.34       | 2.48      | 0.40      |
| Pruned Decision Tree       | 2.34       | 2.48      | 0.40      |

### Analysis of Results
- The **Log-Transformed Regression Model** demonstrated the best performance, explaining **64% of the variance** in the dependent variable.
- The **Multiple Linear Regression Model** had the lowest Test RMSE, indicating better generalization to unseen data.
- The **Decision Tree Models** provided lower predictive accuracy but revealed non-linear interactions.

