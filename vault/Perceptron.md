A **perceptron** is an algorithm that takes a set of inputs and returns a single binary output. For example, the following diagram shows a perceptron with three inputs $x_1, x_2, x_3$, that returns an output:

![](http://neuralnetworksanddeeplearning.com/images/tikz0.png)

This output is determined by the weighted ($\mathbf w$) sum of the inputs, including an added constant - the bias $b$ - that shifts the decision boundary away from the origin. A perceptron is a so-called [[Binary classifier|binary classifier]], which means its output is either $1$ or $0$. This can be interpreted as "making a decision" by weighing a set of evidence. Consider the following questions:

1. Is the weather good?
2. Have I gotten my paycheck?
3. Are the stores open today?

The answers to these questions are all $1/0$ (yes/no), but can have loads of inputs that aid in finding the correct answer. Not only that, but the answers to these three can further contribute in answering the question of wether I'm going grocery shopping today or not. Many structures with multiple layers can arise from this approach, and quickly get complex. They are, however, useful in many decision making problems.

![](http://neuralnetworksanddeeplearning.com/images/tikz1.png)

Mathematically, a perceptron can be written as

$$\text{output} = \begin{cases}0 & \text{if } \mathbf w\cdot \mathbf x + b \le 0 \\ 1 & \text{if } \mathbf w \cdot \mathbf x + b > 0\end{cases}$$

so it can be described as an [[Artificial neuron|artificial neuron]] with a [[Heaviside step function|Heaviside]] [[Activation function|activation function]].