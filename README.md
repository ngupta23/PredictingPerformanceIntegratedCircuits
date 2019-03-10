# MSDS-6372-Project2
Repo for SMU MSDS Applied Statistics (Spring 2019) Project 2

## Team
Joanna Duran, Nikhil Gupta, Max Moro

##	Problem Background: 
*	This project is a continuation of [Project 1](https://github.com/ngupta23/MSDS-6372-Project1/tree/master/Presentation) for this course. 
* From project 1, we identified a couple of improvements that can be made to the model fit. Specifically
    - Perform intelligent feature engineering and selection.
    - Cluster high Cook's D points and add those as a predictor variable to the model.
* In this project, we will act upon these ideas using the techniques learned in the second half of the course to see if we can improve the model fit

## Approach 1: Principal Component Regression with intelligent featuure selection
* In project 1, we realized that doing a brute force interaction of all the predictors would give us more than 28,000 predictors in the model which would not be practical to use.
* In this project, we will perform feature engineering to create new features (using the ones already available) and do intelligent interactions with a subset of the available predictors. 
* Both feature engineering and intelligent feature interaction will be done by taking domain expertise into account.  

## Approach 2: Clustering based on High Cook's D and using the clusrer as a predictor in the regression model
* We dont know ahead of time which points belong to high Cook's D. Hence in this approach, we will first label the points as High Cook's D or Low Cook's D observation after running a basic linear regression model.
* Using this label, we will perform LDA/QDA/Logistic Regression to train a model to predict the right group for a new observation
 * Finally, we will add the predicted group (from LDA/QDA/Logistic Regression) as a feature into the linear model for predicting the value of the output variable.
 * In a way this is a 2 step machine learning model - first cluster the incoming observation into clusters and then use the cluster information as a predictor in the final model to improve its fit.
  
## Dataset
* Description can be found in Project 1: https://github.com/ngupta23/MSDS-6372-Project1/blob/master/README.md 

## Files
* Description can be found in Project 1: https://github.com/ngupta23/MSDS-6372-Project1/blob/master/README.md
  
## Goals:
* Improve the model fit from Project 1 utilizing the concepts learned in the second half od the course, specifically
  - Principal Component Regression
  - Linear/Quadratic Discriminate Analysis
  - (Time Permitting) Logistic Regression
  
## Sponsor
* Data has been sponsored and approved for use by Texas Instruments Inc. 


