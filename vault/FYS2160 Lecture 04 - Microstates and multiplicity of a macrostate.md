## Micro- and macrostates

Say we have a box with many particles bouncing around in it (a gas). One way to describe the state of the gas inside this box could be to assign a binary descriptor to each particle $n_i$. $n_i = 1$ if the particle is on the *left half* of the box, and $n_i = 0$ if the particle is on the *right half*. The *set* (or actually *vector*, since the microstate is dependent on the ordinality) of all $n_i$, $(n_1,...,n_N)$ is called the *[[Microstate (statistical mechanics)|microstate]]* of the gas.

Given this, we could calculate the number of particles located on the *left half* of the box, as $\sum_{i=1}^Nn_i$. This value is a *[[Macrostate (statistical mechanics)|macrostate]]* of the gas. From this example its pretty obvious that a system can have multiple different [[Microstate (statistical mechanics)|microstates]] for one specific [[Macrostate (statistical mechanics)|macrostate]].

Another example of a micro/macrostate could be a set of two dice, described my the vector $(n_1, n_2)$. $(1,6)$ could be a *[[Microstate (statistical mechanics)|microstate]]* here, with $7$ being a possible *[[Macrostate (statistical mechanics)|macrostate]]*.

### Multiplicity

The number of [[Microstate (statistical mechanics)|microstate]] that give the same [[Macrostate (statistical mechanics)|macrostate]] is called the *[[Multiplicity|multiplicity]]* of that [[Macrostate (statistical mechanics)|macrostate]]. This can be used to find the probability of a certian [[Macrostate (statistical mechanics)|macrostate]], by dividing its [[Multiplicity|multiplicity]] by the number of total [[Microstate (statistical mechanics)|microstate]]. More formally, this can be written:

$$ P(q) = \frac{\Omega (q)}{\Omega_{\text{tot}}} ,$$

where $P(q)$ is the probability of the state $q$, $\Omega(q)$ is the [[Multiplicity|multiplicity]] of state $q$ and $\Omega_{\text{tot}}$ is the total [[Multiplicity|multiplicity]] of the system.

Going back to our original example with the gas in the box, we consider the macrostate describing the number of particles located on the left half of the box, and call it $\lambda$ (lambda = "l" for left):

$$ \lambda = \sum_{i=1}^N \lambda_i.$$

Here $N$ is the total number of particles in the gas and $\lambda_i = 1$ if the $i$th particle is located on the *left side* of the box. We've earlier found that the probability distribution for $\lambda$ is given by the binomial distribution, namely

$$ P(N,\lambda) = 2^{-N}\Omega(N,\lambda) ,$$

where $\Omega(N,\lambda) = \left(\begin{matrix}N \\ \lambda\end{matrix}\right)$ is the [[Multiplicity|multiplicity]] of the [[Macrostate (statistical mechanics)|macrostate]] $\lambda$, given $N$ particles. The [[Mean|average]] and the [[Standard deviation|standard deviation]] are easily calculated, and looking at their ratio,

$$ \overline{\lambda} = \frac{N}{2},\quad \sigma_\lambda = \sqrt{\frac{N}{4}},\quad \frac{\sigma_\lambda}{\overline \lambda} = N^{-1/2} ,$$

it's apparent that, as the number of particles gets big, the standard deviation gets negligible and we can pretty much consider $\lambda$ a constant. As an example, a litre of gas at room temperature (with about $10^{23}$ particles) has a standard deviation of about $10^{-10}$ the average value, which is extremely accurate.

***

Meta:
- Course: [[FYS2160]]
- References: [Anders Malthe-Sørensen: "Statistical and Thermal Physics Using Python"](https://www.uio.no/studier/emner/matnat/fys/FYS2160/h20/Compendium/stat_thermal_phys_python.pdf)
- Date: [[daily/2020-08-27]]