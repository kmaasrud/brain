## Lorentz group

Consider a [[Space-time|space-time]] [[Lorentz transformation]] $x^\mu \rightarrow x^{\prime\mu} = \Lambda^\mu_\nu x^\nu$. 

These are equivalent:
- $\Lambda$ is a [[Lorentz transformation]]
-  $x^2 \equiv \eta_{\mu\nu} x^\mu x^\nu \overset{!}{=} x^{\prime 2}$
-  $x^T\eta x \overset{!}{=} (x')^T\eta x' = (\Lambda x)^T\eta (\Lambda x) = x^T\Lambda^T\eta \Lambda x$
- **$\eta = \Lambda^T\eta \Lambda$**

For completeness, lets write the last thing in index-notation as well:  $\eta_{\mu\nu} = \Lambda_\mu^\tau \eta_{\tau\sigma}\Lambda_\nu^\sigma$. 

***

Compare this to 3D rotations:  $x^i \rightarrow R^{ij}x^i$

$R$ is a rotation $\Leftrightarrow x^2\equiv \vec x\cdot \vec x =$ constant $\Leftrightarrow \mathbb{1}_{3\times3} = R^T \mathbb{1}_{3\times 3}R$ $\Leftrightarrow R$ is *[[Orthogonality|orthogonal]]*.

***

[[Lorentz transformation|Lorentz transformations]] form a [[Group (mathematics)|group]] $L$: $\{\{\Lambda\}, \cdot\}$. A group satisfies:
- [[Closure]]: $\Lambda_1, \Lambda_2 \in L \Rightarrow \Lambda_1 \cdot \Lambda_2 \in L$
- [[Associativity]]: $\forall\ \Lambda_1, \Lambda_2, \Lambda_3 \in L: (\Lambda_1\cdot\Lambda_2)\cdot \Lambda_3 = \Lambda_1\cdot(\lambda_2\cdot\Lambda_3)$
- [[Identity]]: $\forall\ \Lambda \in L: \mathbb{1}\cdot\Lambda = \Lambda\cdot \mathbb{1} = \Lambda$

***

Meta:
- Course: #FYS4170 
- Lecturer: [[Torsten Bringmann]]
- Date: [[daily/2020-08-20]]