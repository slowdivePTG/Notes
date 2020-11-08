# Chapter 2. Hydrostatic Equilibrium

**Approximation** - star ~ sphere (no special direction)

In this way, the stellar density $\rho$ is only a function of $r$ (and $t$ since the star evolves).

- **Mass shell**
  $$
  \text dm=4\pi \rho r^2\text dr\Rightarrow \frac{\partial m}{\partial r}=4\pi\rho r^2
  $$
  At given $t=t_0$, $m(r,t_0)$ is used for the radial coordinate
  $$
  \frac{\partial}{\partial r}=4\pi r^2\rho\frac{\partial}{\partial m}
  $$

## Gravity

The gravitational acceleration $g$ is given by
$$
g=-\frac{Gm}{r^2}
$$
where $G=6.67\times 10^{-8}$ in cgs units.

The gravitational field inside a star is given by a potential, which satisfies the Poisson equation
$$
\nabla^2\Phi=4\pi G\rho
$$
In a spherical system, we can rewrite it as
$$
\frac{1}{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial\Phi}{\partial r}\right)=4\pi G\rho
$$
And the total gravitational force onto a volume $V$ is
$$
\vec F_G=\int_V \rho\vec g\text dV
$$


## Pressure Gradient Force

The force onto a this mass shell per unit area $\text dS$ due to pressure is
$$
\vec f_P=-P\vec n\text dS
$$
Thus the pressure gradient force onto a unit volume is given by
$$
\vec F_P=-\oint P\vec n\text dS=-\int\nabla P\text dV
$$


## Hydrostatic Equilibrium

$$
0=\vec F_G+\vec F_p=\int\left(\rho \vec g-\nabla P\right)\text dV\Rightarrow -\frac1\rho \nabla P+\vec g=0
$$

Again, in a spherical system.
$$
\frac1\rho\frac{\partial P}{\partial r}=-\frac{Gm}{r^2}\iff\frac{\partial P}{\partial m}=-\frac{Gm}{4\pi r^4}
$$
This is known as the **hydrostatic equlibrium**, **one of the most important equations in astrophysics**.

- Estimate the central temperature of the Sun ($M_\odot=2\times 10^{33}$ g, $R_\odot=7\times10^{10}$ cm)

  First we estimate the central pressure $P_c$, by assuming
  $$
  \frac{\partial P}{\partial m}\sim\frac{P_0-P_c}{M_\odot}\sim -\frac{G\left(M_\odot/2\right)}{4\pi \left(R_\odot/2\right)^4}
  $$
  Here we adopt the median values of $m$ and $r$. $p_0\sim 0$ is the surface pressure. Thus
  $$
  P_c\sim\frac{2GM_\odot^2}{\pi R_\odot^4}
  $$
  Further assuming the ideal gas EoS
  $$
  P_c=\frac{\rho_ck_BT_c}{\mu m_\text{p}}
  $$
  where $\mu\approx 0.5$ is the mean molecular weight (ionized Hydrogen), thus the central temperature is
  $$
  k_BT_c\sim\frac{2\mu m_\text{p}GM_\odot^2}{\pi \rho_c R_\odot^4}
  $$
  Since $\rho_c>\bar\rho$, we have
  $$
  k_BT_c<\frac{8 GM_\odot}{3 R_\odot}\mu m_\text{p}\sim 3\text{ keV}
  $$
  which means $T_c<3\times10^7$ K.

  Currently the most updated value is $T_c\simeq1.6\times10^7$ K, so our estimation is not bad.

So far, the acceleration of mass shells is neglected.

The EoM (only radial motion is considered) is give by
$$
\frac{\partial^2 r}{\partial t^2}=-\frac1\rho\frac{\partial P}{\partial r}-\frac{Gm}{r^2}
$$

- If there is no pressure
  $$
  \frac{\partial^2 r}{\partial t^2}=-\frac{Gm}{r^2}\equiv\frac{r}{t_\text{ff}^2}\Rightarrow t\sim t_\text{ff}\equiv\sqrt{\frac{r^3}{Gm}}\sim\frac1{\sqrt{G\rho}}
  $$
  $t_\text{ff}$ is known as the **free-fall timescale**.

- If there is no gravity
  $$
  \frac{r}{t_\text{sc}^2}\equiv\frac{1}{\rho}\frac{P}{r}\Rightarrow t_\text{sc}\equiv\frac{r}{\sqrt{P/\rho}}\sim \frac{r}{c_s}
  $$
  $t_\text{sc}$ is known as the **sound-crossing timescale**, since $c_s$ is the **sound speed**.

Therefore, hydrostatic equilibrium requires
$$
t_\text{ff}\simeq t_\text{sc}
$$
This is generally satisfied in stellar interior.