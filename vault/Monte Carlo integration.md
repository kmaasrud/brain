**Monte Carlo integration** is a way of evaluating an integral using the [[Monte Carlo method]] (using random numbers). The method generalizes well to higher dimensions and is thus computationally much more effective than many other numerical integration methods.

The simplest form of Monte Carlo integration evaluates the mean function value over a set of parameters randomly sampled within the interval, and multiplies it with said interval. For example, the simple one parameter integral $I = \int^5_{-2} f(x) = \int^5_{-2}(-x^3 + 6x^2 - x + 17)dx$ can be calculated with $6$ Monte Carlo cycles thusly:

![](https://miro.medium.com/max/700/1*D3cackc27gSRjS2LrjYKzQ.jpeg)

The mean value of the yellow areas represent the result of the Monte Carlo integration.

## Definition

Consider a multidimensional integral of the function $f$

$$I = \int_\Omega f(\mathbf x)d\mathbf x$$

in the domain $\Omega$. The domain has volume $V = \int_\Omega d\mathbf x$. Monte Carlo integration revolves around doing a set number ($N$) of samples $\mathbf x_1, ..., \mathbf x_N \in \Omega$ and approximating the integral as

$$I \approx M_I = \frac{V}{N}\sum_{i=1}^N f(\mathbf x_i).$$

When $N\rightarrow \infty$, the [[Law of large numbers|law of large numbers]] says that also $M_I \rightarrow I$.

The key here is how the parameters $\mathbf x_i$ are sampled. In the example above (the *crude Monte Carlo*), we simply sample from a [[Uniform distribution|uniform distribution]], but more complex (and more efficient) methods do what's called *importance sampling* in accordance with a [[Probability density function|PDF]].