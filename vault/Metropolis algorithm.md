The **Metropolis** or **Metropolis-Hastings** algorithm is a method of obtaining random samples from a [[Probability distribution|probability distribution]] which might be difficult to sample directly from.

## The algorithm

We often might know a [[Probability distribution|probability distribution]] $P(\theta)$ only up to the [[Proportionality|proportional function]] $g(\theta)$, because doing integration to normalize it might be difficult. We are thus presented with the case of

$$p(\theta) \propto g(\theta),$$

where our goal is to sample from $p(\theta)$. The algorithm proceeds as follows:

1. Select an initial value $\theta_0$. This is often chosen randomly.
2. For $i=1,...,N$, repeat the following
	1. Draw a candidate $\theta'$ from the proposal distribution $q(\theta'|\theta_{i-1})$
	2. Compute the ratio $r = \frac{g(\theta')q(\theta_{i-1}|\theta')}{g(\theta_{i-1})q(\theta'|\theta_{i-1})}$
	3. Decide:
		- If $r \ge 1$ or $r > u$ (where $u$ is a random sample from the uniform distribution), set $\theta_{i} = \theta'$.
		- Else, set $\theta_{i} = \theta_{i-1}$
		
The proposal distribution $q(\theta'|\theta_{i-1})$ is the distribution that suggests a new sample given the previous one. A typical choice here is to use a [[Normal distribution|normal distribution]] centered around the previous sample to favor samples close to it. This makes the sequence into a [[Random walk|random walk]] and makes computing $r$ a bit simpler (now $r = \frac{g(\theta')}{g(\theta_{i-1})}$)[^1]

Ideally, the random walk Metropolis algorithm should accept about $23\%-50\%$ of the proposed candidates^[From [this video](https://youtu.be/0lpT-yveuIA?t=550)].

---

The Metropolis algorithm is known as a first order [[Markov chain Monte Carlo]] method in the sense that the next step in the chain only depends on the current position.

[^1]: Hello
	My name is.