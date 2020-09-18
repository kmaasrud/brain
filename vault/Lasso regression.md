The **Lasso** is a [[Linear regression|regression]] method expressed as,

$$ \hat \beta^{\text{lasso}} = \underset{\beta}{\arg \min} \begin{Bmatrix}\sum_{i=1}^N\left(y_i - \beta_0 - \sum_{j=1}^p x_{ij}\beta_j\right)^2 + \lambda \sum_{j=1}^p |\beta_j| \end{Bmatrix} .$$

Notice the similarity to [[Ridge regression]], the difference being the penalty. The ridge penalty $L_2 \equiv \sum_{j=1}^p\beta_j^2$ is replaced by the Lasso penalty $L_1 \equiv \sum_{j=1}^p |\beta_j|$. There's also a difference in that the Lasso regressor has no closed form expression, and must thus be computed programatically.