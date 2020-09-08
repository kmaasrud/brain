**Ridge regression** penalizes the size of the regression coefficients, and thus shrinks them. Like in [[Ordinary least squares regression|OLS regression]], the [[Cost function|cost function]] is an [[Residual sum of squares|RSS function]], but this time with an extra term pertaining to this shrinkage:

$$ \text{RSS}(\beta,\lambda) = \sum_{i=1}^N (y_i - \hat y_i)^2 + \lambda \sum_{j=1}^p\beta_j^2 ,$$

$$ \text{RSS}(\beta, \lambda) = (\mathbf y - \mathbf X\beta)^T(\mathbf y - \mathbf X\beta) + \lambda \beta^T\beta $$

Here, $\lambda \ge 0$ is a parameter that controls how much the $\beta$'s are shrunk'; the greater the $\lambda$, the more shrinkage. The *Ridge [[Estimator|estimator]]* is of course now

$$ \hat \beta^{\text{ridge}} = \underset{\beta}{\arg \min}\ \text{RSS}(\beta,\lambda) .$$

Like explained in the [[Ordinary differential equation|page about OLS]], the above minimization problem can be written on matrix form as

$$ \hat \beta^{\text{ridge}} = (\mathbf X^T\mathbf X + \lambda \mathbf I)^{-1}\mathbf X^T\mathbf y ,$$

where $\mathbf I$ is the $p\times p$ identity matrix. Notice that when adding a positive constant to the diagonal (or *ridge* 😉), the matrix inside the parentheses will always be [[Invertibility|invertible]]. 