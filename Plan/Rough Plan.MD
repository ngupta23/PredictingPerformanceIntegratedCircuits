## Week 1 (9th - 16th)
 - Introduction (send for approval) [Nikhil]
 - [Option 1] Feature Engineering (Basic with only interaction terms) [Max]
 - [Option 2] Export grouping from R (dataset with group variable so it can be used in SAS) [Max]
 
## Week 2 and 3 (17th - 31st)
### [Option 1] PCR with Basic Feature Engineering - 2 way interactions of all variables. [Max]
     1. PCA is working. However, feature selection (Forward, Backward, Stepwise running for over 1 week and still not done).
     2. LASSO and LARS are running.
     3. Full Model is giving very good residuals (normal, no skew as before), but we dont know if it is overfitting 
     4. Need to check with Test set if it is really overfitting [Max]
     5. LARS and LASSO runs, but results (residuals) are not good)
 
 ### [Option 1] PCR with Advanced Feature Engineering (more advanced feature engineering with domain expertise) [Nikhil]
     1. PCA with original variables (no interaction): Since original variables were not correlated, we saw slow rise for the scree plot (i.e. many PCA's were needed to explain 80% variability)
     2. With 2 way interactions (with original variables), ~3800 PCA's explain 80% of variance 
     3. With Domain specific feature engineered terms and 2 way interaction of only x terms
         - Number of PCAs to explain 90% variability is only 164 . Results of full model not as good as the one obtained above with 2 way interaction of all variables (including statistical variables).
         - Correlation between output and feature engineered varaibles is more compared to with just original variables
         - Scatter plots show fan shaped plots (could this be a problem?) 
         - Try 3 way interaction of x terms [Nikhil] 
         - Full 2 way interactins with domain specific features + LASSO/LARS (no forward/backwatd/stepwise) [Nikhil] 
         - Include scatterplots of y3 with PCA [Max for 2 way with original variabels, Nikhil with 2 way with domain specific features]
           
 ### [Option 2] Perform LDA/QDA/Bayesian to find grouping [Joanna]
     1. Rerun with mutually exclusive train test sets [Joanna]
     2. Run Logistic regression on the data instead of LDA/QDA (NEW) [Joanna]
     3. Train LM model with grouping variable (+ interactions) [Joanna] 
         - Since we are short of time, keep as next steps in paper, i.e. create a pipeline of models with Logistic Regression output being used as a feature for linear regression)
 
## Week 4 (1st - 7th)
 - **Prepare Paper and Presentation** [All]
     1. Nikhil to add outline of paper/presentation (before Sat April 6th)
     2. Joanna to start filling details (before Sat April 6th)
     3. Meet Sat/Sun to finalize paper/presentation 


------------------------------------------------------------------

**Original Draft Outline**

[Option 1]
PCR with intelligent feature engineering 
 
[Option 2]
High Cook's D clustering
    - We dont know ahead of time which points belong to high Cook's D unless
    - We could label the points as High Cook's D (HCD) or Low Cook's D (LCD) after running 
 the linear regression
     - Perform LDA/QDA/Logistic Regression to train model to predict the right group for a point
     - Add predicted group as feature (factor) + its interaction term (with what variables?)
 for LM model for predicting y3
 
 OR Train LM model for each group separately to predict y3 
 (but we only have 288 points for HCD group, could be increased by lowering HCD threshold)
 
 Prediction
     - incoming data point >> pass through LDA/QDA/Logistic Regression Model to predict the group
     - Use the LM model for the predicted group to predict the output variable y3
