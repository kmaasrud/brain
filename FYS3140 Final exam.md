# Problem 1
## 1.a)

I consider the length of the arch $C_R$ and multiply it by the maximum value of the function to get an answer greater than the integral in question. The result when letting $R\rightarrow\infty$ is:
$$\lim_{R\rightarrow\infty} |\tilde I_R| = \lim_{R\rightarrow\infty} \left|\int_{C_R}f(z)dz\right| < \lim_{R\rightarrow\infty} (\phi_2 - \phi_1) R \cdot M(R) = 0$$
$$\Rightarrow \lim_{R\rightarrow\infty} \tilde I_R = 0$$
## 1.b)
![](assets/1b.png)
Since $f(z)$ is analytic (has no poles) in the whole region encapsulated by $\Gamma_R$, as well as on $\Gamma_R$, I can apply [Cauchy's integral theorem](https://mathworld.wolfram.com/CauchyIntegralTheorem.html), and thus conclude with:
$$I_R = \oint_{\Gamma_R} e^{iaz^2}dz = 0.$$
## 1.c)
Using the same logic as in "1.a)", I need to find an upper bound to the absolute value of the integral. This can be done by substituting $z = Re^{i\theta}$, with $dz = iRe^{i\theta}d\theta$, giving:

$$\left|\int_{C_2}e^{iaz^2}dz\right| = \left|\int_0^{\frac{\pi}{4}}e^{ia\left(Re^{i\theta}\right)^2}iRe^{i\theta}d\theta\right| = \left|\int^{\frac{\pi}{4}}_0 e^{iaR^2\cos(2t)}e^{-aR^2\sin(t2)}iRe^{i\theta}d\theta\right|$$

$$\le R\int^{\frac{\pi}{4}}_0e^{-aR^2\sin(2t)}d\theta \le R\int^{\frac{\pi}{4}}_0e^{-\frac{4aR^2}{\pi}\theta}d\theta = \frac{\pi}{4aR} - \frac{\pi}{4aRe^{aR^2}}.$$

As $R\rightarrow\infty$, this clearly $\rightarrow 0$, and with the magnitude of the integral being limited to $0$,
$$\int_{C_2}e^{iaz^2}dz = 0$$
## 1.d)
Along $C_1$, $z\in\mathbb R$. I can therefore change to the real variable $x$ thusly:
$$\int_{C_1}e^{iaz^2}dz = \int^R_0e^{iax^2}dx = \int^R_0\left(\cos(ax^2) + i\sin(ax^2)\right)dx$$
$$= \int^R_0\cos(ax^2)dx + i\int^R_0\sin(ax^2)dx$$
$C_3$ is simply $C_1$, but rotated by the factor $e^{i\frac{\pi}{4}}$, so I can substitute $z = r e^{i\frac{\pi}{4}}$, with $dz = e^{i\frac{\pi}{4}}dr$
$$\int_{C_3}e^{iaz^2}dz = \int_R^0e^{iar^2e^{i\frac{\pi}{2}}}e^{i\frac{\pi}{4}}dr = -e^{i\frac{\pi}{4}}\int_0^Re^{-ar^2}dr,$$
which is a [[Gaussian integral]].
## 1.e)
From "1.d)", I simply find
$$\int^\infty_0\cos(ax^2)dx = \lim_{R\rightarrow\infty}\Re\left(\int_{C_{1}}e^{iaz^2}dz\right).$$
With the knowledge from "1.b)", that $$\oint_{\Gamma_R} e^{iaz^2}dz = \int_{C_1}e^{iaz^2}dz + \int_{C_2}e^{iaz^2}dz + \int_{C_3}e^{iaz^2}dz = 0$$, I recognize
$$\int_{C_1}e^{iaz^2}dz = -\int_{C_3}e^{iaz^2}dz = e^{i\frac{\pi}{4}}\int_0^Re^{-ar^2}dr.$$
The Gaussian integral $$\int^\infty_{-\infty}e^{-ax^2}dx$$ is known to equal $$\sqrt{\frac{\pi}{a}}$$, and since Gaussian functions are even, halving this gives me
$$\int^\infty_0 e^{-ax^2}dx = \sqrt{\frac{\pi}{4a}}.$$
Using this, I get the final result:
$$\int^\infty_0\cos(ax^2)dx = \lim_{R\rightarrow\infty}\Re\left(e^{i\frac{\pi}{4}}\int_0^Re^{-ar^2}dr\right) = \Re\left(e^{i\frac{\pi}{4}}\sqrt{\frac{\pi}{4a}}\right) = \sqrt{\frac{\pi}{8a}}$$
# Problem 2
## 2.a)
I can rewrite the differential equation as such:
$$xy'' + (1-x)y' + \lambda y = 0$$
$$\Rightarrow y'' + \frac{1-x}{x}y' + \frac{\lambda}{x}y = y'' + \frac{b(x)}{x}y' + \frac{c(x)}{x^2}y = 0,$$
with $$b(x) = 1-x$$ and $$c(x) = \lambda x$$. Both $$b(x)$$ and $$c(x)$$ are analytic at $$x=0$$, so I have at least one solution on the Fröbenius form:
$$y(x) = x^s\sum_{n=0}^\infty a_nx^n.$$
Differentiating these gives
$$y'(x) = \sum_{n=0}^\infty a_n(n+s)x^{n+s-1},$$
$$y''(x) = \sum_{n=0}^\infty a_n(n+s)(n+s-1)x^{n+s-2}.$$
I now insert the above into the original differential equation:
$$x\sum_{n=0}^\infty a_n(n+s)(n+s-1)x^{n+s-2} + (1-x)\sum_{n=0}^\infty a_n(n+s)x^{n+s-1} + \lambda x^s\sum_{n=0}^\infty a_nx^n = 0$$
$$\Rightarrow \sum_{n=0}^\infty a_n(n+s)^2x^{n+s-1} - \sum_{n=0}^\infty a_n(n+s-\lambda)x^{n+s} = 0$$
The indicial equation is garnered by equating the lowest order term of the differential equation (in this case the term containing $$x^{s-1}$$) to $$0$$. This results in:
$$a_0s^2 = 0 \Rightarrow s = 0$$
## 2.b)
Using the above solution for $$s$$, I have
$$\sum_{n=0}^\infty a_nn^2x^{n-1} - \sum_{n=0}^\infty a_n(n-\lambda)x^{n} = 0.$$
Gathering the terms of the same order and equating the $$x^n$$-term to $$0$$, gives me the following relation
$$a_{n+1} (n+1)^2 - a_n(n-\lambda) = 0$$
$$\Rightarrow a_{n+1} = -\frac{\lambda - n}{(n+1)^2}a_n$$
## 2.c)
Calculating a few of the first terms with the above rule shows a pattern:
$$a_1 = -\frac{\lambda}{1^2}a_0 = (-1)^1\frac{\lambda}{(1!)^2}a_0,$$
$$a_2 = -\frac{\lambda - 1}{2^2}a_1 = (-1)^2\frac{\lambda(\lambda - 1)}{(2!)^2}a_0,$$
$$a_3 = -\frac{\lambda - 2}{3^2}a_2 = (-1)^3\frac{\lambda(\lambda - 1)(\lambda - 2)}{(3!)^2}a_0.$$
So generally:
$$a_n = (-1)^n\frac{\lambda(\lambda - 1)(\lambda -2)(\lambda -3)\overset{n\text{ times}}{\cdots}}{(n!)^2}a_0.$$
The coefficients $$a_{n > \lambda} = 0$$, because the numerator now evaluates to $$0$$. Assuming $$\lambda = N$$, which is an integer, I can now write the general form of the coefficient as:
$$a_n = (-1)^n\frac{N!}{(N - n)!(n!)^2}a_0,$$
which gives the [[Fröbenius]] solution as
$$y(x) = \sum_{n=0}^N(-1)^n\frac{N!}{(N - n)!(n!)^2}a_0x^n.$$
# Problem 3
## 3.a)
$$f(x)$$ is an [[Odd function]], which means there will be no cosines in the series (and also no $$a_0$$, since the function is not defined in $$x=0$$). 
$$f(x) = \sum_{n=1}^\infty b_n\sin\left(\frac{\pi nx}{L}\right)$$
Now let us calculate the coefficients $$b_n$$:
$$b_n = \frac{1}{L}\int_{-L}^L f(x)\cdot\sin\left(\frac{\pi nx}{L}\right)dx$$
$$= \frac{1}{2L}\left(\int^L_0(L-x)\cdot\sin\left(\frac{\pi nx}{L}\right)dx-\int_{-L}^0 (L+x)\cdot\sin\left(\frac{\pi nx}{L}\right)dx\right)$$
From antisymmetry $$f(-x) = -f(x)$$, so the two integrals equal eachother.
$$\Rightarrow b_n = \frac{1}{L}\int^L_0 (L-x)\cdot\sin\left(\frac{\pi nx}{L}\right)dx = \frac{L(\pi n - \sin(\pi n))}{\pi^2 n^2} = \frac{L}{\pi n},$$
and so the [[Fourier series]] of the function is:
$$f(x) = \frac{L}{\pi}\sum_{n=1}^\infty \frac{1}{n}\sin\left(\frac{\pi n x}{L}\right)$$
## 3.b)
I start by setting $$L = 1$$, which means I have the following expression for $$f(x)$$:
$$f(x) = \frac{1}{\pi}\sum_{n=1}^\infty\frac{\sin(\pi n x)}{n}.$$
Now I change the variable in $$f$$ to $$\chi = \frac{x}{\pi}$$ to get
$$f(\chi) = \frac{1}{\pi} \sum_{n=1}^\infty\frac{\sin(nx)}{n}$$
$$\Rightarrow \sum_{n=1}^\infty\frac{\sin(nx)}{n} = \pi f(\chi) = -\frac{1}{2}\bigg\{\begin{matrix}(\pi + x) & \text{for} & -1\le x < 0 \\ (x - \pi) & \text{for} & 0 < x \le 1\end{matrix}$$
# Problem 4
## 4.a)
![](assets/4a.png)
$$F(k) = \frac{1}{\sqrt{2\pi}}\left(\int_{-a}^0 2(a+x)e^{-ikx}dx + \int^a_02 (-x+a)e^{-ikx}dx\right)$$
$$= \frac{\sqrt 2a}{\sqrt \pi}\left(\int_{-a}^0e^{-ikx}dx + \int^a_0e^{-ikx}dx\right) + \sqrt \frac{ 2}{\pi}\left(\int^0_{-a}xe^{-ikx}dx - \int^a_0xe^{-ikx}dx\right)$$
$$= \frac{\sqrt 2a}{\sqrt \pi}\left(\int_{a}^0e^{ikx}dx + \int^a_0e^{-ikx}dx\right) + \sqrt \frac{ 2}{\pi}\left(\int^0_{a}(-x)e^{ikx}dx - \int^a_0xe^{-ikx}dx\right)$$
$$= \frac{4a}{\sqrt{2\pi}}\int^a_0\cos(kx)dx - \frac{4}{\sqrt{2\pi}}\int^a_0x\cos(kx)dx$$
$$=\frac{4a}{\sqrt{2\pi}k}\sin(ak) - \frac{4}{\sqrt{2\pi}k^2}\left(ak\sin(ak)+\cos(ak) - 1\right)$$
$$F(k) = \frac{4}{\sqrt{2\pi}k^2}(1-\cos(ak))$$
## 4.b)
Using the expression for $$F(k)$$ above, I get:
$$f(x) = \frac{1}{\sqrt{2\pi}}\int^\infty_{-\infty}F(k)e^{ikx}dk = \frac{2}{\pi}\int^\infty_{-\infty}\frac{1-\cos(ak)}{k^2}e^{ikx}dk$$
## 4.c)
Inserting the values of $$a = 1$$ and $$x = 0$$ into the function $$f(x)$$ and the expression above gives me:
$$f(0) = 2 = \frac{2}{\pi}\int^\infty_{-\infty}\frac{1-\cos k}{k^2}dk$$
Since the integrand $$\frac{1-\cos k}{k^2}$$ is an even function, I utilize the [[Parity|symmetry]] of it to split the integral into two equal integrals from $$0$$t to $$\infty$$:
$$2 = \frac{2}{\pi}\cdot 2\int^\infty_0\frac{1-\cos k}{k^2}dk$$
$$\Rightarrow \int^\infty_0\frac{1 - \cos k}{k^2}dk = \frac{\pi}{2}$$
# Problem 5
## 5.a)
I start by [[Laplace transform|Laplace transforming]] the [[Partial differential equation|PDE]] with regards to the time dependence:
$$\mathcal L\left\{\frac{\partial^2 u(x,t)}{\partial t^2}\right\} = c^2\mathcal L \left\{\frac{\partial^2 u(x,t)}{\partial x^2}\right\}$$
$$s^2\mathcal L \left\{u(x,t)\right\} - su(x,0) - \frac{\partial u(x,t)}{\partial t}\bigg|_{t=0} = c^2\mathcal L \left\{\frac{\partial^2 u(x,t)}{\partial x^2}\right\}$$
The initial conditions where $$t = 0$$ are known to equal $$0$$, and thus
$$s^2\mathcal L\left\{u(x,t)\right\} = c^2\mathcal L \left\{\frac{\partial^2 u(x,t)}{\partial x^2}\right\} = c^2\cdot \int^\infty_0 e^{-st}\cdot \frac{\partial^2 u(x,t)}{\partial x^2}dt$$
$$s^2\mathcal L\left\{u(x,t)\right\} = c^2 \frac{\partial^2}{\partial x^2}\cdot \int^\infty_0 e^{-st}u(x,t)dt = c^2\frac{\partial^2}{\partial x^2}\mathcal L\left\{u(x,t)\right\}$$
Renaming $$\mathcal L\left\{u(x,t)\right\} = U(x,s)$$, I now end up with the following [[Ordinary differential equation|ODE]]:
$$\frac{\partial^2 U(x,s)}{\partial x^2} = \frac{s^2}{c^2}U(x,s)$$
This equation is easily solved generally by utilizing the characteristic equation
$$r^2 - \frac{s^2}{c^2} = 0 \Rightarrow r = \pm \frac{s}{c}$$
$$\Rightarrow U(x,s) = A(s)e^{\frac{sx}{c}} + B(s)e^{-\frac{sx}{c}}$$
## 5.b)
The [[Laplace transform]] $$U(x,s)$$ has to apply to the same boundary conditions as $$u(x,t)$$ (with regards to $$x$$ of course). Applying them will give me expressions for $$A(s)$$ and $$B(s)$$.
$$\lim_{x\rightarrow\infty} u(x,t) = \lim_{x\rightarrow\infty} U(x,s) = \lim_{x\rightarrow\infty}A(s)e^{\frac{sx}{c}} + B(s)e^{-\frac{sx}{c}} = 0.$$
The term $$e^{\frac{sx}{c}}$$ tends to infinity as $$x\rightarrow\infty$$, and thus $$A(s) = 0$$. The second boundary condition is a bit more difficult as it is a function itself. With the function
$$g(t) = \bigg\{\begin{matrix}\sin t, & 0 \le t < 2\pi \\ 0, & \text{otherwise}\end{matrix}$$
as the boundary condition for $$u(0,t)$$, the [[Laplace transform]] $$G(s) = \mathcal L\{g(t)\}$$ is the boundary condition for $$U(0,s)$$. Thus,
$$U(0, s) = B(s) = G(s),$$
and my final Laplace transformed function is
$$U(x,s) = e^{-\frac{sx}{c}}G(s).$$
The task gives us the shifting property $$\mathcal L\left\{f(t-a)H(t-a)\right\} = e^{-as}F(s)$$. Applying this backwards gives me an expression for $$u(x,t)$$:
$$u(x,t) = \mathcal L^{-1}\left\{U(x,s)\right\} = \mathcal L^{-1}\left\{e^{-\frac{x}{c}s}G(s)\right\} = g\left(t - \frac{x}{c}\right)H\left(t - \frac{x}{c}\right),$$
$$u(x,t) = \bigg\{\begin{matrix}\sin\left(t - \frac{x}{c}\right), & \frac{x}{c} \le t < \frac{x}{c} + 2\pi \\ 0, & \text{otherwise}\end{matrix}.$$
