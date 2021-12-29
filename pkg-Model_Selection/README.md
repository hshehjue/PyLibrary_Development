# best-feature 
#### Model Name: *best_feature*
#### Version: *0.1.1*
#### Distributed: *https://pypi.org*
#### Distribution Date: 12/28/2021
#### Author: *SeungHeon Han*
#### Email: *seung225@gwu.edu*

#### Description:
* best_feature is the Python package that helps users to select the best features as a model selection tool. the package is designed for the model with a numeric target varible such as a linear regression model. One of the deployed modules is Best Subset Selection method that considers every possible combination of the features employed for a model. The best set of features are selected based on the smallest Mean Squared Error(MSE) computed by a k-fold cross validation. the Best Subset Selection module supports more measurements beyond MSE, which are AIC, BIC, and adjR2. It detects the most optimal model by finding the sets of features generating the lowest AIC, BIC, or adjusted-R2. This approach doesn't incorporate any cross validation, so, it remarkably reduces the processing time. As an alternative of the Best Subset Selection, the package offers Forward-Stepwise Selection that selectively chooses the candidate features in the process. When increasing the number of the candidate variables, it includes only the feature with the smallest loss function (MSE). Forward-Stepwise Selection can efficiently identify the best model reducing running time but cannot take every possible model into account like Best Subset Selection. 

#### Effects:
* Preventing model over & under-fitting
* Preventing features' Multiclonearity 
* Filtering out features with little contribution
#### Installation: *pip install best_feature*
#### Instruction for the use:
* **Pre-processing:** train set is only needed 
* **Caution:** 
  - train set is required to be partitioned into X train and y train ("sklearn.model_selection - train_test_split" recommended).
  - Every features in X train are all considered as the candidate models. If any redandunt variables included, drop them from X train set beforehand.
* **Best Subset Selection with MSE:**
  - Load Library
    - from best_feature.BestSubsetSelection import BestSubset
  - Define An Object
    - BSS = BestSubset(X_train, y_train)
  - Find the Best Model (k-fold CV)
    - BSS.BestModel(n_splits =, n_repeats =, random_state =)
      - If leave it empty, default parameters:
      - {n_splits = 5, n_repeats = 1, random_state = 123}
  - Attributes For the Results
    - BSS.feat_(): Displaying the selected features
    - BSS.index_(): Displaying the indices of the selected features
    - BSS.MSE_(): Displaying the average MSE of the selected model
    
* **Best Subset Selection with AIC, BIC, adjR2:**
  - Load Library
    - from best_feature.BestSubsetSelection import BestSubset
  - Define An Object
    - BSS = BestSubsetShort(X_train, y_train)
  - Find the Best Model (k-fold CV)
    - BSS.BestModel()
      - no parameters needed
  - Attributes For the Results
    - BSS.varAIC_: Displaying the best model selected based on min AIC
    - BSS.AIC_: Displaying the min AIC
    - BSS.indexAIC_: Displaying the indices of the best model selected based on min AIC
    
    - BSS.varBIC_: Displaying the best model selected based on min BIC
    - BSS.BIC_: Displaying the min BIC
    - BSS.indexBIC_: Displaying the indices of the best model selected based on min BIC
    
    - BSS.varadjR2_: Displaying the best model selected based on min adjR2
    - BSS.adjR2_: Displaying the min adjR2
    - BSS.indexadjR2_: Displaying the indices of the best model selected based on min adjR2

* **Forward-Stepwise Selection with MSE:**
  - Load Library
    - from best_feature.ForwardStepwiseSelection import ForwardStepwise
  - Define An Object
    - FSS = ForwardStepwise(X_train, y_train)
  - Find the Best Model (k-fold CV)
    - FSS.BestModel(n_splits =, n_repeats =, random_state =)
      - If leave it empty, default parameters:
      - {n_splits = 5, n_repeats = 1, random_state = 123}
  - Attributes For the Results
    - FSS.feat_(): Displaying the selected features
    - FSS.index_(): Displaying the indices of the selected features
    - FSS.MSE_(): Displaying the average MSE of the selected model




