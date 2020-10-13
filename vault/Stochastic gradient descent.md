**Stochastic gradient descen** or **SDG** is a special form of [[Gradient descent|gradient descent]] designed to increase numerical efficiency over the regular method. It considers the [[Cost function|cost function]] $C$, described by the parameter $w$ we wish to optimize. It is typically defined over all observations in the ([[Training set|training]]) dataset

$$C(w) = \frac{1}{N}\sum_{i=1}^N C_i(w),$$

where $C_i$ is the cost associated with the $i$'th observation. Regular [[Gradient descent|gradient descent]] would calculate the gradient over all these observations before taking a step,

$$w = w - \eta \nabla C(w) = w - \frac{\eta}{N}\sum_{i=1}^N \nabla C_i(w).$$

Stochastic gradient descent changes this recipe by taking a step towards optimizing $w$ for each observation, randomly ordered. This is more easily described stepwise:

- Start with an initial value of $w$ and the stepsize $\eta$.
- Repeat the following until the desired minimum is achieved (when the value of $w$ [[Convergence|converges]]):
	- Randomly shuffle the [[Training set|training set]].
	- For each observation $i$, do:
		- $w= w - \eta\nabla C_i(w)$
		
		
Sources:
- [Wikipedia](https://en.wikipedia.org/wiki/Stochastic_gradient_descent)