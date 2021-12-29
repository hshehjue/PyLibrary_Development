# Instruction how to use model selection package
## Section telling how to install the modules 
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




