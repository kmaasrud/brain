**Test error**, or **generalization error**, is the prediction error over an independent test sample:

$$ \text{Err}_{\mathcal T} = \text E[L(Y, \hat f(X))|\mathcal T] ,$$

where both $X$ and $Y$ are drawn randomly from their joint distribution, and $L$ is the [[Loss function|loss function]]. Here the training set $\mathcal T$ is fixed, and test error refers to the error for this specific training set. The **expected  test error** is

$$ \text{Err} = \text E[L(Y, \hat f(X))] = \text E[\text{Err}_{\mathcal T}] $$