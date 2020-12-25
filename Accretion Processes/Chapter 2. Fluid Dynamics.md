# Chapter 2. Fluid Dynamics

## Fluid Approximation

The fluid approximation is valid when the system size $L$ is much larger than the mean free path $l_\text{mfp}$.

- For ISM (interstellar medium), the typical mean free path is
  $$
  l_\text{mfp}\sim 10^{15}\text{cm}\left(\frac{n}{1\text{ cm}^{-3}}\right)^{-1}\left(\frac{d}{1\ \AA}\right)^{-2}
  $$

Inside each fluid particle, we can define thermal dynamical quantities, $T,\rho,P,S$, as well as a velocity field $\vec v(\vec x,t)$.

For any quantity of the fluid element at $(\vec r_0,t_0)$, say $F(\vec r_0,t_0)$, we have
$$
\begin{align*}
\Delta F&=F\left(\vec r_0+\vec v(\vec r_0)\Delta t,t_0+\Delta t\right)-F(\vec r_0,t_0)\\
&=\left(\frac{\partial F}{\partial t}+v_x\frac{\partial F}{\partial x}+v_y\frac{\partial F}{\partial y}+v_z\frac{\partial F}{\partial z}\right)\Delta t+\mathcal O(\Delta t^2)
\end{align*}
$$
In fact, we can write the derivative of $F$
$$
\lim_{\Delta t\to 0}\frac{\Delta F}{\Delta t}
$$
in two different ways

- **Lagrange's derivative**
  $$
  \frac{\text DF}{\text Dt}
  $$
	which follows the fluid element everywhere.
	
- **Eulerian derivative**
  $$
  \left(\frac{\partial}{\partial t}+\vec v\cdot \nabla\right) F
  $$
  which is more important for numerical calculations, as it considers only fixed fluid cells.



## Equation of Continuity - Mass Conservation

- In **Eulerian picture**

  For a small, fixed volume $\delta V_0$, in a time span of $\Delta t$, the change in mass inside is
  $$
  \delta m=\Delta t\cdot\frac{\text d}{\text dt}\left(\iiint_{\delta V_0}\rho\text dV_0\right)
  $$
  Consider the **mass flow** at the surface
  $$
  \vec j=\Delta t\oiint_{\delta S}\left(\vec v\cdot\vec n\right)\rho\text dS=\Delta t\iiint_{\delta V_0}\nabla\cdot\left(\rho\vec v\right)\text dV_0
  $$
  where we have applied Gauss' divergence theorem. Here $\vec n$ is the normal vector of the surface.

  If there are no source/sink of mass within the fluid element, the mass flow should exactly account for the change in mass
  $$
  \frac{\text d}{\text dt}\left(\iiint_{\delta V_0}\rho\text dV_0\right)+\iiint_{\delta V_0}\nabla\cdot\left(\rho\vec v\right)\text dV_0=0
  $$
  Since we have fixed $\Delta V$, we can write this formula so that for any $\Delta V_0$
  $$
  \iiint_{\delta V_0}\left(\frac{\partial \rho}{\partial t}+\nabla\cdot\left(\rho\vec v\right)\right)\text dV_0=0
  $$
  The arbitrariness of the choice of $\Delta V$ directly leads to the famous **equation of continuity**
  $$
  \frac{\partial \rho}{\partial t}+\nabla\cdot\left(\rho\vec v\right)=0
  $$

- In **Lagrange's picture**

  Let us consider a volume element $\delta V$ that moves with fluid particles.

  If no mass creation / annihilation
  $$
  0=\frac{\text D(\delta m)}{\text Dt}=\frac{\text D}{\text Dt}\left(\rho\delta V\right)=\frac{\text D\rho}{\text Dt}\delta V+\rho\frac{\text D}{\text Dt}\left(\delta V\right)
  $$

  $$
  \Rightarrow
  \frac{\text D\rho}{\text Dt}=-\frac{\rho}{\delta V}\frac{\text D}{\text Dt}\left(\delta V\right)=-\rho\sum_{i}\frac{1}{\delta x_i}\frac{\text D\left(\delta x_i\right)}{\text Dt}=-\rho\left(\nabla\cdot \vec v\right)
  $$

  Recall that
  $$
  \frac{\text D}{\text Dt}=\frac{\partial}{\partial t}+\vec v\cdot \nabla
  $$
  Then
  $$
  \left(\frac{\partial}{\partial t}+\vec v\cdot \nabla+\nabla\cdot\vec v\right)\rho=0\Rightarrow\frac{\partial\rho}{\partial t}+\nabla\cdot\left(\rho\vec v\right)=0
  $$

Two pictures give exactly the same equation!

Now we further explore the relation between two pictures. In the Lagrange's picture,
$$
\delta V=\text dx\cdot\text dy\cdot\text dz
$$
while in the Eulerian picture
$$
\delta V_0=\text d\xi_x\cdot\text d\xi_y\cdot\text d\xi_z
$$
$\delta V$ and $\delta V_0$ are related as follows,
$$
\delta V=\left|\frac{\partial\left(x,y,z\right)}{\partial\left(\xi_x,\xi_y,\xi_z\right)}\right|\delta V_0\equiv J\delta V_0
$$
The ratio $J$ is called the **expansion** of the fluid. **Euler's expansion formula** claims that
$$
\frac{\text DJ}{\text Dt}=\left(\nabla \cdot \vec v\right)J
$$
Then if we reconsider the conservation of mass in Lagrange's picture,
$$
\frac{\text D}{\text Dt}\iiint_{\delta V}\rho\text{d}V=0
$$

$$
\iff 0=\frac{\text D}{\text Dt}\iiint_{\delta V}\rho J\text{d}V_0=\iiint_{\delta V}\left[\frac{\text D \rho}{\text Dt}+\rho\left(\nabla\cdot \vec v\right)\right]J\text dV_0
$$

which also gives the continuity formula
$$
\frac{\text D \rho}{\text Dt}+\rho\left(\nabla\cdot u\right)=0
$$
Before moving to the next section, we can similarly derive several useful identities of the Lagrange's derivative.

For a function $F$,
$$
\frac{\text D }{\text Dt}\iiint_VF\text dV=\frac{\text D }{\text Dt}\iiint_VFJ\text dV_0=\iiint_V\left[\frac{\text D F}{\text Dt}+\left(\nabla \cdot \vec v\right)F\right]J\text dV_0=\iiint_V\left[\frac{\text D F}{\text Dt}+\left(\nabla \cdot \vec v\right)F\right]\text dV
$$

$$
\iff \frac{\text D }{\text Dt}\iiint_VF\text dV=\iiint_V\left[\frac{\partial F}{\partial t}+\nabla\cdot\left(F \vec v\right)\right]\text dV
$$

This is known as the **Reynolds transport theorem**. Simply let $F=\alpha\rho$, we have
$$
\begin{align*}
\frac{\text D }{\text Dt}\iiint_V\alpha\rho\text dV&=\iiint_V\left[\frac{\text D }{\text Dt}\left(\alpha\rho\right)+\left(\nabla \cdot \vec v\right)\alpha\rho\right]\text dV\\
&=\iiint_V\left\{\alpha\left[\frac{\text D \rho}{\text Dt}+\left(\nabla \cdot \vec v\right)\rho\right]+\rho\frac{\text D\alpha}{\text Dt}\right\}\text dV\\
&=\iiint_V\rho\frac{\text D\alpha}{\text Dt}\text dV
\end{align*}
$$
This identity is extremely useful in the following chapters.



## Euler Equation - Momentum Conservation

In the Lagrange's picture, the acceleration onto a mass element is given by
$$
\frac{\text D}{\text Dt}\iiint_{V(t)}\rho\vec v\text dV=\iiint_{V(t)}\rho\frac{\text D\vec v}{\text Dt}\text dV
$$
With the Reynolds transport theorem, the EoS thus gives
$$
\iiint_{V(t)}\rho\frac{\text D\vec v}{\text Dt}\text dV=\iiint_{V(t)}\vec f\text dV+\oiint_{S(t)}\vec t\text dS
$$

- First term - body force (e.g gravity)
- Second term - surface force (e.g. pressure)

Consider the $i$-th component of the RHS
$$
\iiint_{V(t)}f^i\text dV+\oiint_{S(t)}t^i\text dS=\iiint_{V(t)}f^i\text dV+\oiint_{S(t)}T^{ij}n_j\text dS=\iiint_{V(t)}\left(f^i+\partial_jT^{ij}\right)\text dV
$$
where $\mathcal T$ is the **stress tensor**, which satisfies
$$
t^i=T^{ij}n_j
$$

An important surface force is pressure.

The force caused by pressure is
$$
\vec F_p=-\iint_S p\vec n\text dS=-\iiint_V\nabla p\text dV
$$
- **Pressure and Stress Tensor**

  If the $i$-th component
  $$
  -\partial_i p=\partial_j T^{ij}
  $$
  Thus $p$ is strongly correlated with the diagonal components in $\mathcal T$.

Since the choice of $V$ is arbitrary, the EoM is expressed as
$$
\rho\frac{\text D\vec v}{\text Dt}=-\nabla p+\vec f
$$

$$
\iff \frac{\partial \vec v}{\partial t}+\left(\vec v\cdot \nabla\right)\vec v=-\frac1\rho\nabla p+\frac1\rho\vec f
$$

which is the famous **Euler equation** for ideal fluid.

Using the equation of continuity and the Euler equation, we can calculate the time derivative of **mass flux**
$$
\begin{align*}
\frac{\partial}{\partial t}\left(\rho v^i\right)&=v^i\frac{\partial\rho}{\partial t}+\rho\frac{\partial v^i}{\partial t}\\
&=-v^i\partial_j\left(\rho v^j\right)-\rho v^j\partial_jv^i-\partial_j\delta^{ij}p\\
&=-\partial_j\left(\rho v^iv^j+\delta^{ij}p\right)\\
&\equiv -\partial_j\Pi^{ij}
\end{align*}
$$
So in the Eulerian picture, the **momentum conservation** is
$$
\frac{\partial}{\partial t}\left(\rho v^i\right)+\partial_j\Pi^{ij}=0
$$
Integrate the above equation over a fixed volume $V$
$$
\begin{align*}
\frac{\text d}{\text dt}\iiint_V\rho v^i\text dV&=-\iiint\partial^i p\text dV-\iiint\partial_j\left(\rho v^iv^j\right)\text dV\\
&=-\oiint_Spn^i\text dS-\oiint_S\rho v^iv^jn_j\text dS
\end{align*}
$$

- First term - thermal pressure
- Second term - ram pressure



## Equation of State: $f(\rho,p,T)=0$

Two independent quantities are necessary to characterize thermal states.

- Ideal gas
  $$
  p=\frac{\rho k_BT}{\mu m_p}
  $$

- Adiabatic gas
  $$
  p=K\rho^\gamma,\quad \gamma=\frac{c_p}{c_V}
  $$
  The adiabatic index $\gamma=5/3$ for mono-atomic gas.

> Ideal + adiabatic is an example of polytropic EoS
>
> If $p=f(\rho)$, the EoS is known as **barotropic**.

For inviscid fluid
$$
\frac{\text Ds}{\text Dt}=\frac{\partial s}{\partial t}+\left(\vec v\cdot \nabla\right)s=0
$$
that is, entropy doesn't change along each fluid stream line.

Furthermore, if $s=const$ everywhere at $r=r_0$, and $s=const$ is preserved, the. motion is known as **isentropic motion**.



## Bernoulli's theorem

In general, we would like to derive the energy conservation with Euler equation with certain assumptions

- Barotropic EoS: $\rho=f(p)$, thus the specific enthalpy is simply
  $$
  h(p)\equiv\int\frac{\text dp}{\rho(p)}
  $$

- Potential force: $\vec f=-\rho\nabla \phi$

Then we can rewrite Euler equation
$$
\frac{\partial \vec v}{\partial t}+\left(\vec v\cdot \nabla\right)\vec v=-\frac1\rho\nabla p-\nabla\phi
$$

$$
\Rightarrow \frac{\partial \vec v}{\partial t}+\nabla\left(\frac12v^2+h+\phi\right)=\vec v\times\vec\omega
$$

where the **vorticity** is defined as
$$
\vec\omega=\nabla\times\vec v
$$
and we have applied the identity
$$
\vec v\times\left(\nabla\times\vec v\right)=\left(\nabla\cdot\vec v\right) \vec v-\left(\vec v\cdot\nabla\right) \vec v=\frac12\nabla v^2-\left(\vec v\cdot\nabla\right) \vec v
$$

- For steady flow
  $$
  \frac{\partial u}{\partial t}=0
  $$
  thus
  $$
  \vec v\cdot\nabla\left(\frac12v^2+h+\phi\right)=\vec v\cdot\left(\vec v\times\vec\omega\right)=0
  $$
  which means $\frac12v^2+h+\phi$ is conserved along each streamline.

- No vorticity
  $$
  \nabla\times \vec v=0\Rightarrow \vec v=-\nabla\psi
  $$
  thus
  $$
  \frac{\partial\psi}{\partial t}+\frac12v^2+h+\phi=F(t)
  $$
  and $\nabla F(t)=0$.

- Steady & no vorticity
  $$
  \frac{\partial \psi}{\partial t}=0
  $$
  Then $\frac12v^2+h+\phi$ remains a constant everywhere.



## Energy Conservation

For fluid dynamics, the energy change in a unit time is given by
$$
\frac{\text D}{\text D t}\iiint_{V(t)}\rho\left(e+\frac12 v^2\right)\text dV=\iiint_{V(t)}\vec f\cdot\vec v\text dV+\oiint_{S(t)}\vec t\cdot\vec v\text dS
$$
where $e$ is the specific internal energy.

If $T^{ij}$ is simply given by $-p\delta^{ij}$, the second term
$$
\oiint_{S(t)}\vec t\cdot\vec v\text dS=-\iiint_{V(t)}\nabla\cdot\left(p\vec v\right)\text dV
$$
Again with Reynolds transport theorem,
$$
\iiint_{V(t)}\left[\rho\frac{\text D}{\text Dt}\left(e+\frac12 v^2\right)+\nabla\cdot\left(p\vec v\right)\right]\text dV=\iiint_{V(t)}\vec f\cdot \vec v\text dV
$$

$$
\Rightarrow \rho\frac{\text D}{\text Dt}\left(e+\frac12 v^2\right)+\nabla\cdot\left(p\vec v\right)=\vec f\cdot \vec v
$$

$$
\iff \frac{\text D}{\text Dt}\left[\rho\left( e+\frac12 v^2\right)\right]-\left(e+\frac12 v^2\right)\frac{\text D\rho}{\text Dt}+\nabla\cdot\left(p\vec v\right)=\vec f\cdot \vec v
$$

$$
\iff \frac{\partial}{\partial t}\left[\rho\left( e+\frac12 v^2\right)\right]+\left(\nabla\cdot \vec v+\vec v\cdot \nabla\right)\left[\rho\left( e+\frac12 v^2\right)\right]+\nabla\cdot\left(p\vec v\right)=\vec f\cdot \vec v
$$

$$
\iff \frac{\partial}{\partial t}\left[\rho\left( e+\frac12 v^2\right)\right]+\nabla\cdot\left[\rho\vec v\left( e+\frac12 v^2+\frac{p}{\rho}\right)\right]=\vec f\cdot \vec v
$$

which is known as the **energy equation**.

We can integrate and expand the second term so that
$$
\iiint_V \nabla\cdot\left[\rho\vec v\left( e+\frac12 v^2+\frac{p}{\rho}\right)\right]\text dV=\oiint\rho v_{\vec n}\left( e+\frac12 v^2\right)\text dS+\oiint pv_{\vec n}\text dS
$$
These two terms correspond to the **energy flux** and the **work**, respectively.

- Here,
  $$
  h=e+\frac p\rho
  $$
  is the specific enthalpy.

- If $\vec f$ is given by a static potential as
  $$
  \vec f=-\rho\nabla\phi,\quad \frac{\partial \phi}{\partial t}=0
  $$
  we can further write the energy equation as
  $$
  \frac{\partial}{\partial t}\left[\rho\left( e+\frac12 v^2+\phi\right)\right]+\nabla\cdot\left[\rho\vec v\left(\frac12 v^2+h+\phi\right)\right]=0
  $$

### Kinetic Energy

We derive the equation of the kinetic energy from Euler equation,
$$
\vec v\cdot\left[\frac{\partial \vec v}{\partial t}+\left(\vec v\cdot \nabla\right)\vec v+\frac1\rho\nabla p-\frac1\rho\vec f\right]=0
$$

$$
\iff \rho\left(\frac{\partial}{\partial t}+\vec v\cdot\nabla\right)\left(\frac12v^2\right)+\left(\vec v\cdot\nabla\right) p=\vec f\cdot\vec v
$$

$$
\iff \rho\frac{\text D}{\text Dt}\left(\frac12v^2\right)+\left(\vec v\cdot\nabla\right) p=\vec f\cdot\vec v
$$



### Thermal Energy (Total - Kinetic)

$$
\rho\frac{\text D}{\text Dt}\left(e+\frac12 v^2\right)-\rho\frac{\text D}{\text Dt}\left(\frac12v^2\right)+\nabla\cdot\left(p\vec v\right)-\left(\vec v\cdot\nabla\right) p=0
$$

$$
\iff \rho\frac{\text De}{\text Dt}+\left(\nabla\cdot\vec v\right) p=0
$$

Since
$$
\frac{\text D}{\text Dt}\left(\frac1\rho\right)=\frac1\rho\nabla\cdot\vec v
$$
We have
$$
\frac{\text De}{\text Dt}+p\frac{\text D}{\text Dt}\left(\frac1\rho\right)=0
$$
Recall that the first law of thermaldynamics gives
$$
\frac{\text De}{\text Dt}=-p\frac{\text D}{\text Dt}\left(\frac1\rho\right)+T\frac{\text Ds}{\text Dt}
$$
thus
$$
\frac{\text Ds}{\text Dt}=0
$$
which suggests adiabatic motion of the fluid. In this way, as long as we assume
$$
T^{ij}=-p\delta^{ij}
$$
we obtain **ideal fluid**.



## Viscosity & Navier-Stokes Equation

In general, the stress tensor is not diagonal,
$$
T^{ij}=-p\delta^{ij}+\sigma^{ij}
$$
where $\sigma$ is the **viscous tensor**.

The $i$-th component of the surface force is thus
$$
F_S^i=\oiint T^{ij}n_j\text dS=-\oiint pn^i\text dS+\oiint\sigma^{ij}n_j\text dS
$$
 and the force vector is
$$
\vec F_S=\iiint_V\left(\nabla\cdot \sigma-\nabla p\right)\text dV
$$
We claim that $\mathcal T$ is symmetric, that is, $T^{ij}=T^{ji}$. Consider a box with $\delta V=\delta x\delta y\delta z$. In the $z$-direction, the net torque caused leads to the change in angular momentum with respect to the center of $\delta S_{x,y}$
$$
\frac{\text dL_z}{\text dt}=\left(\vec r\times \vec F\right)_z
$$

$$
\rho\delta V\cdot\frac{\delta x^2+\delta y^2}{6}\dot\omega_z\sim\left(T_{x,y}-T_{y,x}\right)\delta V
$$

for $\delta x\to0,\delta y\to0$, we have $T_{x,y}=T_{y,x}$, otherwise the $\dot \omega$ goes to infinite.

Now that we know $\mathcal T$ is symmetric, it has 6 independent components.

### Viscous Tensor for Fluid

In a flow with $v_x$ that has a gradient of $\text dv_x/\text dy$, the stress to the $x$-axis is well approximated as
$$
\sigma_{xy}=\eta\frac{\text d v_x}{\text dy}
$$
where $\eta$ is the **(dynamic) viscosity** determined by microscopic processes of particles. Fluid that satisfies such approximation is known as **Nowton fluid**.

In astrophysics, a more frequently applied viscosity is the **kinematic viscosity** $\nu$, defined as
$$
\nu=\frac{\eta}{\rho}
$$
**$\nu$ in a microscopic perspective**

Consider a flow with coherent bulk velocity $v_x(y)$ along the $x$-axis, we try to count how much momentum is exchanged at the surface of $y=y_0$ per unit area per unit time, that is, the shear stress.

For simplicity, all we need to consider is a thin layer within $[y-l_\text{mfp},y+l_\text{mfp}]$, since we assume mometum is fully exchanged in the first collision. In this way, statistically, particles outside this layer cannot transport momentum to the surface $y=y_0$.

The number flux of particles hitting $y=y_0$ from one side can be estimated as
$$
N=\frac13 n\bar c\times\frac12
$$
where $n$ is the number density of particles and $\bar c$ is the **average velocity dispersion** ($\sim c_s$). We introduce a factor of $1/3$ because particles move in all three dimensions and $1/2$ further distinguish motion upwards and downwards. As a result, the shear stress is given by
$$
\sigma_{xy}=\frac16n\bar cm\left[v_x(y_0+l_\text{mfp})-v_x(y_0-l_\text{mfp})\right]=\frac13\rho\bar cl_\text{mfp}\frac{\partial v_x(y_0)}{\partial x}
$$
Thus
$$
\nu=\frac13\bar cl_\text{mfp}
$$
Unfortunately, momentum transition through collisions of particles is not the main cause of viscosity in astrophysics, and this formula is useless... In fact we can estimate the **viscous timescale**, in which viscosity drives materials to fall into the accretor.
$$
t_\text{vis}=\frac{r^2}{\nu}\sim\frac{r^2}{\bar cl_\text{mfp}}
$$
For the supermassive black hole (SMBH), this assumption gives a $t_\text{vis}$ if 10 Gyr, which is orders of magtitude longer than the typical AGN timescale ($\sim$ Myr). At present, it is widely agreed that the [**Magneto-Rotational Instability (MRI)**](https://en.wikipedia.org/wiki/Magnetorotational_instability) causes the viscosity in accretion disks. In this case, the $l_\text{mfp}$ is given by the **thickness of the disk** $H\sim0.01 r$, and the viscous timescale is quite satistying.



### Construction of Stress Tensor

1. $\sigma_{ij}$ is symmetric since $T_{ij}$ is symmetric, but the original definition.
   $$
   \sigma_{ij}=\eta\frac{\partial v_i}{\partial x^j}
   $$
   is not. In this way, we expand it into symmetric and anti-symmetric parts, as we can do to any second-order tensor
   $$
   \sigma_{ij}=\frac{\eta}{2}\left(\frac{\partial v_i}{\partial x^j}+\frac{\partial v_j}{\partial x^i}\right)+\frac{\eta}{2}\left(\frac{\partial v_i}{\partial x^j}-\frac{\partial v_j}{\partial x^i}\right)
   $$
   The second (anti-symmetric) term corresponds to the rotation. It has no viscosity, so we will consider a linear relation between $\sigma_{ij}$ and $E_{ij}$, which is defined as
   $$
   E_{ij}\equiv\frac{1}{2}\left(\frac{\partial v_i}{\partial x^j}+\frac{\partial v_j}{\partial x^i}\right)
   $$

2. Fluid doesn't have a preferred direction.

   Intuitionally, we write down the (multi-)linear relation as
   $$
   \sigma_{ij}=\alpha_{ijkl}E^{kl}
   $$
   We don't have any information of $\alpha$, but since fluid is **isotropic**, we would like to believe the tensor itself is isotropic, which means it has the same components in all rotated coordinate systems. There are only three basic 4-order isotropic tensors, all of which are the combination of the famous Kronecker delta $\delta_{ij}$.
   $$
   A_{ijkl}=\delta_{ij}\delta_{kj},\ \delta_{ik}\delta_{jl},\ \delta_{il}\delta_{jk}
   $$
   So we assume $\alpha_{ijkl}$ is simply their linear combination
   $$
   \begin{align*}
   \sigma_{ij}&=\left(B\delta_{ij}\delta_{kj}+C\delta_{ik}\delta_{jl}+D\delta_{il}\delta_{jk}\right)E^{kl}\\
   &=B\delta_{ij}E^k_k+CE_{ij}+DE_{ji}\\
   &=B\left(\nabla\cdot \vec v\right)\delta_{ij}+(C+D)E_{ij}
   \end{align*}
   $$

3. Decompose $\sigma_{ij}$ into trace part and traceless part
   $$
   \text{tr}\left(\sigma\right)=\delta^{ij}\sigma_{ij}=(3B+C+D)\nabla\cdot \vec v
   $$
   Thus
   $$
   \sigma_{ij}^{\text{tr}}=\frac{1}3(3B+C+D)\left(\nabla\cdot \vec v\right)\delta_{ij}
   $$

   $$
   \sigma_{ij}^\text{trf}=-\frac{C+D}3\left(\nabla\cdot \vec v\right)\delta_{ij}+\frac{C+D}2\left(\frac{\partial v_i}{\partial x^j}+\frac{\partial v_j}{\partial x^i}\right)
   $$

4. Redefine $\eta$ and $\zeta$ as
   $$
   \eta\equiv \frac12(C+D),\quad\zeta\equiv\frac13(3B+C+D)
   $$
   Finally, with only two free parameters, we may obtain
   $$
   \sigma_{ij}=\eta\left[\frac{\partial v_i}{\partial x^j}+\frac{\partial v_j}{\partial x^i}-\frac23\left(\nabla\cdot \vec v\right)\delta_{ij}\right]+\zeta\left(\nabla\cdot \vec v\right)\delta_{ij}
   $$

   - First term - traceless, pure **shear viscosity**

   - Second term - **bulk viscosity**

     >When Stokes first derived this formula, he believed the **bulk viscosity** vanished. In fact this term is usually close to 0.

### Navier-Stokes Equation

Right now,
$$
T^{ij}=-p\delta^{ij}+\sigma^{ij}
$$
and we can rewrite the momentum tensor by adding the viscous tensor
$$
\Pi^{ij}=\rho v^iv^j+\delta^{ij}p-\sigma^{ij}
$$
From this correction, the conservation of momentum (Euler equation) gives
$$
\frac{\text D\vec v}{\text Dt}=\frac1\rho\vec f+\frac1\rho\nabla\cdot\mathcal T=-\frac1\rho\nabla p+\frac1\rho\vec f+\frac1\rho\nabla\cdot\sigma
$$
Since
$$
\begin{align*}
(\nabla\cdot\sigma)_i&=\eta\partial^j\left[\partial_jv_i+\partial_iv_j-\frac23\partial_kv^k\delta_{ij}\right]+\zeta\partial^j\partial_kv^k\delta_{ij}\\
&=\eta\left[\nabla^2v_i+\frac13\partial_i(\nabla\cdot\vec v)\right]+\zeta\partial_i(\nabla\cdot\vec v)
\end{align*}
$$

$$
\iff \nabla\cdot\sigma=\eta\nabla^2\vec v+\left(\zeta+\frac13\eta\right)\nabla\left(\nabla\cdot\vec v\right)
$$

Finally we derive the **Navier-Stokes equation**
$$
\frac{\partial \vec v}{\partial t}+\left(\vec v\cdot \nabla\right)\vec v=-\frac1\rho\nabla p+\frac1\rho\vec f+\frac1\rho\eta\nabla^2\vec v+\frac1\rho\left(\zeta+\frac13\eta\right)\nabla\left(\nabla\cdot\vec v\right)
$$
In the end, let us consider the energy conservation in the viscous situation
$$
\frac{\text D}{\text D t}\iiint_{V(t)}\rho\left(e+\frac12 v^2\right)\text dV=\iiint_{V(t)}\vec f\cdot\vec v\text dV+\oiint_{S(t)}\vec t\cdot\vec v\text dS
$$

$$
\iff \iiint_{V(t)}\rho\frac{\text D}{\text D t}\left(e+\frac12 v^2\right)\text dV=\iiint_{V(t)}\vec f\cdot\vec v\text dV+\iiint_{V(t)}\nabla\cdot\left(\mathcal T\cdot\vec v\right)\text dV
$$

$$
\iff\rho\frac{\text D}{\text D t}\left(e+\frac12 v^2\right)=\vec f\cdot\vec v+\nabla\cdot\left(\mathcal T\cdot\vec v\right)
$$

By multiplying N-S equation with $\rho\vec v$, we have
$$
\rho\frac{\text D}{\text Dt}\left(\frac12v^2\right)=\vec f\cdot\vec v+\vec v\cdot\left(\nabla\cdot\mathcal T\right)
$$

$$
\Rightarrow \rho\frac{\text De}{\text D t}=\left(\mathcal T\cdot\nabla\right)\cdot \vec v
$$

Now we expand the RHS
$$
\begin{align*}
\left(\mathcal T\cdot\nabla\right)\cdot \vec v&=(\partial_iv_j)T^{ij}\\
&=-\partial_iv^ip+(\partial_iv_j)\sigma^{ij}\\
&=-p(\nabla\cdot\vec v)+\eta(\partial_iv_j)\left[2E^{ij}-\frac23\left(\nabla\cdot \vec v\right)\delta_{ij}\right]+\zeta(\partial_iv^i)\left(\nabla\cdot \vec v\right)\\
&=-p(\nabla\cdot\vec v)+\eta(\partial_iv_j)(\partial^jv^i+\partial^iv^j)+\left(\zeta-\frac23\eta\right)\left(\nabla\cdot \vec v\right)^2
\end{align*}
$$
where
$$
\begin{align*}
(\partial_iv_j)(\partial^jv^i+\partial^iv^j)&=\frac12(\partial_iv_j+\partial_jv_i)(\partial^jv^i+\partial^iv^j)\\
&-\frac12(\partial_iv_j-\partial_jv_i)(\partial^jv^i+\partial^iv^j)\\
&=2E_{ij}E^{ij}
\end{align*}
$$
as the second term obviously vanishes. Finally,
$$
\left(\mathcal T\cdot\nabla\right)\cdot \vec v=-p(\nabla\cdot\vec v)+2\eta E_{ij}E^{ij}+\left(\zeta-\frac23\eta\right)\left(\nabla\cdot \vec v\right)^2
$$
Define
$$
\Phi_\text{vis}=2\eta E_{ij}E^{ij}+\left(\zeta-\frac23\eta\right)\left(\nabla\cdot \vec v\right)^2
$$
we have
$$
\rho\left[\frac{\text De}{\text D t}+p\frac{\text D}{\text Dt}\left(\frac1\rho\right)\right]=\Phi_\text{vis}=\rho T\frac{\text Ds}{\text Dt}
$$
Thus,
$$
\frac{\text DS}{\text Dt}=\frac{\text D}{\text Dt}\iiint_{V}\rho s\text dV=\iiint_{V}\rho \frac{\text Ds}{\text Dt}\text dV=\iiint_{V}\frac{\Phi_\text{vis}}{T}\text dV
$$
The second law of thermaldynamics tells us
$$
\frac{\text DS}{\text Dt}\ge0
$$
In fact, we can prove
$$
\Phi_\text{vis}\ge0
$$


### The Reynolds Number

**The Reynolds number** is defined as
$$
\text{Re}=\frac{UL}{\nu}
$$
where $U$ is the flow speed, $L$ is a characteristic linear dimension, and $\nu$ is the kinematic viscosity. It is naturally connected with the Navier-Stokes equation when we try to derive a dimensionless form of the equation.

By assuming incompressible fluid ($\nabla\cdot \vec v=0$) and neglecting the external force, the Navier-Stokes equation goes like
$$
\frac{\partial \vec v}{\partial t}+\left(\vec v\cdot \nabla\right)\vec v=-\frac1\rho\nabla p+\nu\nabla^2\vec v
$$
Define several dimensionless quantities,
$$
r'=\frac rL,\quad \vec v'=\frac{\vec v}{U},\quad t'=\frac{t}{L/u},\quad \rho'=\frac{\rho}{\rho_0},\quad p'=\frac{p}{\rho_0v^2}
$$
We have
$$
\frac{\partial \vec v'}{\partial t'}+\left(\vec v'\cdot \nabla'\right)\vec v'=-\frac1\rho'\nabla' p'+\frac\nu{UL}\nabla'^2\vec v'\equiv -\frac1\rho'\nabla' p'+\frac1{\text{Re}}\nabla'^2\vec v'
$$
The Reynolds number is simply there.

If $\text{Re}\to\infty$, the equation goes back to the Euler equation (ideal fluid).

Small $\text{Re}$ corresponds to **laminar flow**, a fluid flowing in parallel layers with no disruption between the layers, while large $\text{Re}$ introduces annoying **turbulence**, a fluid motion characterized by chaotic changes in pressure and flow velocity. In astrophysics, $\text{Re}$ is usually large.

**Notes**

1. Dimensionless Navier-Stokes equation does not depend on $\rho_0$ - **scale-free**. Once a hydrodynamical simulation is done with certain density, it is done with any other density. This beautiful scale-free law breaks when

   - $P-\rho$ relation is not a simple power-law, and has certain breaks.
   - the simulation has to take opacity/cooling/heating into account, none of which is scale-free.

2. If we introduce gravity as the external force
   $$
   \vec f_\text{ext}=-\frac{GM}{r^2}\hat{\vec r}
   $$
   the corresponding term in the dimensionless Naiver-Stokes equation is
   $$
   -\frac{1}{LU^2}\frac{GM}{r'^2}
   $$
   It seems to have dependence on $M$, however, if we set
   $$
   U=c,\quad L=r_\text{g}\equiv\frac{GM}{c^2}
   $$
   where $r_\text g$ is the Schiwarzchild radius. This term is simply
   $$
   -\frac1{r'^2}
   $$
   Around a black hole, Navier-Stokes equation is again scale-free, this time for the mass of the accretor.

   

