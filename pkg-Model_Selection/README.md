# best-feature 
### Model Name: best_feature
### Version: 0.1.1
### Author: SeungHeon Han
### email: seung225@gwu.edu
### Description:
* best_feature is the Python package that helps users to select the best features as a model selection tool. the package is designed for the model with a numeric target varible such as a linear regression model. One of the deployed modules is Best Subset Selection method that considers every possible combination of the features employed for a model. The best set of features are selected based on the smallest Mean Squared Error(MSE) computed by a k-fold cross validation. the Best Subset Selection module supports more measurements beyond MSE, which are AIC, BIC, and adjR2. It detects the most optimal model by finding the sets of features generating the lowest AIC, BIC, or adjusted-R2. This approach doesn't incorporate any cross validation, so, it remarkably reduces the processing time. As an alternative of the Best Subset Selection, the package offers Forward-Stepwise Selection that selectively chooses the candidate features in the process. When increasing the number of the candidate variables, it includes only the feature with the smallest loss function (MSE). Forward-Stepwise Selection can efficiently identify the best model reducing running time but cannot take every possible model into account like Best Subset Selection. 

