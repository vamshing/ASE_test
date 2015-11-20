## Learning Model for the Holland America Data-set
**Author:** Guduguntla Vamsi
| email: gudugu@ncsu.edu
| date: 20 Nov 2015

#### 1.Abstract
The aim of this paper is to develop a predictive model for the prediction of cancelling of the booking.The model is developed by first screening out the unimportant variables from the given variable set (~23 variables) to discover which covariates have the most predictive power from the set. The predictive model is proposed, based on the tournament of classification algorithms their performances are compared using k-fold cross-validation technique.

#### 2.Methods

**3.1.Screening of predictors**
The data has around 23 covariates trying to explain booking status (~2200 observations). I have employed the screening by making use of Random Forest method.. Therefore, screening out the variables which showed little or no effect on Cancellation .By looking at the predictors qualifying in the > 10% bracket are chosen to be the ones with highest predictive power from the remaining batch.

**3.2.Tournament of Classifiers**
I have ran a tournament of classifiers to see which gave the best predictive power.Adaboost,Gradientboost,logistic regression,SVM's and Random Forests are chosen for the study.

**3.3 k - fold cross validation**

In practice, I have used 10 fold cross-validation based on the elbow curve to avoid over-fitting. The accuracy of the classifier is used to determine the best classifier.


**3.4 Random Forests**

Random forests are a combination of tree predictors such that each tree depends on the values of a random vector sampled independently and with the same distribution for all trees in the forest.Random forests are an effective tool in prediction. Because of the Law of Large Numbers they do not overfit. Injecting the right kind of randomness makes them accurate regressors.

#### 4.Results:
**Important Features**
Using the above mentioned techniques, some of the important features are as given below. 

![screen shot 2015-11-20 at 5 48 30 pm](https://cloud.githubusercontent.com/assets/10588000/11313930/f31b3d8e-8fae-11e5-9dd7-5e4a7cb6221d.png)

**Tournament of Classifiers - Results**

```
{'RandomForest': 0.904, 'Support Vector Machines': 0.832, 'Gradientboost': 0.88, 'Adaboost': 0.812, 'Logistic': 0.782}
```

So, we pick RandomForest (90.4%) accurate for classification

#### Question 2

What kind of people book suites (meta in ('S','D')) (Active bookings only)?

```
223 Bookings in 60%-40% (Suite-Deluxe Suite)

- All US Nationals 
- with Median age 59
- 30% of them have been in the cruise before atleast once
- who booked 180 days(6 months) in advance on an average
- 92 % of them did not book air with us
- 76% of them booked through an agency
- equally proportion of males and females
- more than half opted for "Your time Dining"
- Only 25% of them having insurance
- Mean Revenue per booking is $302
```
