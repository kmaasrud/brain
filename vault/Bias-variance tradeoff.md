![](https://miro.medium.com/max/738/1*wqDhhG2BjkBCl5WuHojddw.png)

The **bias-variance tradeoff** is the property where a predictive model with a *low [[Bias of estimators|bias]]* has a *higher [[Variance|variance]]* and vice versa. 

- High [[Bias of estimators|bias]] can cause a model to miss important relations between features and target outputs.
- High [[Variance|variance]] can lead to the random noise of the [[Training set|training set]] to be modeled, namely [[Overfitting|overfitting]]. This, in turn, will likely lead to greater errors when introduced to [[Training set|new data]].

An often used simplification of this tradeoff reads:

> Bias is related with a model failing to fit the training set and variance is related with a model failing to fit the testing set.