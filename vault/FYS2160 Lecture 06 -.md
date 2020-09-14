As mentioned in the end of [[FYS2160 Lecture 05 - Multiplicity of Einstein crystal, multiplicity limit and Stirling approximation#Multiplicity of coupled Einstein crystals|the last lecture]], a system will always develop towards the most likely [[Macrostate (statistical mechanics)|macrostate]] - namely, the [[Macrostate (statistical mechanics)|macrostate]] with the highest [[Multiplicity|multiplicity]]. The final state is called the **[[Thermodynamic equilibrium|equilibrium state]]** of the system.

#### Example

Going back to the example with the two contacting [[Einstein crystal|Einstein crystals]], we consider the multiplicity of the system where one of the crystals has energy $q_A$:

$$ \Omega = \Omega_A \Omega_B = \Omega(N_A, q_A)\Omega(N_B, q - q_A) ,$$

where $q = q_A + q_B$ is the conserved total energy. We can find the extremum of this and calculate onwards from there

$$ \frac{\partial \Omega}{\partial q_A}\Omega = \frac{\partial \Omega_A}{\partial q_A} \Omega_B + \Omega_A\frac{\partial \Omega_B}{\partial q_A} = 0 $$

$$ \Rightarrow \frac{\partial \Omega_A}{\partial q_A} \Omega_B - \Omega_A\frac{\partial \Omega_B}{\partial q_B} = 0 $$

$$\Rightarrow \frac{1}{\Omega_A}\frac{\partial \Omega_A}{\partial q_A} = \frac{1}{\Omega_B}\frac{\partial \Omega_B}{\partial q_B} $$

$$\Rightarrow \frac{\partial \ln \Omega_A}{\partial q_A} = \frac{\partial \ln \Omega_B}{\partial q_b} .$$

now this last expression suggests a relation between the logarithms of the multiplicities corresponding to the [[Thermodynamic equilibrium|equilibrium state]]. We introduce the term *[[Entropy|entropy]]* to explain this.

## Definition of entropy

The [[Entropy|entropy]] of an isolated system with a given number of particles $N$, volume $V$ and energy $E$ is defined as

$$ S = k\ln \Omega(N,V,E) ,$$

where $k$ is the [[Boltzmann constant]] and $\Omega(N, V, E)$ is the [[Multiplicity|multiplicity]] of the system at the given $N$, $V$ and $E$.

***

Meta:
- Course: [[FYS2160]]
- References: [[Statistical and Thermal Physics using Python]]
- Date: [[daily/2020-09-09]]
- Time: 18:00