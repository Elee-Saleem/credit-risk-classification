# Module 12 Report Template

## Overview of the Analysis

  In this section, I describe the analysis I completed for the machine learning models used in this Challenge. This might include:

  * ### The purpose of the analysis:
    To teach computer how to apply rules to data in order to figure out which "healthy loans", "high risk loans" are.

  * ### Financial information the data was on, and what I needed to predict.
    - Financial information the data was on borrowers informations with their "loan status", "loan size",	"interest rate",	"borrower income",	"debt to income",	"number of accounts",	"derogatory marks",	"total debt".
    - What I needed to predict is "loan status" per other borrower's data given to the machine.

  * ### Basic information about the variables I was trying to predict:
    I was trying to predict "loan status" per other borrower's information.
    So I found out that "loan status" for healthy loans `0` = 75036 which is the majority out of 77536 of total records, whenever high risk loans records are the minority with only 2500 records.


  * ### The stages of the machine learning process I went through:
    1. Saperating the target column (the column needed to be learned and redicted) from the whole dataframe.
    2. Creating a varible for the rest of data (without that target).
    3. Then I applied train-test-split process in order to get training and testing data for both the target and the rest of data.
    4. Then Logistic Regression process and fitting it on training data to be trained so that it can predict with testing data of the rest testing dataframe (without traget test).
    5. Then from there I've got:
        * Balanced Accuracy Score off target testing data with testing predictions data.
        * Confusion Matrix of target testing data with testing predictions data.
        * Classification Report of target testing data with testing predictions data.

  * ### Methods I used:
    - In this case I used Logistic Regression since the target column (that's needed to be learned and predicted) is dicrete I mean its categorical.
    - After getting results of Classification Report I noticed that the machine is not predicting the minority data (which here is "high risk loans") that good enough (f1-score not in range of 95-90%) so I used Over Sampling method which was fitted with training data to get splitted oversampled data that was later Logistically Regressed and fitted.
    - After fitting we were able to predict with the testing data of the rest of data frame, hoping that we would get better results ( Balanced Accuracy Score, Confusion Matrix, and Classification Report).
    - So what oversampling did is that it got the classes equal or in other words we've got rid of imbalanced classes and made them balanced. What I mean by classes is groups so we have 2 groups here healthy loans and high-risk loans.


  ## Results

  The balanced accuracy scores and the precision and recall scores of all machine learning models:

  * Machine Learning Model 1:
    * Description of Model 1 Accuracy, Precision, and Recall scores:
       1. Accuracy :<br> 
          Accuracy is the number of correct predictions / total number of predictions, so we can evaluate the performance of a model at prdicting the target. 94.4% it should be a good percentage.
        2. Precision:<br>
          Precision is the number of correctly predicted instances of that class or group / totals number of predictions of that class or group. so it shows how accurate the model is at predicting a certain group or class, and we notice here that it predicted healthy loans AKA class `0` perfectly at 100%, although it wasn't that excellent at predicting high-risk loans AKA class `1` but 87% is consider good.
        3. Recall:<br>
          Recall tells us how the model is able to identify true positives of the total instances, and we notice here that it identified healthy loans AKA class `0` perfectly at 100%, although it wasn't that excellent at identifying high-risk loans AKA class `1` but 89% is considered a good value.



  * Machine Learning Model 2:
    * Description of Model 2 Accuracy, Precision, and Recall scores:
       1. Accuracy :<br> 
          With the 2nd model accuracy has improved, so we've got 99.6% this is a very good ratio.
        2. Precision:<br>
          We notice here that it predicted healthy loans AKA class `0` perfectly at 100%, but it has not improved or changed the model at predicting high-risk loans AKA class `1` it stayed the same at 87% and it is consider good.
        3. Recall:<br>
          Recall with the 2nd model has improved for high-risk loans AKA class `1` so now it's at 100% so it went up by +11%.

## Summary

Summary of the results of the machine learning models:

* Which one seems to perform best? How do you know it performs best?
    - The 2nd model performs better because it has got better numbers so f1-score (which combines precision and recall into a single value. It provides a balanced assessment of a model's performance, F1-score will be closer to the smaller of the two values (precision or recall)) with 2nd model is at 93% whenever f1-score for the 1st model came at 88%.
    

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
    - Yes it does, the problem we have is more important to find out unhealthy or high-risk loans `1` since the bankers are more conservatives and doubtful of risky loans whenever it's not a big deal of missing healthy ones`0`.
