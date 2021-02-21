A **perceptron** is an algorithm that takes a set of inputs and returns a single binary output. For example, the following diagram shows a perceptron with three inputs $x_1, x_2, x_3$, that returns an output:

![](https://www.startpage.com/av/proxy-image?piurl=https%3A%2F%2Fwww.allaboutcircuits.com%2Fuploads%2Farticles%2Fhow-to-perform-classification-using-a-neural-network-a-simple-perceptron-example_rk_aac_image2.jpg&sp=1613904738T51951699155ce66d63d95336f8ae5b51553b7867206ddb4f585710ced69eace8)

This output is determined by the weighted ($\mathbf w$) sum of the inputs, including an added constant - the bias $b$ - that shifts the decision boundary away from the origin. A perceptron is a so-called [[Binary classifier|binary classifier]], which means its output is either $1$ or $0$. This can be interpreted as "making a decision" by weighing a set of evidence. Consider the following questions:

1. Is the weather good?
2. Have I gotten my paycheck?
3. Are the stores open today? ^6d807f

The answers to these questions are all $1/0$ (yes/no), but can have loads of inputs that aid in finding the correct answer. Not only that, but the answers to these three can further contribute in answering the question of whether I'm going grocery shopping today or not. Many structures with multiple layers can arise from this approach, and quickly get complex. They are, however, useful in many decision making problems.

![](https://www.startpage.com/av/proxy-image?piurl=https%3A%2F%2Fmissinglink.ai%2Fwp-content%2Fuploads%2F2018%2F11%2Fmultilayer-perceptron.png&sp=1613904710T74d642d21844611d6139087439fd63c645a9309f2e7fed278c003c46e4223ea6)

Mathematically, a perceptron can be written as

$$\text{output} = \begin{cases}0 & \text{if } \mathbf w\cdot \mathbf x + b \le 0 \\ 1 & \text{if } \mathbf w \cdot \mathbf x + b > 0\end{cases}$$

so it can be described as an [[Artificial neuron|artificial neuron]] with a [[Heaviside step function|Heaviside]] [[Activation function|activation function]].