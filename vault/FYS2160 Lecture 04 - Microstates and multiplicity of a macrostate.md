## Micro- and macrostates

Say we have a box with many particles bouncing around in it (a gas). One way to describe the state of the gas inside this box could be to assign a binary descriptor to each particle $n_i$. $n_i = 1$ if the particle is on the *left half* of the box, and $n_i = 0$ if the particle is on the *right half*. The *set* (or actually *vector*, since the microstate is dependent on the ordinality) of all $n_i$, $(n_1,...,n_N)$ is called the *[[Microstate (statistical mechanics)|microstate]]* of the gas.

Given this, we could calculate the number of particles located on the *left half* of the box, as $n = \sum_{i=1}^Nn_i$. The value of $n$ is a *[[Macrostate (statistical mechanics)|macrostate]]* of the gas. From this example its pretty obvious that a system can have multiple different [[Microstate (statistical mechanics)|microstates]] for one specific [[Macrostate (statistical mechanics)|macrostate]].

Another example of a micro/macrostate could be a set of two dice, described my the vector $(n_1, n_2)$. $(1,6)$ could be a *[[Microstate (statistical mechanics)|microstate]]* here, with $7$ being a possible *[[Macrostate (statistical mechanics)|macrostate]]*.

### Multiplicity

The number of [[Microstate (statistical mechanics)|microstate]] that give the same [[Macrostate (statistical mechanics)|macrostate]] is called the *[[Multiplicity|multiplicity]]* of that [[Macrostate (statistical mechanics)|macrostate]]. This can be used to find the probability of a certian [[Macrostate (statistical mechanics)|macrostate]], by dividing its [[Multiplicity|multiplicity]] by the number of total [[Microstate (statistical mechanics)|microstate]]. More formally, this can be written:

$$ P(q) = \frac{\Omega (q)}{\Omega_{\text{tot}}} ,$$

where $P(q)$ is the probability of the state $q$, $\Omega(q)$ is the [[Multiplicity|multiplicity]] of state $q$ and $\Omega_{\text{tot}}$ is the total [[Multiplicity|multiplicity]] of the system.

Going back to our original example with the gas in the box, we 

***

Meta:
- Course: [[FYS2160]]
- References: [Anders Malthe-Sørensen: "Statistical and Thermal Physics Using Python"](https://www.uio.no/studier/emner/matnat/fys/FYS2160/h20/Compendium/stat_thermal_phys_python.pdf)
- Date: [[daily/2020-08-27]]