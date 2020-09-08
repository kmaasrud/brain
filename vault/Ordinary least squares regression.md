**Ordinary least squares** (OLS) is a method of estimating the parameters in a [[Linear regression|linear regression]] model. 

We have a dataset of $n$ observations $(y_i, \mathbf x_i)$, where $\mathbf x_i$ are the column vectors of length $p$ containing the parameters and $y_i$ are the scalar responses. We set up the linear function for the $i$'th case as

$$ y_i = \beta_1 x_{i1} + \beta_2 x_{i2} + \dots + \beta_p x_{ip} + \epsilon_i,$$

$$ y_i = \mathbf x^T_i\beta + \epsilon_i .$$

Here $\beta$ is an unknown $p\times 1$ vector and $\epsilon_i$ is the error of the model in the $i$'th case. So for all $i$ cases, we write the total equation on matrix form as

$$ \mathbf y = \mathbf X\mathbf \beta + \mathbf \epsilon ,$$

with $\mathbf X$ being an $n\times p$ matrix, often called the *[[Design matrix|design matrix]]* or *matrix of regressors*. It's worth noting that - contrary to what on might've thought - the $i$'th **row** of $\mathbf X$ equals $\mathbf x_i^T$. Also, the constant term is included in our equation by setting $x_{i1} = 1\ \forall\ i=1,\dots, n$.

Now because of the errors, $\mathbf y = \mathbf X\mathbf \beta$ does not have a unique solution. However, we can find the best fit by finding the vector $\hat \beta$ that minimizes some sort of [[Cost function|cost function]],

$$ \hat \beta = \underset{\beta}{\arg \min} S(\beta) .$$

$\hat \beta$ will give us an estimate of $\mathbf y$, namely $\hat{\mathbf y} = \mathbf X \hat \beta$.

In the case of OLS, the [[Cost function|cost function]] we use is the [[Residual sum of squares|residual sum of squares (RSS) function]]:

$$ \text{RSS}(\beta) = \sum_{i=1}^N \left(y_i - \hat y_i\right)^2 .$$

Changing into matrix notation again, we get

$$ \text{RSS}(\beta) = (\mathbf y - \hat{\mathbf y})^T(\mathbf y - \hat{\mathbf y}) = (\mathbf y  - \mathbf X\beta)^T(\mathbf y - \mathbf X\beta) ,$$

which we can differentiate with respect to $\beta$ to find the minimum.

$$ \frac{\partial \text{RSS}}{\partial \beta} = -2\mathbf X^T (\mathbf y - \mathbf X\beta) .$$

Assuming [[Rank (linear algebra)|full column rank]] for $\mathbf X$, $(\mathbf X^T \mathbf X)$ is thus [[Positive definite|positive definite]] (and importantly, [[Invertibility|invertible]]). Setting the first derivative to $0$, we get

$$ \mathbf X^T(\mathbf y - \mathbf X\beta) = 0$$

$$\Rightarrow \hat \beta = (\mathbf X^T\mathbf X)^{-1}\mathbf X^T \mathbf y $$