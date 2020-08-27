## Preliminary

(**Note**: This lecture uses indices starting at $0$)

(We will normally split our data in training data and test data)

Recall: [[Machine learning]] has three important elements:

- The data set
- The model
- The cost/error/loss function

## [[Linear regression]]

### Data set

We have a data set, which contains some variables $(y,x)$. $x$ we call the *input* and $y$ we call the *output* or *target*. The general assumption we make is:

$$ y(x) = f(x) + N(0, \sigma^2) ,$$

where $N$ is a [[Probability density function|PDF]] ([[Normal distribution]]), where $\mu = 0$ and we have a variance $\sigma^2$. Then we assume this [[Probability density function|PDF]] $P(x)$ is known and [[Continuity|continuous]], then our mean value is defined:

$$\sigma = \int dx x P(x),$$

However, in our case, $P(x)$ is often unkown. [[Machine learning]] is a [[Frequentist approach|frequentist approach]] to this.

$$ (y,x)\rightarrow x= \begin{matrix}\{x_0,x_1,...,x_{n-1}\} \\ \{y_0,y_1,...,y_{n-1}\}\end{matrix} $$

The mean value we estimate:

$$ \mu_y = \frac{1}{n}\sum_{i=0}^{n-1}y_i $$
$$ \mu_y \ne \mu $$

So $\mu_y$ is not the exact mean, but the **[[Sample mean|sample mean]]**.

***

$$ \sigma^2 = \int (x-\mu)^2 P(x) dx ,$$

the true [[Variance]]. However, we have to live with the **[[Sample variance|sample variance]]**.

$$ \sigma_x^2 = \frac{1}{n}\sum_{i=0}^{n-1}(x_i \mu_x)^2 $$
$$\sigma_x^2 \ne \sigma^2$$

(when [[Morten Hjorth-Jensen|Morten]] puts a subscript to the variance or mean, he is talking about the sampled version)

***

So now back to the function $f(x)$, which is the function we seek. It can be approximated

$$ f(x) \simeq \tilde y(x) $$

We discretize

$$ y(x) \rightarrow y(x_i) = y_i $$
$$ y(x_i) \simeq \tilde y_i $$
$$ \epsilon_i \sim N(0,\sigma^2) $$

Now we need to make a **model**

### Model

We have some data points, which we hope to match linearly

$$ \tilde y_i = \tilde y_i(x_i) = \beta_0 + \beta_1 x_i $$
$$ \mathbf{\beta} = \{\beta_0, \beta_1\} $$

How can we find $\beta$, so that the distance between $y$ (target) and $\tilde y$ is as small as possible?

### Cost function

(When you see $y - \tilde y$, this equals $\sum_{i=0}^{n-1} (y_i - \tilde y_i$)

We have the [[Mean squared error|mean squared error (MSE)]]:

$$ \text{MSE} = \frac{1}{n}\sum_{i=0}^{n-1}(y_i - \tilde y_i) = C(\mathbf{\beta}|x) $$

or [[Cost function]] (which [[Morten Hjorth-Jensen|Morten]] will write as $C(\mathbf{\beta})$ from now on).

We seek an optimal $\hat \beta = \text{argmin}_{\beta} C(\mathbf{\beta}1|x)$.

We can rewrite the [[Cost function]] ([[Morten Hjorth-Jensen|Morten's]] slides of this [here](https://compphysics.github.io/MachineLearning/doc/pub/Regression/html/Regression.html#___sec12))

$$ C(\mathbf{\beta}) = \frac{1}{n}\left[\left(\mathbf y - \mathbf{\tilde y}\right)^T \left(\mathbf y -\mathbf{\tilde y}\right)\right] $$

We want to minimize the spread of $C(\beta)$, which in practical terms means we require:

$$ \frac{\partial C(\mathbf \beta)}{\partial \beta_j} = ... = 0 $$

$$ \frac{\partial C(\mathbf \beta)}{\partial \beta_j} = 0 = \mathbf X^T (\mathbf y - \mathbf X \mathbf \beta) $$

which can be rewritten into

$$ \mathbf X^T \mathbf y = \mathbf X^T \mathbf X \mathbf \beta .$$

If the matrix $\mathbf X^T \mathbf X$ is [[Invertibility|invertible]], we have our solution, namely:

$$ \mathbf \beta = \left(\mathbf X^T \mathbf X\right)^{-1} \mathbf X^T \mathbf y $$

## Practical application

From `sklearn.linear_model` we can import `LinearRegression` which contains the handy function `fit`.

(Hopefully, [[Morten Hjorth-Jensen|Morten]] will go more into this)

***

Meta:
- Course: [[FYS-STK4155]]
- Lecturer: [[Morten Hjorth-Jensen]]
- Date: [[daily/2020-08-20]]