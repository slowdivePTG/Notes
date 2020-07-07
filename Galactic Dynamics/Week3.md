# Week3: Potential Theory

Confronted with more complex dynamics of stars and galaxies, potential theory comes to the stage. 

## General Potential Theory

### Potential-density pair $\rho\Leftrightarrow \Phi$

The force that matter at position $\vec{x}'$ exerts on a test particle $m$ is
$$
\delta\vec{ F}(\vec{x}') = \frac{Gm\, \rho(\vec{x}') \text{d}^3 \vec{x}'
}{|\vec{x}' - \vec{x}|^3}(\vec{x}' - \vec{x}),
$$
Since we would like to study the gravitational field itself, a quantity without test particle involved is preferred. Thus, one can define the gravitational field (force per unit) to be:
$$
\vec{g}(\vec{x}) = \int \frac{\delta F}{m} = \int \frac{G\, \rho(\vec{x}') \text{d}^3 \vec{x}'
}{|\vec{x}' - \vec{x}|^3}(\vec{x}' - \vec{x}).
$$
Noticing that 
$$
\nabla_{\vec{x}}\left(\frac{1}{|\vec{x}' - \vec{x}|}\right) = \frac{\vec{x}' - \vec{x}}{|\vec{x}' - \vec{x}|^3},
$$
we have
$$
\vec{g}(\vec{x}) = \nabla_{\vec{x}} \int \text{d}^3 \vec{x}' \frac{G\rho(\vec{x}')}{|\vec{x}' - \vec{x}|},\\
$$
let 
$$
\Phi(\vec{x}) = -G \int \text{d}^3 \vec{x} \frac{\rho(\vec{x}')}{|\vec{x}' - \vec{x}|},
$$
we have
$$
\vec{g}(\vec{x}) = -\nabla_{\vec{x}} \Phi(\vec{x}) = -\nabla \Phi(\vec{x}).
$$



If we take the divergence of gravitational field $\vec{g}(\vec{x})$, we have:
$$
\nabla_{\vec{x}}\cdot \vec{g}(\vec{x}) = \int G\, \rho(\vec{x}') \text{d}^3\vec{x}' \, \nabla_{\vec{x}}\cdot \frac{\vec{x}' - \vec{x}}{|\vec{x}' - \vec{x}|^3}.
$$

Since we have
$$
\nabla_{\vec{x}}\cdot \frac{\vec{x}' - \vec{x}}{|\vec{x}' - \vec{x}|^3} = -\frac{3}{|\vec{x}' - \vec{x}|^3} + \frac{3(\vec{x}' - \vec{x})\cdot(\vec{x}' - \vec{x})}{|\vec{x}' - \vec{x}|^5},
$$
if $\vec{x}'\neq\vec{x}$, $\quad\nabla_{\vec{x}}\cdot \dfrac{\vec{x}' - \vec{x}}{|\vec{x}' - \vec{x}|^3}  = 0$. 

If $\vec{x}' = \vec{x}$, we have to find another way to calculate the divergence. 
$$
\begin{align*}
\nabla_{\vec{x}}\cdot \vec{g}(\vec{x}) &= G \int_{|\vec{x}'-\vec{x}|<h} \rho(\vec{x}')\, \nabla_{\vec{x}}\cdot \frac{\vec{x}' - \vec{x}}{|\vec{x}' - \vec{x}|^3}  \text{d}^3\vec{x}'\\
&= -G \int_{|\vec{x}'-\vec{x}|<h} \rho(\vec{x}')\, \nabla_{\vec{x'}}\cdot \frac{\vec{x}' - \vec{x}}{|\vec{x}' - \vec{x}|^3}  \text{d}^3\vec{x}'\\
&= -G\rho(\vec{x}) \int_{|\vec{x}'-\vec{x}|<h}   \frac{\vec{x}' - \vec{x}}{|\vec{x}' - \vec{x}|^3}  \text{d}^2\vec{S}'\ \quad (\lim h \to 0)\\
&= -4\pi G\rho(\vec{x}) 
\end{align*}
$$
The last integration corresponds to the total solid angle of a sphere (with radius $h$).

Since $\vec{g}(\vec{x}) = -\nabla_{\vec{x}} \Phi(\vec{x})$, thus
$$
\text{Poisson Equation:}\\
\nabla^2 \Phi(\vec{x}) = 4\pi G\rho(\vec{x}). 
$$

where the subscript $\vec{x}$ is omitted.

Integrate the Poisson Equation, we have the Gaussian Theorem (as an analogue of the Gaussian theorem of EM force):
$$
\int \nabla\Phi \cdot \vec{\text{d}S} = 4\pi GM.
$$


Given a distribution of matter $\rho(\vec{x})$ and a reasonable boundary condition, the gravitational potential $\Phi$ can be solved; and vice versa, given a potential and plug it in the equation above, you can get the matter density distribution. This is called the **potential-density pair**.



### Potential energy

Potential is a proxy for the gravitational field. We would like to obtain the gravitational potential energy of the system (the work that is done to separate/construct the system). Assume we add an infinitesimal test particle $\delta m$ into a field $\Phi(\vec{x})$, the change of potential energy is 
$$
\delta W = \Phi(\vec{x})\delta m = \int \Phi(\vec{x})\, \delta \rho\, \text{d}^3\vec{x}.
$$
In the meantime, according to Poisson Equation, we introduced a perturbation of density field, thus
$$
\nabla^2(\Phi+\delta\Phi) = 4\pi G(\rho+\delta \rho),\\
\nabla^2\delta\Phi = 4\pi G\delta\rho.
$$
Thus, 
$$
\begin{align*}
\delta W &= \int\Phi(\vec{x}) \delta \rho\ \text{d}^3\vec{x}\\
&= \frac{1}{4\pi G} \int\Phi(\vec{x})\ \nabla^2\delta\Phi\ \text{d}^3\vec{x}\\
&= \frac{1}{4\pi G} \int\Phi(\vec{x})\ \nabla\cdot\nabla\delta\Phi\ \text{d}^3\vec{x}\\
&= \frac{1}{4\pi G} \int\left[\nabla\cdot(\Phi\nabla\delta\Phi) - \nabla\Phi \cdot \nabla\delta\Phi\right] \ \text{d}^3\vec{x}.
\end{align*}
$$
Take the integral, the surface term (first term) vanished, hence
$$
\begin{align*}
\delta W &= -\frac{1}{4\pi G} \int \nabla\Phi \cdot \nabla\delta\Phi \ \text{d}^3\vec{x}\\
&= -\frac{1}{4\pi G} \int \nabla\Phi \cdot \delta\nabla\Phi \ \text{d}^3\vec{x}\\
&= -\frac{1}{8\pi G} \int \delta\left((\nabla\Phi)^2 \right) \ \text{d}^3\vec{x}\\
&= -\frac{1}{8\pi G} \delta \int (\nabla\Phi)^2 \ \text{d}^3\vec{x}.\\
\end{align*}
$$
Hence, the total potential energy of this system is:
$$
\begin{align*}
W &= -\frac{1}{8\pi G} \int (\nabla\Phi)^2 \ \text{d}^3\vec{x}\\
&= -\frac{1}{8\pi G} \int \nabla\Phi \cdot \nabla\Phi \ \text{d}^3\vec{x}\\
&= -\frac{1}{8\pi G} \int \left[\nabla\cdot(\Phi\nabla\Phi) - \Phi\nabla^2\Phi\right] \ \text{d}^3\vec{x}\\
&= \frac{1}{8\pi G} \int \Phi\nabla^2\Phi\ \text{d}^3\vec{x}\\
&= \frac{1}{2}\int \rho\,\Phi\ \text{d}^3\vec{x}.
\end{align*}
$$
Intuitively, $1/2$ comes from the redundant calculation when enumerating potential energies between every two stars. 

TBD: **Chandrasekhar potential-energy tensor** 



## Spherical System

For a spherical system, we have Newton's laws: 

1. A body that is inside a spherical shell of matter experiences no net gravitational force from that shell.
2. The gravitational force on a body that lies outside a spherical shell of matter is the same as it would be if all the shell’s matter were concentrated into a point at its center.

Thus, when calculating the potential at point $\vec{x} < R$, we have:
$$
\begin{align*}
\Phi(r) = &-G\int_0^r \frac{4\pi r'^2\rho(r')\text{d}r'}{r} [\text{as if every shell is at the center}] \\&- G\int_r^R \frac{4\pi r'^2\rho(r')\text{d}r'}{r'} [\text{the potential inside a shell is constantly }-\frac{G\text{d}m}{r'}].
\end{align*}
$$
And the gravitational field is
$$
\vec{g}(r) = -\int_0^r \frac{G\text{d}m}{r^2} = -\frac{GM(<r)}{r^2}.
$$
**Circular velocity** is defined as
$$
\frac{GM(<r)}{r^2} = \frac{v_c^2}{r},\quad v_c = \sqrt\frac{GM(<r)}{r}.
$$
**Circular frequency** is defined as
$$
\Omega = \frac{v_c}{r} = \sqrt{\frac{GM(<r)}{r^3}}.
$$
**Escape velocity** is defined as
$$
\frac{v^2}{2} + \Phi(r) = 0,\quad v_{\text{esc}}^2 = 2|\Phi(r)| \ \left(= \frac{2GM(<r)}{r}\right).
$$



### Homogeneous Sphere

Density is constant, thus
$$
v_c = \sqrt{\frac{4}{3}\pi G\rho}\ r,\\
T_c = \frac{2\pi r}{v_c} = \sqrt{\frac{3\pi}{G\rho}}.
$$
Another fun example is: if we dug a hole along the diameter of a homogeneous sphere, put a ball inside that hole from one end, what's the period of that ball?
$$
\ddot r = -\frac{GM(<r)}{r^2} = -\frac{4}{3}\pi G\rho \ r
$$
follows the form of harmonic oscillation. Thus the period is 
$$
P = \sqrt{\frac{3\pi}{G\rho}} \sim (G\rho)^{-1/2}.
$$
This time serves as a useful indicator, and is also called **dynamical time** of a system. 

The potential energy (binding energy) is well-known:
$$
W = -\frac{3}{5}\frac{GM^2}{R}.
$$
The potential goes as:
$$
\begin{align*}
\Phi(r>R) &= -\frac{GM(r=R)}{r},\\
\Phi(r<R) &= -4\pi G \int_0^r \frac{r'^2\rho\ \text{d}r'}{r} - 4\pi G\int_r^R \frac{ r'^2\rho\ \text{d}r'}{r'}\\
&= - 4\pi G \rho \frac{r^2}{3} - 4\pi G\rho \left(\frac{R^2}{2} - \frac{r^2}{2}\right)\\
&= -2\pi G\rho \left(R^2 - \frac{r^2}{3}\right).
\end{align*}
$$
When $r\ll R$, the potential is approximately constant, and goes to zero at large radii. Hence the homogeneous sphere model is a good approximation for a constant potential when $r$ is small.



### Plummer Sphere

We might expect that in many spherical systems the density is roughly constant near the center, and falls to zero at large radii. Plummer sphere is of this type:
$$
\Phi(r) = -\frac{GM}{\sqrt{r^2 + b^2}},
$$
where $M$ is the total mass.

We already discussed the potential-density pair, hence density can be calculated as
$$
\begin{align*}
\rho &= \frac{1}{4\pi G}\nabla^2\Phi = \frac{1}{4\pi G}\frac{1}{r^2}\frac{\text{d}}{\text{d}r}r^2\frac{\text{d}}{\text{d}r}\Phi\\
&= \frac{3Mb^2}{4\pi}\frac{1}{(r^2 + b^2)^{5/2}} = \frac{3M}{4\pi b^3}\left(1+\frac{r^2}{b^2}\right)^{-5/2}.
\end{align*}
$$
$$
\begin{align*}
r\to\infty &\Rightarrow \rho\sim r^{-5}\\
r\ll b &\Rightarrow \rho\sim\text{const}, \Phi\sim\text{const}.
\end{align*}
$$

Hence, $b$ is the core size of this sphere. 

Potential energy:
$$
\begin{align*}
W &= \frac{1}{2} \int \rho\Phi\ \text{d}V \\
&= -\frac{1}{2} \frac{GM}{b} \frac{3M}{4\pi b^3}\int_0^{\infty}\left(1+\frac{r^2}{b^2}\right)^{-3}4\pi r^2\text{d}r\\
&= -\frac{3\pi GM^2}{32b}.
\end{align*}
$$


### Isochrone potential

$$
\Phi(r) = -\frac{GM}{b+\sqrt{r^2 + b^2}}
$$



### Modified Hubble model

$$
I_h(R) = \frac{2j_0 a}{1+R^2/a^2}.
$$

It describes the projected surface density (or brightness), instead of the volume density.



### Power-law density model

$$
\rho(r) = \rho_0 \left(\frac{r_0}{r}\right)^{\alpha}
$$

#### Example: $\alpha=2$.

The circular velocity is a constant:
$$
v_c^2 = 4\pi G\rho_0 r_0^2.
$$
This model is also called <u>"singular isothermal"</u> model. 



### Two Power-law density model

$$
\rho(r) = \frac{\rho_0}{(r/a)^{\alpha} (1+r/a)^{\beta-\alpha}}.
$$

- Dehnen models: $\beta = 4$ (reasonable models of the centers of elliptical galaxies)
- Hernquist model: $\alpha =1,\ \beta=4$
- Jaffe model: $\alpha =2,\ \beta=4$

------


