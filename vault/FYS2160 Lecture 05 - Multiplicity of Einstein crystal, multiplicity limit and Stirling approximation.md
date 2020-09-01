## Einstein crystals

Inspired by the model of an [[Ideal gas|ideal gas]], we make a simplification of solids as well. We picture the solid as atoms spaced regularly in a lattice, each atom held in place by the potential generated by the surrounding atoms. The atoms vibrate around the minimum of this potential. We describe this local potential well by the [[Taylor series|lowest order approximation]], which corresponds to [[Harmonic oscillator|the harmonic oscillator]].

So the simplification has these properties:

- The atoms do not interact directly
- Each atom acts as a [[Harmonic oscillator|harmonic oscillator]] in a 3D potential
- The system consists of $N$ atoms
- The atoms in the system share the total energy of the system

This model is called the **[[Einstein crystal]]** or the **ideal crystal**.

### Multiplicity of Einstein crystals

From quantum mechanics, we know that the energies of a harmonic system is quantized, namely it follows the values

$$E = h\nu n,$$

where $n$ takes integer values. So, looking at a whole system of atoms, we can measure the total energy as the sum of the individual energies, but measured in the dimensionless unit $\epsilon = h\nu$. This measure is often called $q$, and can only take integer values. Say we have a crystal with $4$ atoms, each at the energy level $n_i$. In this case, we would calculate

$$q = \sum_{i=1}^4 n_i.$$

This means we can describe the [[Macrostate (statistical mechanics)|macrostate]] of our [[Einstein crystal]] using the two integers $N$ (the number of atoms) as well as $q$ (the total energy level). So, for example, a system described by the [[Macrostate (statistical mechanics)|macrostate]] $N=4$ and $q=2$ could have the two [[Microstate (statistical mechanics)|microstates]] $(2,0,0,0)$ and $(0,1,1,0)$ separately. 

To calculate the [[Multiplicity|multiplicity]] of an [[Einstein crystal]], we first need to represent the [[Microstate (statistical mechanics)|microstates]] in a simpler way. Picture $N$ buckets and $q$ balls. I think you would agree that the different ways of putting the $q$ balls in the buckets correspond to the different [[Microstate (statistical mechanics)|microstates]] of our [[Einstein crystal]]. Now place the buckets next to each other and only consider the border between them, which we picture as just walls. Naming the walls $1$ and the balls $0$, we can rewrite the [[Microstate (statistical mechanics)|microstate]] $(2,0,0,0)$ as $00111$, and $(0,1,0,1)$ into $10110$. I think you see how this is much simpler, because calculating the multiplicity of a [[Einstein crystal|crystal]] now turns into a question of arranging $q$ balls (or zeroes) on either side of $N-1$ walls (or ones).

Thus, the [[Multiplicity|multiplicity]] of an [[Einstein crystal]] reads:

$$\Omega(N,q) = \left(\begin{matrix}(N-1)+ q \\ q\end{matrix}\right) = \frac{(N-1+q)!}{q!(N-1)!}.$$

### Multiplicity of coupled Einstein crystals

Say we have two [[Einstein crystal|Einstein crystals]] that are in contact. We name the crystals $A$ and $B$ respectively. The total system has the macrostate:

- $N = N_A + N_B$
- $q = q_A + q_B$

and since the [[Multiplicity|multiplicity]] of the crystals are independent of each other, the total [[Multiplicity|multiplicity]] is

$$\Omega = \Omega_A\cdot \Omega_B.$$

A simple [[Python]] implementation follows here:

```python
from matplotlib.pyplot import *

# comb(N,k) returns the number of N things taken k at a time.
from scipy.special import comb


def multiplicity_plot(NA, NB, q):
    N = NA + NB
    qA_all = [qval for qval in range(q+1)]

    totMult = []
    for qA in qA_all:
        qB = q - qA
        multA = comb(NA - 1 + qA, qA)
        multB = comb(NB - 1 + qB, qB)
        totMult.append(multA * multB)

    plot(qA_all, totMult, '-o')

    xlabel(r'$q_A$'), ylabel(r'$\Omega$')
    show()
```


Running `multiplicity_plot(100, 100, 200)` returns this plot:

![](data:image/png;base64,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)

## Stirling approximation

***

Meta:
- Course: [[FYS2160]]
- References: [[Statistical and Thermal Physics using Python]] and [[Dag Kristian Dysthe|Dag's]] [lecture notes](https://www.uio.no/studier/emner/matnat/fys/FYS2160/h20/Lectures%20and%20assignments/Lecture5/index.html)
- Date: [[daily/2020-09-01]]
- Time: 12:55