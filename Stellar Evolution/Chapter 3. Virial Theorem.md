# Chapter 3. Virial Theorem

In a star, where hydrostatic equilibrium is achieved, two important energy reservoirs are connected,
$$
\text{Gravitational energy }\sim\text{ Internal energy}
$$

## Derivation

Starting from
$$
\frac{\partial P}{\partial m}=-\frac{Gm}{4\pi r^4}
$$

$$
\Rightarrow \int_0^M 4\pi r^3 \frac{\partial P}{\partial m}\text dm=-\int_0^M \frac{Gm}{r}\text dm
$$

### Internal Energy

$$
\begin{align*}
LHS&=\int_{P_c}^{P_0}4\pi r^3\text dP\\
&=\left(4\pi r^3 P\right)\bigg|_{P_c}^{P_0}-3\int_{0}^{R}4\pi r^2p\text dr\\
&=4\pi R^3P_0-3\int_0^V P\text dV
\end{align*}
$$

In normal cases (main sequence stars), $P_0=0$.

>For an evolved star, the stellar core is embedded in an envelope. At the surface of the star, $p_0\neq0$.

Thus
$$
\begin{align*}
LHS&=-3\int_0^V P\text dV=-3\int_0^M\frac{P}{\rho}\text dm
\end{align*}
$$

### Gravitational Energy

The RHS can be interpreted as the gravitational potential energy.
$$
RHS=-\int_0^M\frac{Gm}{r}\text dm\equiv E_g<0
$$
The gravitational energy is always negative.

### Virial Theorem

Thus if we combine the LHS and the RHS, we obtain the **virial theorom**
$$
-3\int_0^M\frac{P}{\rho}\text dm=E_\text g
$$
Recall that we have only two assumptions

- **spherical gas**
- **hydrostatic equilibrium**

without considering any detail of the gas.

If we further assume **ideal gas EoS**
$$
P=\frac{\rho k_BT}{\mu m_p}
$$

$$
\Rightarrow \frac{P}{\rho}=\frac{k_B T}{\mu m_p}=\left(c_P-c_V\right)T=\left(\gamma-1\right)c_VT
$$

where $c_P$ and $c_V$ are **specific heat capacity at constant pressure** and **volume**, respectively. For ideal gas, the second equation was derived by *Julius von Mayer* and is known as [Mayer's relation](https://en.wikipedia.org/wiki/Mayer%27s_relation). $c_P$ and $c_V$ are related by
$$
c_P=\gamma c_V
$$
where $\gamma$ is the **heat capacity ratio**, as well as the **adiabatic index**. $\gamma=5/3$ for mono-atomic gas.

Finally, the **specific internal energy** for ideal gas is simply
$$
e=c_VT
$$
Therefore
$$
\frac{P}{\rho}=\left(\gamma-1\right)e
$$
And the virial theorem can be expressed as
$$
-E_\text g=3\left(\gamma-1\right)\int_0^Me\text dM=3(\gamma-1)E_\text{int}
$$
where $E_\text{int}$ corresponds to the **total internal energy within a star**.

> For $\gamma=5/3$, $E_\text{int}=-E_\text g/2$.

Virial theorem directly links the total gravitational energy to the total internal energy of a star without knowing its detailed internal structure. Consider a more tightly bound star, whose $E_\text g$ is more negative, then it must be hotter to obtain corresponding internal energy.

- Now we can revisit the temperature of the Sun.
  $$
  E_\text g=-\alpha\frac{GM^2_\odot}{R_\odot},\quad \alpha\sim\mathcal O(1)
  $$

  $$
  E_\text{int}=\frac32\frac{k_B}{\mu m_p}\int_0^MT\text dm\equiv \frac32\frac{k_B}{\mu m_p}\bar T
  $$

  So the **mean** temperature of the Sun is
  $$
  \bar T=-\frac{2}{3}\frac{\mu m_p}{k_B}\frac{E_\text g}{3(\gamma-1)}=\frac{2\alpha}{9(\gamma-1)}\frac{\mu m_p}{k_B}\frac{GM_\odot}{R_\odot^2}
  $$
  Given $\gamma=5/3$ and $\alpha\sim1$, $\bar T\sim4\times10^6$ K.



### Total Energy

$$
E_\text{tot}=E_\text g+E_\text{int}=(4-3\gamma)E_\text{int}=\frac{4-3\gamma}{3(1-\gamma)}E_\text g
$$

- If $\gamma=5/3$, $E_\text{tot}=E_\text g/2<0$, so the star is safely bound.
- If $\gamma\to4/3+$ (slightly over $4/3$), $E_\text{tot}$ is only sightly below zero, and the star is **weakly bound**.
  - For a massive star, where radiation pressure dominates, $\gamma\sim4/3$.
  - For cases where relativistic degenerate electron pressure donimates, such as a relativistic white dwarf, $\gamma\sim4/3$.
  - $\gamma=4/3$ is one critical condition for the onset of star formation, or in other word, the onset of hydrodynamics.



## Kelvin-Helmholtz Mechanism

Let us consider a contracting star (fix the mass and lower the radius).

If the contracting timescale is long enough, the star can still be well approximated by hydrostatic equilibrium. In this way the energy loss rate in a unit time, that is, the **luminosity**, is given by
$$
\begin{align*}
L&=-\frac{\text dE_\text{tot}}{\text dt}\\
&=-\frac12\frac{\text dE_\text{g}}{\text dt}\quad (\gamma=5/3)\\
&=-\frac12\frac{\text dE_\text{g}}{\text dR}\frac{\text dR}{\text dt}
\end{align*}
$$
while
$$
\frac{\text dE_\text{int}}{\text dt}=-\frac12\frac{\text dE_\text{g}}{\text dt}>0
$$
So **half** of the **gravitational energy loss** is used for **providing luminosity $L$**. The other half is used to **increase the internal energy (temperature)**. In other words, energy loss promotes $T$.
$$
\Rightarrow \Delta E_\text{tot}=-\Delta E_\text{int}=-\frac32\frac{k_B}{\mu m_p}M\Delta T\equiv C\Delta T
$$
The heat capacity is **negative**!

Now we can estimate the time it takes for the gravitational energy released by this so-called **Kelvin-Holmholtz mechanism** to be carried to the surface
$$
t_\text{KH}=\frac{\left|E_\text g\right|}{L}\sim\frac{GM^2}{2RL}
$$
This timescale is known as the **Kelvin-Helmholtz timescale**.

- KH timescale for the sun
  $$
  t_\text{KH}\equiv\frac{GM^2_\odot}{2R_\odot L_\odot}\sim10^7\text{ s}
  $$
  The free-fall timescale $t_\text{ff}$ is $\sim 10^3$ s, so the Sun achieves hydrostatic equilibrium quickly, and our former approximation is reasonable.

- KH timescale for star formation

  Originally we have a molecular cloud with typical number density $\bar n\sim 10^4$ cm$^{-3}$.
  $$
  t_\text{ff}=\frac{1}{\sqrt{G\rho}}=\frac{1}{\sqrt{G\bar nm_p}}\sim1\text{ Myr}
  $$
  So mostly within the free-fall time, the molecular cloud is dominated by hydrodynamics, until it reaches a stage where the density gets higher and the contraction slows down. It then becomes **quasi-hydrostatic**, when the Kelvin-Helmholtz mechanism starts to dominate. The KH timescale is about $10^7$ yr. As the contraction goes on, the temperature keeps rising. This quasi-hydrostatic state halts when the central temperature $T_c\sim10^7$ K, high enough to trigger nuclear burning.