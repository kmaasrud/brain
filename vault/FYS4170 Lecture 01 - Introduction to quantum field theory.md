Recall the [[Quantization]] a la [[Erwin Schrödinger|Schrödinger]] with the following properties:

- Relativistic energy-momentum (requirement of [[Special relativity]])
- Number $N$ of particles is conserved

But using these two, we encounter a number of paradoxes:

1. The very concept of a particle seems to be shattered, because the [[Relativistic energy-momentum relation]] combined with the [[Unceirtanty principle]], seems to say that we cannot require that the number of particles is conserved.
2. [[Causality]] is violated
3. There should exist [[Negative energy|negative energy states]]
4. We have no explanation of [[Spin]], but it suddenly appears
5. The [[Probability interpretation]] cannot be explained anymore

In this course we will see what happens if we give up one the assumption that the "number $N$ of particles is conserved", i.e.

> Construct a multiparticle ($N$ not conserved) "field" theory

## 1. Classical field theory

### [[Lagrangian]] formulation

We have a point particle in 1D:

- It has the [[Action (physics)|action]] - $S=\int dt L(q,\dot q)$ - which is only dependent on the [[Phase space]] variables [[Position]] and [[Velocity]]. Minimizing this "trajectory" through [[Phase space]] leads to the [[Euler-Lagrange equation|equations of motion]].

Now lets consider 1D $\rightarrow$ $N$ dimensions. Now $q\rightarrow q = (q_1,...,q_N)$ and $\dot q = \frac{d}{dt}q$. However, our goal is not to consider a situation with $N$ [[Degree of freedom|d.o.f.]], but a situation with infinite [[Degree of freedom|d.o.f.'s]]. 

This is where [[Field theory]] comes in. It considers a [[Lagrangian density]] instead (required by [[Locality]]!). Now our [[Action (physics)|action]] is written:

$$S = \int dtL = \int d^4x\mathcal L(\phi, \partial_\mu \phi ),$$

where $\mathcal L$ is the mentioned [[Lagrangian density]] (or just the [[Lagrangian]], if you must). $\phi(x^\mu)$ is a [[Field (physics)|field]] in [[Space-time]]. So the Lagrangian here is not dependent on $x^\mu$, but on $\phi(x^\mu)$, and the system has infinitely many degrees of freedom.

**[[Principle of least action]]**:
$$0\overset{!}{=}\delta S = \int d^4x\bigg[\frac{\partial \mathcal L}{\partial \phi}\delta\phi + \frac{\partial \mathcal L}{\partial_\mu \phi} \delta(\partial_\mu\phi)\bigg]$$

*Notes*:
- **NB**: [[Index notation|Sum convention]]
- (I don't really understand his usage of curly braces here, but wth)

$$= \int d^4x\bigg[\frac{\partial \mathcal L}{\partial \phi}\delta \phi + \partial_\mu\left(\frac{\partial \mathcal L}{\partial \partial_\mu \phi}\delta \phi\right) - \delta\phi \partial_\mu\left(\frac{\partial \mathcal L}{\partial \partial_\mu \phi}\right)\bigg]$$

- $\partial_\mu\left(\frac{\partial \mathcal L}{\partial \partial_\mu \phi}\delta \phi\right) \rightarrow \int_{\partial V}d\sum_\mu \frac{\partial \mathcal L}{\partial \partial_\mu \phi}\delta \phi$. In our case we describe low interaction so we can ignore this surface term. So the previous $\rightarrow 0$ if:

	1. $\delta\phi(t_1,\vec x) = \delta\phi(t_2,\vec x) = 0$
	2. $\delta \phi(t_1<t<t_2,\vec x)\rightarrow 0$ sufficiently fast for $|\vec x|\rightarrow \infty$ (as you go away from the experiment, you want to make sure it falls off).

$$\Rightarrow 0 \overset{!}{=} \int d^4x\bigg[\frac{\partial \mathcal L}{\partial \phi} - \partial_\mu\left(\frac{\partial \mathcal L}{\partial \partial_\mu\phi}\right)\bigg]\delta \phi \qquad \forall\ \delta\phi(x^\mu)$$

$$\partial_\mu \frac{\partial \mathcal L}{\partial \partial_\mu \phi} - \frac{\partial \mathcal L}{\partial \phi} = 0$$

which is the [[Euler-Lagrange equation#Field theory|Euler-Lagrange equation]] completely analogous to the [[Euler-Lagrange equation#Classical mechanics|classical]] one.

We could have more than one, and different fields, this would still describe the system. 

### [[Hamiltonian]] formulation

Recall: $p\equiv \frac{\partial L}{\partial \dot q}$.

We expand on this concept by defining the *[[Conjugate momentum field|canonical(!) momentum density]]*

$$\pi(x^\mu)\equiv \frac{\partial \mathcal L}{\partial \dot \phi}$$

Now we can use this to describe the [[Hamiltonian]]

$$H\equiv \int d^3x\bigg[\pi(x^\mu)\dot \phi(\vec x^\mu) - \mathcal L\bigg]$$

and the part inside is the *[[Hamiltonian density]]*

$$\mathcal H = \mathcal H(\phi, \pi, \vec \nabla \phi) \equiv \pi(x^\mu)\dot \phi(\vec x^\mu) - \mathcal L$$

### Example: Scalar field $\phi(x^\mu)$

$$\Rightarrow \mathcal L = \frac{1}{2}(\partial_\mu\phi)^2 - V(\phi),\qquad V "=" \frac{1}{2}m^2\phi^2 = \text{"1st term in Taylor expansion"}$$

**Note**: $(\partial_\mu\phi)^2 = (\partial_\mu\phi)(\partial^\mu\phi)$.

Using:

- $\frac{\partial \mathcal L}{\partial \phi} = -V' \rightarrow -m^2\phi$
- $\frac{\partial \mathcal L}{\partial(\partial_\mu \phi)} = \frac{1}{2}\frac{\partial}{\partial(\partial_\mu \phi)}[(\partial_\nu \phi)(\partial_\sigma \phi)\eta^{\nu\sigma}]$

	$= \frac{1}{2}\left[\delta_\nu^\mu(\partial_\sigma\phi)\eta^{\nu\sigma} (\partial_\nu\phi) \delta_\sigma^\mu \eta^{\nu\sigma}\right]= \partial^\mu\phi$
	
Applying the [[Euler-Lagrange equation]] we get the [[Klein-Gordon equation]] (for a *classical* field)

$$(\partial^\mu\partial_m + m^2)\phi = (\square + m^2)\phi = 0$$

***

$$\pi = \frac{\partial \mathcal L}{\partial \dot \phi} = \dot \phi$$

$$\mathcal H = \pi\dot \phi - \mathcal L = \frac{1}{2}\dot \phi^2 + \frac{1}{2}(\vec \nabla \phi)^2 + \frac{1}{2}m^2\phi^2$$

We interpret: 
- $\frac{1}{2}\dot \phi^2$ as the [[Kinetic energy]] of the field.
- $\frac{1}{2}(\vec \nabla \phi)^2$ as the *shearing* in space.
- $\frac{1}{2}m^2\phi^2 >0$ associated with having the field at all

## [[Noether's theorem]]

> For every symmetry, there is a conservation law (a constant of motion)

Consider a continuous field transformation of a [[Field (physics)|physical field]].

$$\phi(x)\rightarrow \phi'(x)\equiv \phi(x) + \Delta\phi(x)$$

$$\Rightarrow \mathcal L \rightarrow \mathcal L' = \mathcal L + \Delta \mathcal L$$

The transformation of $\phi(x)$ is a called a [[Symmetry (physics)|symmetry]] [[iff]] the equations of motion do not change under the transformation. 

- Sufficient condition: $\Delta\mathcal L = \partial_\mu J^\mu(x)$
- In general (when using [[Euler-Lagrange equation|equations of motion]]): $\mathcal L\rightarrow \mathcal L' = \mathcal L(\phi', \partial_\mu \phi')$, which we [[Taylor series|Taylor expand]]:

	$= \mathcal L(\phi, \partial_\mu\phi) + \alpha\frac{\partial \mathcal L}{\partial \phi}\Delta \phi + \alpha\frac{\partial \mathcal L}{\partial \partial_\mu \phi}\Delta\partial_\mu \phi + O(\alpha^2)$
	
	$\alpha\frac{\partial \mathcal L}{\partial \phi}\Delta \phi + \alpha\frac{\partial \mathcal L}{\partial \partial_\mu \phi}\Delta\partial_\mu \phi + O(\alpha^2) = \alpha\Delta\mathcal L = \alpha\bigg[\left(\frac{\partial \mathcal L}{\partial \phi} - \partial_\mu\frac{\partial \mathcal L}{\partial \partial_\mu\phi}\right)\Delta\phi + \partial_\mu\frac{\partial \mathcal L}{\partial(\partial_\mu \phi)}\Delta \phi\bigg]$
	
	The term in the parenthesis dissapears (e.o.m.)
	
$\Rightarrow$ if there is a symmetry (i.e. $J^\mu$ exists), then

$$\partial_\mu \left(J^\mu - \frac{\partial \mathcal L}{\partial (\partial_\mu\phi)}\Delta \phi\right) = \partial_\mu j_N^\mu = 0,$$

where

$$j_N^\mu \equiv J^\mu - \frac{\partial \mathcal L}{\partial (\partial_\mu\phi)}\Delta \phi$$

which is called the [[Conserved current]]

> For each symmetry $\Delta \phi$, there is a [[Conserved current|conserved current]] $j_N^\mu$ (and [[Conserved charge]] $Q = \int d^3x j^0$)

### Application: the energy-momentum tensor

[[Space-time]] translations: $x^\nu\rightarrow x'^\nu = x^\nu + a^\nu$. This gives me four different symmetries - one for each value of $\nu$. 

$\Rightarrow \phi(x) \rightarrow \phi'(x) = \phi(x + a)$, which we [[Taylor series|Taylor expand]] to $\phi(x) + a^\nu\partial_\nu\phi(x) + O(a^2)$. We define $\partial_\nu\phi(x) \equiv (\Delta \phi)_\nu$ - for each symmetry, we have a change in the field, and this is a sum over all of them.

We exploit the fact that we know about [[Lorentz covariance|Lorentz symmetries]]. We know that the [[Lagrangian]] must transform the same way as the scalar field. 

$\mathcal L\rightarrow \mathcal L + a^\nu\partial_\nu \mathcal L = \mathcal L + a^\nu\partial_\mu(\delta^\mu_\nu\mathcal L)$ and identify $\delta^\mu_\nu\mathcal L \equiv (J^\mu)_\nu$.

We have *four* conserved currents:

$$(j_N^\mu)_\nu \equiv T^\mu_\nu = \frac{\partial \mathcal L}{\partial (\partial_\mu \phi)}\partial_\nu\phi - \mathcal L \delta^\mu_\nu$$

What are the conserved charges? They are:

1. $\nu = 0 \rightarrow H = \int T^{00} d^3x = \int \mathcal H d^3x$.
2. $\nu = i \rightarrow p^i = \int T^{0i} d^3x = -\int \pi \partial_i \phi d^3x$, which is the [[physical momentum|physical momentum]].

## Videos

<iframe src="https://www.uio.no/studier/emner/matnat/fys/FYS4170/h20/forelesningsvideoer/qft_lecture_01_1.mp4?vrtx=video-embed" frameBorder="0" allowfullscreen></iframe>

<iframe src="https://www.uio.no/studier/emner/matnat/fys/FYS4170/h20/forelesningsvideoer/qft_lecture_01_2.mp4?vrtx=video-embed" frameBorder="0" allowfullscreen></iframe>

<iframe src="https://www.uio.no/studier/emner/matnat/fys/FYS4170/h20/forelesningsvideoer/qft_lecture_01_3.mp4?vrtx=video-embed" frameBorder="0" allowfullscreen></iframe>

<iframe src="https://www.uio.no/studier/emner/matnat/fys/FYS4170/h20/forelesningsvideoer/qft_lecture_01_4.mp4?vrtx=video-embed" frameBorder="0" allowfullscreen></iframe>

<iframe src="https://www.uio.no/studier/emner/matnat/fys/FYS4170/h20/forelesningsvideoer/qft_lecture_01_5.mp4?vrtx=video-embed" frameBorder="0" allowfullscreen></iframe>

***

Meta:
- Course: #FYS4170
- Date: [[daily/2020-08-19]]
- Lecturer: [[Torsten Bringmann]]