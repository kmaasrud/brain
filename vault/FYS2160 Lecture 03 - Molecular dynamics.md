(These notes were not taken from the actual lecture, but from the [compendium](https://www.uio.no/studier/emner/matnat/fys/FYS2160/h20/Compendium/stat_thermal_phys_python.pdf) and other sources)

## Molecular dynamics

**[[Molecular dynamics]]** or *MD* is  a study of the physical movements of a system of [[Atom|atoms]]/[[Molecule|molecules]] via numerically computing their movements. Most commonly, [[Newton's laws of motion]] are used, based on the [[Interatomic potential|interatomic potentials]] present in the system. 

Now, to accurately depict the dynamics of a large enough system, we would need to compute advanced [[Quantum mechanics|quantum mechanical]] effects on an enormous amount of particles, which would be computationally demanding. Therefore, simplifications - like using [[Newton's laws of motion|Newton's laws]] and/or only considering interactions between neighbouring particles - are required, but only to a point where the cumulating errors are kept to a minimum. 

### Leonard-Jones potential

Let us consider one very simple system. We want to model the interactions between [[Noble gas|noble gas]] atoms, for example [[Argon]]. Between two atoms, these are the main contributions:

- **[[Van der Waals force|Van der Waals interaction]]**: There is an *attractive* force between the atoms, with a potential [[Proportionality|proportional]] to $1/r^6$ ($r$ being the distance between them). 
- **[[Exchange interaction|Pauli repulsion]]**: Due to the possibility of overlapping orbitals, there are quantum mechanical effects which cause *repulsion* between the atoms. This course will not go deeper into this, and we model this with a power law of the form $1/r^n$. In the case of [[Argon]], a suitable approximation would be $n = 12$.

Combining these into one model, we get the [[Leonard-Jones potential]]:

$$ U(r) = 4\epsilon \left(\left(\frac{\sigma}{r}\right)^{12} - \left(\frac{\sigma}{r}\right)^6\right) ,$$

where $\epsilon$ is a *characteristic energy*, which is specific for the atoms we are modeling. $\sigma$ is a *characteristic length*.

The minimum of this potential is easily found as

$$ F(r) = -\frac{d}{dr} U(r) = 0 $$
$$ F(r) = 24 \epsilon_0\left(\left(\frac{\sigma}{r}\right)^6 - 2\left(\frac{\sigma}{r}\right)^{12} \right) = 0 \Rightarrow \frac{r}{\sigma} = 2^{1/6} $$

(...Page 34 of compendium)