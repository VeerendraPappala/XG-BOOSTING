This repository contains information about the xgboosting and the model bulit from the dataset(purchase)  taken from Kaggle Compitition.
 
 #### As the dataset is in larger file size to upload, following link  will directs to download it from drive.   https://drive.google.com/file/d/1Afh3BQ6i0jYvEqPOGXGdeekX675jfS6L/view?ts=5c0b5e0c 

# XG-BOOSTING

In the realm of data science, machine learning algorithms, and model building, the ultimate goal is to build the strongest predictive model while accounting for computational efficiency as well. This is where XGBoosting comes into play. XGBoost (eXtreme Gradient Boosting) is a direct application of Gradient Boosting for decision trees.

## Main advantages are as follows:
1. Easy to use
2. Computational efficiency
3. Model Accuracy
4. Feasibility — easy to tune parameters and modify objectives.

## Important parameters tuned in XG-Boosting are:
### 1. General Parameters: relates to which type of booster to used either linear or tree
  * booster (default = gbtree) Can be gbtree, gblinear or dart; gbtree and dart use tree based models while gblinear uses linear functions.
  * silent (default = 0)
  * nthread - Number of parallel threads used ti run XGboost.
### 2. Learning tank Parameters: relates to decide on the learning scenario
   #### * Objective ( default = reg:linear)
          * reg: linear - for  linear regression
          * reg:logistic - for logistic regression
          * binary:logistic: logistic regression for binary classification, output probability
          * binary:logitraw: logistic regression for binary classification, output score before logistic transformation
          *multi:softmax: set XGBoost to do multiclass classification using the softmax objective, you also need to set num_class(number of classes)
          * multi:softprob: same as softmax, but output a vector of ndata * nclass, which can be further reshaped to ndata * nclass matrix. The result contains predicted probability of each data point belonging to each class.
  #### * Eval metric: relates Evaluation metrics for validation data. users can relate to multiple eval metrics.
          * rmse - root mean square error
          * logloss - negative likelihood
          * Auc - Area under curve
          * error - binary class error
          * merror - multiclass error
          * mae - mean absolute error
          
 ### 3. Command line Parameters: relates to  Number of trees/rounds 
      * num_round : The number of rounds for boosting
      * data - The path of training data
      * test:data - The path of test data to do prediction
      * save_period [default=0] The period to save the model. Setting save_period=10 means that for every 10 rounds XGBoost will save the model

### 4. Tree/ Tuning Parameter: 
      * eta [default=0.3, alias: learning_rate]
      * gamma [default=0, alias: min_split_loss]
      * max_depth [default=6]
      * subsample [default=1]
      * colsample_bytree (range = [0,1] -  is the subsample ratio of columns when constructing each tree. Subsampling occurs once for every tree constructed.
      * colsample_bylevel is the subsample ratio of columns for each level.
      * scale_pos_weight [default=1] - to Control the balance of positive and negative weights, useful for unbalanced classes.     A typical value to consider: sum(negative instances) / sum(positive instances.
### 5. Regularization Parameters for linear booster:
      * lambda [default=0, alias: reg_lambda] - Increasing this value will make model more conservative. L2 regularization term on weights
      * alpha [default=0, alias: reg_alpha] - Increasing this value will make model more conservative.L1 regularization term on weights. 
      
### XGBoosting Documentaion - https://xgboost.readthedocs.io/en/latest/

