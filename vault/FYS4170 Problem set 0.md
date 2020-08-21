## Problem 1

### a)

$$\nabla S = \nabla^i S$$

$$\nabla \cdot \mathbf{A} = \nabla_i A^i$$

$$M = M^i_j \Rightarrow M^T = M_j^i$$

$$M = M^i_j \Rightarrow \text{tr}\ M = M_i^i$$

### b)

Using the [[Levi-Civita symbol]], [[Curl (mathematics)|curl]] can be represented in this way using [[Index notation|index notation]]

$$\nabla \times \mathbf{A} = \epsilon_{ijk}\nabla_j A_k$$

Thus, we have

$$\nabla \cdot(\nabla \times \mathbf{A}) = \nabla_i(\epsilon_{ijk}\nabla_j A_k) = \epsilon_{ijk} \nabla_i \nabla_j A_k = 0$$

Since the [[Levi-Civita symbol]] is antisymmetric and $\nabla_i\nabla_j$ is symmetric.

***

$$\nabla \times (\nabla S) = \epsilon_{ijk}\nabla_j \nabla_k S = 0$$

by the same logic as above.

### c)

- $\partial_\mu x^\nu = \delta_\mu^\nu$ is valid
- $\partial_\mu x^\mu = 1$ is not valid, but equals $4$.
- $\partial^\mu x^\nu = g^{\mu\nu}$ is valid, because $\partial^\mu x^\nu = g^{\mu\sigma}\partial_\sigma x^\nu = g^{\mu\sigma}\delta_\mu^{\;\sigma} = g^{\mu\nu}$
- $T_{\alpha\enspace\gamma}^{\;\beta} = g^{\beta\mu} T_{\alpha\mu\gamma} = g^{\mu\beta} T_{\alpha\mu\gamma}$ is valid. The [[Metric tensor|metric tensor]] raises the $\beta$ term, and it equals its own [[Transpose|transpose]].
- $T_{\alpha\enspace\beta}^{\;\beta} = g_{\alpha\mu}g^{\beta\alpha} T^{\mu}_{\;\alpha\beta}$ since $\alpha$ appears three times, which is inconsistent with our notation. A solution would be $T_{\alpha\enspace\beta}^{\;\beta} = g_{\alpha\mu}g^{\beta\sigma} T^{\mu}_{\;\sigma\beta}$

## Problem 2

