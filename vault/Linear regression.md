A **linear regression model** assumes that the regression function is linear in the inputs. Namely, for a system with $n$ datapoints and $p$ parameters, it can be represented by this matrix equation

$$ \mathbf y = \mathbf X\mathbf \beta + \mathbf \epsilon ,$$

where $\mathbf X$ is the $n\times p$ input matrix, $\mathbf y$ is the output vector, $\mathbf \beta$ is the vector of regression coefficients and $\mathbf \epsilon$ contains the errors.

Some methods of linear regression I've written about:

- [[Ordinary least squares regression]]
- [[Lasso regression]]
- [[Ridge regression]]
- [[Principal components regression]]