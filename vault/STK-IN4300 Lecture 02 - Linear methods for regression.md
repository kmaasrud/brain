([[Riccardo De Bin|Riccardo's]] lectures are kind of a joke, I'll take my own notes from the [book](https://web.stanford.edu/%7Ehastie/Papers/ESLII.pdf))

***

## Linear methods of regression

A [[Linear regression|linear regression]] model assumes that the regression function $E(Y|X)$ is linear in the inputs. 

Assume an input vector $X^T = (X_1, X_2, \dots, X_p)$, where we want to predict an output $Y$. If we know that the output should take a linear form or that this is a reasonable approximation, we can use linear regression. The [[Linear regression|linear regression model]] has the form

$$ f(X) = \beta_0 + \sum^p_{j=1}X_j\beta_j ,$$

where the $\beta_j$'s are unknown coefficients or parameters.

Typically, we have a set of training data $(x_1,y_1),\dots, (x_N,y_N)$, where the $x_i = (x_{i1}, x_{i2},\dots, x_{ip})^T$ elements are vectors containing all the feature measurements for the $i$th case. A common method of estimating the regression function is **[[Least squares|least squares]]**. Here we pick the $\beta$'s based on minimizing the [[Residual sum of squares|RSS function]]:

$$ \text{RSS}(\beta) = \sum_{i=1}^N \left(y_i - f(x_i)\right)^2 = \sum_{i=1}^N \left(y_i - \beta_0 - \sum^p_{j=1}x_{ij}\beta_j\right)^2, $$

where $\beta = (\beta_1, \beta_2, \dots, \beta_p)^T$ is the vector of all the coefficients.

Now how do we minimize this? Start by denoting an input matrix $\mathbf X$ (dimensionality $N\times p +1$), where each row is an input vector (with a 1 in the first position, to allow for constants in the model). $\mathbf y$ (dimensionality $N$) are all the outputs we have in our training set. Now the [[Residual sum of squares|RSS]] is

$$ \text{RSS}(\beta) = (\mathbf y  - \mathbf X\beta)^T(\mathbf y - \mathbf X\beta) ,$$

which we can differentiate with respect to $\beta$ to find the minimum.

$$ \frac{\partial \text{RSS}}{\partial \beta} = -2\mathbf X^T (\mathbf y - \mathbf X\beta) $$
$$ \frac{\partial^2\text{RSS}}{\partial \beta \partial \beta^T} = 2\mathbf X^T\mathbf X $$

For the moment, we assume that $\mathbf X$ has [[Rank (linear algebra)|full column rank]] and $\mathbf X^T \mathbf X$ is thus [[Positive definite|positive definite]] (and [[Invertibility|invertible]]). Setting the first derivative to $0$, we get

$$ \mathbf X^T(\mathbf y - \mathbf X\beta) = 0 \Rightarrow \hat \beta = (\mathbf X^T\mathbf X)^{-1}\mathbf X^T \mathbf y $$

and now we easiliy get the predicted values ($\hat y_i = f(x_i)$, gathered in the vector $\hat{\mathbf y}$) as

$$ \hat{\mathbf y} = \mathbf X\hat \beta = \mathbf X(\mathbf X^T\mathbf X)^{-1}\mathbf X^T \mathbf y = \mathbf H\mathbf y .$$

We often call $\mathbf H = \mathbf X(\mathbf X^T\mathbf X)^{-1}\mathbf X^T$ the *hat matrix*.

(There's more to this, but the book gets kinda technical, and I presume this level of detail will come naturally later)

## Subset selection

The estimates produced by [[Least squares|least squares]] are often not satisfactory, for two reasons:

- **Prediction accuracy**: [[Least squares|Least squares estimates]] often have small bias, but large [[Variance|variance]]. Shrinking coefficients or setting them equal zero can often improve the accuracy, by sacrificing some bias.
- **Interpretation**: We would often like to determine the subset of a large number of predictors that has the largest effect. Here, we sacrifice the smaller details to get a practical "bigger picture".

## Model assessment

### Bias, variance and model complexity

There is a balance to be struck in our model complexity, as seen by this graph from [[The Elements of Statistical Learning]]:

![[assets/Pasted image.png]]

*The light blue curves show the [[Training error|training error]] $\overline{\text{err}}$, while the light red curves show the [[Test error|conditional test error]] $\text{Err}_{\mathcal T}$ for $100$ training sets of size $50$ each, as the model complexity is increased. The solid curves show the [[Test error|expected test error]] $\text{Err}$ and the [[Training error|expected training error]] $E[\overline{\text{err}}]$.*

**[[Test error]]**, or **generalization error**, is the prediction error over an independent test sample:

$$ \text{Err}_{\mathcal T} = \text E[L(Y, \hat f(X))|\mathcal T] ,$$

where both $X$ and $Y$ are drawn randomly from their joint distribution. Here the training set $\mathcal T$ is fixed, and test error refers to the error for this specific training set. The **expected  test error** is

$$ \text{Err} = \text E[L(Y, \hat f(X))] = \text E[\text{Err}_{\mathcal T}] $$

**[[Training error]]** is the average loss over the training sample

$$ \overline{\text{err}} = \frac{1}{N} \sum_{i=1}^NL(y_i, \hat f(x_i)) .$$

### Model assessment and selection

Assume we have a *tuning parameter* or *parameters* $\alpha$, so that our predictions can be written $\hat f_\alpha(x)$. $\alpha$ varies the complexity of our model, and the goal is to find the complexity that minimizes our resulting error. There are two goals we have in mind:

- **[[Model selection]]**: Estimating the *performance* of different models in order to choose the best one.
- **[[Model assessment]]**: Having chosen a final model, estimating its *[[Test error|generalization error]]* on new data.

Now say we are in a situation where we have *a lot* of data. In this case it would be best practice to randomly separate this data in to three sets, roughly, but not strictly according to this distribution:

- 50% **Training set**: This set is used to fit the models
- 25% **Validation set**: This set is used to estimate the [[Test error|prediction error]] for *[[Model selection|model selection]]*.
- 25% **Test set**: This set is used for assessing the [[Test error|generalization error]] of the final chosen model.

The validation step can be tested either *analytically* ([[Akaike information criterion|AIC]], [[Bayesian information criterion|BIC]], MDL or SRM) or by *efficient sample re-use* ([[Cross-validation|cross-validation]] or [[Bootstrapping (statistics)|the bootstrap]]).

***

Meta:
- Course: [[STK-IN4300]]
- References: [The Elements of Statistical Mechanics](https://web.stanford.edu/%7Ehastie/Papers/ESLII.pdf)
- Date: [[daily/2020-08-24]]