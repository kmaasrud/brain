The **Leonard-Jones potential** is a model of the [[Interatomic potential|interatomic potential]] between two neutral [[Atom|atoms]] or [[Molecule|molecules]]. 

$$ U(r) = 4\epsilon \left(\left(\frac{\sigma}{r}\right)^{12} - \left(\frac{\sigma}{r}\right)^6\right) ,$$

where $\epsilon$ is a *characteristic energy*, which is specific for the atoms we are modeling. $\sigma$ is a *characteristic length*.

The contributions come from the two main interactions:

- **[[Van der Waals force|Van der Waals interaction]]**: There is an *attractive* force between the atoms, with a potential [[Proportionality|proportional]] to $1/r^6$ ($r$ being the distance between them). 
- **[[Exchange interaction|Pauli repulsion]]**: Due to the possibility of overlapping orbitals, there are quantum mechanical effects which cause *repulsion* between the atoms. This is modelled with a power law of the form $1/r^n$. A good approximation is $n = 12$.