# Chapter 13. Star Formation

Generally speaking, stars come from molecular clouds which cannot support their self-gravity and collapse. Typical physical parameters for a molecular cloud and a star are listed below.

|                                            | Molecular Cloud                | Star                                                         |
| ------------------------------------------ | ------------------------------ | ------------------------------------------------------------ |
| Size                                       | $\sim1\text{ pc}$              | $\sim R_\odot$                                               |
| Density                                    | $\sim10^2-10^4\text{ cm}^{-3}$ | $\sim 1\text{ g/cm}^3$ in mass ($\sim10^{24}\text{ cm}^{-3}$) |
| Free-fall timescale ($\sim1/\sqrt{G\rho}$) | Myrs                           | Minutes                                                      |

In a word, star formation is multi-scales and interdisciplines physics, a combination of MHD, radiation physics, and astrochemistry.



## Jeans Instability

For stars we assume hydrostatic equilibrium, that is, the free-fall timescale and the sound-crossing timescale are comparible, $t_\text{ff}\sim t_\text{sc}$. But for a collapsing system, $t_\text{ff}\ll t_\text{sc}$, where pressure is negligible.

Let us take a look at the EoM,
$$
\frac{\partial^2 r}{\partial t^2}=\frac1\rho\frac{\partial P}{\partial r}-\frac{GM(r)}{r^2}<0
$$
The first term on the RHS is approximately $c_s^2/r$, while the second is roughly $G\rho r$. As long as
$$
r>\frac{c_s}{\sqrt{G\rho}}\iff t_\text{ff}<t_\text{sc}
$$
the cloud starts to collapse. Here we define **Jeans length** $\lambda_J$
$$
\lambda_J\equiv\frac{c_s}{\sqrt{G\rho}}
$$
to mark the onset of instability/hydrodynamics. For $r>\lambda_J$, self-gravity dominates.

We now estimate the Jeans length for a typical molecular cloud
$$
\lambda_J\sim3\text{ pc}\left(\frac{T}{10\text{ K}}\right)^{1/2}\left(\frac{n}{100\text{ cm}^{-3}}\right)^{-1/2}
$$
For $n\sim10^2-10^4\text{ cm}^{-3}$, $\lambda_J\sim\text{ pc}$, which is the upper limit for the size of a molecular cloud.

Accordingly we can define **Jeans radius** $M_J$
$$
M_J\sim\rho J^3\sim50M_\odot\left(\frac{T}{10\text{ K}}\right)^{3/2}\left(\frac{n}{100\text{ cm}^{-3}}\right)^{-1/2}
$$

The rigorous derivation starts with perturbing an isothermal hydrostatical system
$$
\frac{\partial \rho}{\partial t}+\nabla\cdot(\rho\vec v)=0
$$

$$
\frac{\partial \vec v}{\partial t}+(\vec v\cdot\nabla)\vec v=-\frac1\rho\nabla P-\nabla\Phi
$$

$$
\nabla^2\Phi=4\pi G\rho
$$

$$
P=\rho c_s^2
$$

where $c_s$ is a constant. If we use the index 0 and 1 to denote unperturbed quantities and corresponding linear perturbation (that is, for quantity $Q$, $Q=Q_0+Q_1$, where $Q_0$ is a constant throughout the region we are interested in, while $Q_1\ll Q_0$), to the leading order, these equations can be rewritten as
$$
\frac{\partial \rho_1}{\partial t}+\rho_0\nabla\cdot\vec v_1=0
$$

$$
\frac{\partial \vec v_1}{\partial t}=-\frac{c_s^2}\rho_0\nabla \rho_1-\nabla\Phi_1
$$

$$
\nabla^2\Phi_1=4\pi G\rho_1
$$

Note that the initial velocity $v_0=0$. Then
$$
\Rightarrow\frac{\partial }{\partial t}(\nabla\cdot\vec v_1)=-\frac{c_s^2}{\rho_0}\nabla^2 \rho_1-4\pi G\rho_1
$$

$$
\Rightarrow\left(\frac{\partial^2}{\partial t^2}-c_s^2\nabla^2\right)\rho_1=4\pi G\rho_0\rho_1
$$

This is a typical wave equation. The simpliest form of solution is known as the **plane wave solution**, which describes the wave propogation in one dimension.
$$
\delta Q=A\exp\left[i\left(\vec k\cdot\vec r+\omega t\right)\right]
$$
And for 1-D case, the equation for $\rho_1$ above can be simplified as
$$
\omega^2=c_s^2k^2-4\pi G\rho_0
$$
which gives the **dispersion relation**.

- For $k>k_J\equiv\sqrt{4\pi G\rho_0}/c_s$ (*small scale*), $\omega^2$ is positive, thus the perturbation is stable. In fact, pressure wave is produced in this way.
- For $k<k_J$ (*large scale*), $\omega=i\sigma$, where $\sigma\in \mathcal R^+$. So $\delta Q\propto\exp(\pm\sigma t)$, which are the **growing mode** and **decaying mode** respectively. The decaying mode is soon damped, while the growing mode would finally destroy the linear perturbation assumption and marks the onset of instability.

Since $k_J$ is a typical wave number, we define **Jeans length** as the corresponding wave length,
$$
\lambda_J\equiv\frac{2\pi}{\lambda_J}=\sqrt{\frac{\pi}{G\rho_0}}c_s=\sqrt\pi c_st_\text{ff}\simeq0.04\text{ pc}\left(\frac T{10\text{ K}}\right)^{1/2}\left(\frac{\rho_0}{10^{-19}\text{ g/cm}^3}\right)^{-1/2}
$$
and the **Jeans mass** as
$$
M_J\equiv\frac43\pi\left(\frac{\lambda_J}{2}\right)^3\rho_0\simeq2M_\odot\left(\frac T{10\text{ K}}\right)^{3/2}\left(\frac{\rho_0}{10^{-19}\text{ g/cm}^3}\right)^{-1/2}
$$
The **unstable condition** is $r>\lambda_J$, where $r$ is the typical scale of the system.

For polytropic EoS, $T\propto\rho^{\gamma-1}$,
$$
\Rightarrow M_J\propto T^{3/2}\rho^{-1/2}\propto\rho^{\frac32(\gamma-4/3)}
$$
For a system of the mass $M\gtrsim M_J$, if $\gamma>4/3$, increasing $\rho$ gives increasing $M_J$. But initially $M$ is only slightly larger than $M_J$, so the collapse soon stops. If $\gamma<4/3$, however, the $M_J$ further decreases as the collapses goes on. On the other hand, the free-fall timescale goes down, making the collapse timescale shorter and shorter. As a result, the system undergoes runaway collapse. So only for systems of which $\gamma<4/3$, $M>M_J$ is the **collapse criterion**.



## Different Geometry in Molecular Cloud

Let's consider a gas **filament** (of which the radial size $R$ is much smaller than the length $l$ ) with a constant line mass
$$
\mu=\frac{M_\text{tot}}l
$$
and we only consider the radial collapse (two-dimensional collapse) so that the filament gets thinner ($R$ decreases) while $l$ is fixed. Again, whether the collapse will start depends on the battle of the gravitational force and the pressure gradient force. First let us calculate the gravitational force at the surface of a filament.
$$
4\pi G\iiint\rho\text dV=\iiint\nabla^2\Phi\text dV=\oiint\nabla\Phi\cdot\text d\vec S=-\oiint \vec F_\text{g}\cdot\text d\vec S
$$
Due to the cylindrical symmetry,
$$
\Rightarrow 4\pi G \mu l=F_\text g\cdot2\pi Rl\Rightarrow F_\text g\propto R^{-1}
$$
The pressure gradient force is
$$
F_P\propto\frac1\rho\frac{P}{R}\propto\frac{\rho^{\gamma-1}}{R}\propto\frac{\left(\mu/R^2\right)^{\gamma-1}}{R}\propto R^{1-2\gamma}
$$

$$
\Rightarrow \frac{F_\text g}{F_P}\propto R^{2(\gamma-1)}
$$

So for the filamentary structure, the critical $\gamma_\text{crit}\equiv1$.

Similarly we can also consider a gas **sheet** with a fixed surface density $\Sigma$. The collapse is one-dimensional (the thickness of the sheet $h$ decreases). The gravitational force is given by
$$
4\pi G\Sigma r^2=F_\text g\cdot 2\pi r^2\Rightarrow F_\text g\propto h^0
$$
And the pressure gradient force is
$$
F_P\propto\frac{\rho^{\gamma-1}}{h}\propto\frac{\left(\Sigma/h\right)^{\gamma-1}}{h}\propto h^{-\gamma}
$$

$$
\Rightarrow \frac{F_\text g}{F_P}\propto R^\gamma
$$

Surprisingly, the critical $\gamma$ is $0$.

