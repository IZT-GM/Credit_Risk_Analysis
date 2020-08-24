# Credit_Risk_Analysis
## Objective
______
Create machine leaning models to analyse a set of loans applications in order to define if a person is a high risk or a low risk applicant.
The models will have the performance compared and discussed.

## Analysis
_________
The original data was previously analysed, and it shows a large imbalance between the low-risk and the high-risk data (Original data counts: 'low_risk': 51366, 'high_risk': 246). The data then was re-evaluated using the following machine learning methods and models to overcome the imbalance.
-	Oversampling: To oversample the high-risk data to the same level as the low-risk. Data after been oversampled: 'low_risk': 51366, 'high_risk': 51366.
    *	RandomOverSampler
    *	SMOTE
-	Undersampling: To undersample the low-risk to the same level as the high-risk. Data after been undersampled: 'high_risk': 246, 'low_risk': 246
    *	RandomOverSampler
-	Combination (Over and Under) Sampling: First the data is oversampled with SMOTE and then the nearest points are undersampled. Data after been combined: 'high_risk': 68460, 'low_risk': 62011
    * SMOTEENN
## Results
_________________
The table below summarizes the accuracy score of each model:

|	|RandomOverSampler|SMOTE|RandomOverSampler|SMOTEENN|
|------|-----|------|-------|-------|
|Balanced Accuracy Score|0.66|0.66|0.54|0.64|
The oversampling models performed 0.02 points better than the combination and 0.12 points better and the unddersampling model.

Accuracy is good metric, however, a model can not be only evaluated based on its accuracy number.

The table below summarizes the precision and the recall of each model.
|	|RandomOverSampler|---  |SMOTE|--- |RandomOverSampler|--- |SMOTEENN|--- |
|------|-----|------|-------|-------|-------|-------|-------|-------|
|	     |pre |rec |pre |rec |pre |rec |pre |rec |
|high_risk|0.01|0.63|0.01|0.63|0.01|0.68|0.01|0.72|
|low_risk|1.00|0.69|1.00|0.69|1.00|0.41|1.00|0.57|
|avg / total|0.99|0.69|0.99|0.69|0.99|	0.41|0.99|0.57|


It’s possible to noticed that all models have the same precision and all models fail drastically to predict the high-risks, but it has a perfect precision to identify the low-risks. It means, as precision, the models would identify every person as a low-risk.

The good news is that there is one more component that can help evaluate the models. The recall or sensitivity. Where it measures, from all that were identified (as low-risk or high-risk), how many were correctly identified. 

In this case, the oversampling models had the best overall sensitivity, with 0.69. Which means that from the people identified as low-risk or high-risk, 69% would be accurate.

 ## Conclusion
 _______
Based on the results shown above, it doesn’t seem that any of these models are perfect and it may fall on the average side.

However, it should be wise to understand the risk of the business itself. Loans are definitely not on the safe side, and maybe a good enough model could improve revenue at a not-so-low-risk.
