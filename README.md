# credit_assessor
Using supervised learning with imbalanced data sets to evaluate credit risk

## Overview of the Analysis

The purpose of the analyses that we performed in this project was to identify the credit worthiness of borrowers applying for loans.  In order to train our model and predict whether or not a loan had a high risk of default, we utilized a dataset that included the size of the loan requested, the interest rate of the loan, and the borrower's income, debt to income ratio, number of open accounts, derogatory marks, and total debt.  Our predictions result in a binary classification -- 0 for healthy loans and 1 for high-risk loans.  Our original dataset was highly imbalanced with value counts of approximately 75000 healthy loans and 2500 unhealthy loans, leading to the possibility that such skewed values would impact our model's ability to accurately predict especially the high-risk loans.  Our data was split into training and testing data using train_test_split. To address potential concerns of fitting our model to such imbalanced data, we initially fit our model to the original dataset and then to a newly generated oversampled and balanced one for comparative and analysis purposes.  We utilized the LogisticRegression module from scikit-learn on both of our models, but for our second model we used RandomOverSampler from imbalanced-learn to resample and balance our dataset values to see how it would affect the accuracy of our predictions. 
  

## Results


* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.

    * Accuracy -- The overall accuracy score for our first model was approximately 0.952, which is actually quite good for such an   imbalanced dataset.  Our model was able to predict the quality of the loan just over 95% of the time.
    
    * Precision -- The precision values for our first model were a perfect 1 for the quality loans and 0.85 for the high-risk loans.  This difference is not surprising given the imbalanced nature of the initial dataframe. These numbers mean if our model identified a loan as high quality, there is a 100% chance that it is accurate, while if it predicted that a loan was high risk there is an 85% chance it is accurate.
    
    * Recall -- Our recall scores for the first model were 0.99 for high quality loans and 0.91 for high-risk loans.  This indicates that our model will identify quality loans 99% of the time and high-risk loans 91% of the time.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  
      * Accuracy -- The overall accuracy score for our second model was approximately 0.9937, indicating a highly accurate model that accurately predicted the quality of the loan around 99.37% of the time.  
    
    * Precision -- The precision values for our second model were a perfect 1 for the quality loans and 0.84 for the high-risk loans.  These numbers mean if our model identified a loan as high quality, there is a 100% chance that it is accurate, while if it predicted that a loan was high risk there is an 84% chance it is accurate.  This is a somewhat surprising result, as the precision score on our second model actually went down slightly vs. our original model based on a far more imbalanced dataset.
    
    * Recall -- Our recall scores for the second model were 0.99 for high quality loans and 0.99 for high-risk loans.  This indicates that our model will identify quality loans 99% of the time and high-risk loans 99% of the time.  This is a substantial improvement over our original model's (+8%) ability to identify high-risk loans.


## Summary

Overall both models were highly accurate, with the most substantial improvement in our second model coming from an 8% increase in its ability to predict high-risk loans.  With a 0.99 recall score for our second model paired with a 0.84 precision score that was essentially identical to the first model, for the purposes of identifying high risk loans our second model would be extremely valuable.  If one were able to predict high-risk loans with such accuracy, they would be able to avoid making a risky loan almost 100% of the time.  While the model may improperly identify a loan as risky approx 15% of the time given the precision score, there would still be plenty of opportunities to extend high quality loans while avoiding nearly all loans that would end up being high risk.  The only concern I would have for both models is the fact that they both scored perfectly on precision for high quality loans, indicating the possibility that the models are overfit to the data we are basing this on.  Because of this possibility, I would recommend running our models on other testing data to ensure this is not the case.  If they prove to not be overfit, model two would be an excellent choice to assess and predict the quality of the loans requested.

