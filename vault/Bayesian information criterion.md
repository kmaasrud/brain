The **Bayesian information criterion** (BIC) or **Schwarz information criterion** (SIC) is a criterion for [[Model selection|model selection]] in a finite set of models. We prefer the model with the lowest BIC. Its general defenition is

$$ \text{BIC} = \log N\cdot d - 2\ \text{loglik} ,$$

where $N$ is the number of data points $d$ is the number of parameters estimated by the model and $\text{loglik}$ is the log of the maximized [[Likelihood function|likelihood function]].

Sources:
- [Wikipedia](https://en.wikipedia.org/wiki/Bayesian_information_criterion)
- [[The Elements of Statistical Learning]]