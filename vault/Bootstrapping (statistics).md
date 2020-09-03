**Bootstrapping** is (in general) a method of assessing the accuracy of a statistic. It can also be used to estimate the skill of a [[Machine learning|machine learning (ML)]] model.

Briefly, this is the process:

1. Choose a number $B$ of bootstrap samples to perform.
2. Generate $B$ bootstrap sets of the desired size, using [[Sampling with replacement|sampling with replacement]].
3. For each bootstrap set, either:
	- Calculate the statistic on the set.
	- Fit a model to the set and estimate the skill of said model.
4. Calculate the mean of the statistics/model skill estimates.