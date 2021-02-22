The **variational Monte Carlo (VMC) method** is a method that applies the [[Variational method|variational method]] to approximate the [[Ground state|ground state]] of a quantum mechanical system. To achieve this, [[Monte Carlo integration]] is used.

## Brief description

Given the Hamiltonian $H$ and the [[Many-body problem|many-body system]] $R$, we define a trial [[Wave function|wave function]] $|\Psi_T(R, \alpha)\rangle$, and the corresponding [[Expectation value (quantum mechanics)|expected energy]] $E(\alpha)$. The latter is written as

$$E(\alpha) = \frac{\langle \Psi(R, \alpha)|H|\Psi(R, \alpha)\rangle}{\langle\Psi(R, \alpha)|\Psi(R, \alpha)\rangle} = \frac{\int|\Psi(R,\alpha)|^2 \frac{H\Psi(R, \alpha)}{\Psi(R, \alpha)}dR}{\int|\Psi(R, \alpha)|^2 dR} = \int \frac{|\Psi(R, \alpha)|^2}{\int |\Psi(R, \alpha)|^2 dR}E_{\text{local}}(R)\ dR,$$

where $E_{\text{local}}(R) = \frac{H\Psi(R, \alpha)}{\Psi(R, \alpha)}$ is the so-called *local energy*. $\frac{|\Psi(R, \alpha)|^2}{\int |\Psi(R, \alpha)|^2dR}$ can be interpretted as a [[Probability distribution|probability distribution]] and thus be used in the [[Monte Carlo method]] to evaluate $E(\alpha)$ as the average of $E_{\text{local}}(R)$. Doing this for a set of variational parameters $\alpha$, we find the minimum and use it as our approximation for the [[Ground state|ground state]] [[Wave function|wave function]].


### The Metropolis algorithm

...