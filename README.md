Overview: 
       A bank is trying to increase the number of customers who subscribe to it’s term deposit product. The marketing team is interested in utilizing it’s resources judiciously by targeting those customers who have high probability of subscribing.  There is historical data of the past campaigns along with the corresponding customer details existing with the bank.
Problem Statement: 
       Currently the effort to increase the number of subscribers to term deposit is random. The hit ratio is abysmal and the resources utilized is very high for very little gain. The marketing team requires help with identification of customers who have a higher chance of subscribing when contacted.
Goal Statement: 
       Using the data, collected from existing customers, build a model that will help the marketing team to identify potential customers who are relatively more likely to subscribe to the term deposit and thus increase their hit ratio. 
Approach:
Extensive experimentation with more than 10 different models was done to identify the best model that could predict customer behaviour so that the bank can take proactive steps to increase the number of subscriptions for the term deposit.
The data was slightly imbalanced (Majority class: Minority Class = 89:11) and hence appropriate model evaluation metric was required to be chosen. A combination of Harmonic mean (F1 score), Sensitivity and Area Under the Curve (AUC) was used to finalize the best model.
Models tried to arrive at the best are 
Simple Models like Logistic Regression  with different thresholds for classification
Decision Tree followed by various ensemble models were tried on the original dataset and the results compared
Since the data was imbalanced, minority oversampling was used to improve the ratio to 67:33. Then the linear and ensemble models were trained on the ‘minority class treated’ data.

Results:
Default classification achieved through Logistic regression  did not give satisfactory results as the recall (sensitivity/true positive rate) and F1-scores were too poor to proceed with the model. However when the thresholds were tuned (to 25%) the performance improved to a great extent  (recall=61% and F1-score=57%). This was better than any of the tree based models tried.
The tree based algorithms, on the original data, gave poor results in terms of recall (sensitivity/true positive rate) achieved. The results were poorer than the linear model (Logistic Regression) attempted.
The accuracy scores for the tree based models were better than logistic regression indicating the imbalance in target variable was impacting the performance of tree based models. The tree based models needed more examples of the minority class to learn better and generalize well on unseen data.
The recall and F1-scores for Decision tree and bagging algorithms were the worst indicating individual trees and correlated trees can give unstable/unreliable results. The ensemble models (with de-correlated trees)  generalize better .
When the class imbalance was treated by improving the ratio of Majority class: Minority class  to 67:33, all the tree based algorithms outperformed logistic regression results by a big margin indicating the relationship between X and Y was not linear and when the tree based algorithms were provided with adequate number of observations, the learning was robust.
With the balanced data random forest and stacked ensemble models gave the best results. 

