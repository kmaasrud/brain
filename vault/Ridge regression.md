**Ridge regression** is a [[Linear regression|regression]] method based on reducing the size of the regression coefficients, and thus increasing the [[Bias of estimators|bias]] of the model.

Like in [[Ordinary least squares regression|OLS regression]], the [[Cost function|cost function]] is an [[Residual sum of squares|RSS function]], but this time with an extra term pertaining to the shrinkage of each regression coefficient:

$$ S(\beta,\lambda) = \text{RSS}(\beta) + \lambda \sum_{j=1}^p\beta_j^2 = \sum_{i=1}^N (y_i - \hat y_i)^2 + \lambda \sum_{j=1}^p\beta_j^2 ,$$

$$ S(\beta, \lambda) = (\mathbf y - \mathbf X\beta)^T(\mathbf y - \mathbf X\beta) + \lambda \beta^T\beta $$

Here, $\lambda \ge 0$ is a parameter that controls how much the $\beta$'s are shrunk'; the greater the $\lambda$, the more shrinkage. The *Ridge [[Estimator|estimator]]* is of course now

$$ \hat \beta^{\text{ridge}} = \underset{\beta}{\arg \min}\ S(\beta,\lambda) .$$

Like explained in the [[Ordinary least squares regression|page about OLS]], the above minimization problem can be written on matrix form as [^closed-form]

$$ \hat \beta^{\text{ridge}} = (\mathbf X^T\mathbf X + \lambda \mathbf I)^{-1}\mathbf X^T\mathbf y ,$$

where $\mathbf I$ is the $p\times p$ identity matrix. Notice that when adding a positive constant to the diagonal (or *ridge* 😉), the matrix inside the parentheses will always be [[Invertibility|invertible]]. This was one of the main motivating factors for Ridge regression. Its also worth noting that with [[Orthonormality|orthonormal]] inputs, Ridgre regression is just a scaled version of the [[Ordinary least squares regression|least squares regression]], $\hat \beta^{\text{ridge}} = \frac{1}{1 + \lambda}\hat \beta$.

Now what is the whole idea behind shrinking the regression coefficients? Well, its quite clear that when $\lambda = 0$ the [[Degree of freedom|degrees of freedom]] of the fit is $\text{df}(\lambda) = p$, since this is the number of parameters. However, as $\lambda \rightarrow \infty$, then also $\text{df}(\lambda) \rightarrow 0$, since we gradually reduce the influence the different parameters have on the fit. So the goal is essentially to reduce the influence of unimportant parameters, and thus reduce [[Overfitting|overfitting]]. This ties directly in with reducing the [[Variance|variance]] by increasing the [[Bias of estimators|bias]], following the [[Bias-variance tradeoff]].

[^closed-form]: The Ridge regressor can be expressed in a [[Closed-form expression|closed-form expression]], but for other regression methods, this might not be the case. Therefore, here is a more general formula:

	$$ \hat \beta^{\text{ridge}} = \underset{\beta}{\arg \min} \begin{Bmatrix}\sum_{i=1}^N\left(y_i - \beta_0 - \sum_{j=1}^p x_{ij}\beta_j\right)^2 + \lambda \sum_{j=1}^p \beta_j^2 \end{Bmatrix} .$$