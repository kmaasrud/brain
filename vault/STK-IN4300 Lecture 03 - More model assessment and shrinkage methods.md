## Cross-validation

[[Cross-validation]] is a [[Model assessment|model assessment technique]] based on using a [[Training set|set of training data]] to prime it and then comparing the predictions given to a [[Testing set|validation dataset]], to evaluate the models ability to predict new data. This is to avoid issues like [[Overfitting|overfitting]] and/or [[Selection bias|selection bias]]. The method directly estimates the expected extra-sample error:

$$ \text{Err} = \text E\left[L(Y, \hat f(X)\right] ,$$

the average [[Test error|average generalization error]] when $\hat f(X)$ is a applied to an independent test sample from the joint distribution of $X$ and $Y$.

### $K$-fold cross-validation

Ideally, we would split our data into a [[Training set|training set]] and a [[Testing set|validation set]], like explained in [[STK-IN4300 Lecture 02 - Linear methods for regression|a previous lecture]]. However, in many cases our dataset is too small for this. In this case, we will have to use [[$K$-fold cross-validation]] to reuse our [[Training set|training set]] as our [[Testing set|validation set]].

The method involves splitting our dataset into $K$ different "folds" - usually $5$ or $10$. Say, in our example, that we use $K=6$ and divide our dataset into six different folds. First, we use the first fold as our [[Testing set|validation set]], train on the other five and compute the prediction error of the fitted model. Then, we use the second fold as our [[Testing set|validation set]] and train on the remaining sets, this time also computing the prediction error. Doing this cycle through all $K=6$ folds and averaging the prediction errors gives us our [[Cross-validation|cross-validation estimate]] of the prediction error. 

An illustration of this:

![](https://raw.githubusercontent.com/qingkaikong/blog/master/2017_05_More_on_applying_ANN/figures/figure_1.jpg)

Denoting the fitted function that excludes the $k$th fold as $\hat f^{-k}(X)$, and defining a function $\kappa:\{1,\dots,N\}\rightarrow\{1,\dots,K\}$ that takes in an index of the total dataset and returns the index of the fold containing that datapoint, we can write the [[Cross-validation|cross-validation]] estimate of the prediction error a

$$ \text{CV}(\hat f) = \frac{1}{N}\sum_{i=1}^NL\left(y_i, \hat f^{-\kappa(i)}(x_i)\right) .$$

With a set of models indexed by the tuning parameter $\alpha$, we see that

$$ \text{CV}(\hat f,\alpha) = \frac{1}{N}\sum_{i=1}^NL\left(y_i, \hat f^{-\kappa(i)}(x_i, \alpha)\right) $$

is the curve we need to find the minimum of. The value of $\alpha$ minimizing this curve is often denoted $\hat \alpha$, and we now choose our final model to be $f(x,\hat \alpha)$.

#### Choice of $K$

There is no clear solution on how to choose $K$, but we have to be aware that there is a [[Bias-variance tradeoff|bias-variance tradeoff]]. For example, setting $K=N$ (called *leave-one-out cross-validation* or *LOOCV*) estimates the expected test error approximatively unbiased. However, it has very large variance since the [[Training set|training sets]] are very similar to each other.

### Bootstrap

***

Meta:
- Course: [[STK-IN4300]]
- References: [The Elements of Statistical Mechanics](https://web.stanford.edu/%7Ehastie/Papers/ESLII.pdf) and [[Riccardo De Bin|Riccardo's]] [lecture notes](https://www.uio.no/studier/emner/matnat/math/STK-IN4300/h20/slides/lecture_3.pdf).
- Date: [[daily/2020-08-31]]