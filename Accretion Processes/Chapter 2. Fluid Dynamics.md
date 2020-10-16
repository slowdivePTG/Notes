# Fluid Dynamics

## Fluid Approximation

The fluid approximation is valid when the system size $L$ is much larger than the mean free path $l_\text{mfp}$.

- For ISM (interstellar medium), the typical mean free path is
  $$
  l_\text{mfp}\sim 10^{15}\text{cm}\left(\frac{n}{1\text{ cm}^{-3}}\right)^{-1}\left(\frac{d}{1\ \AA}\right)^{-2}
  $$

Inside each fluid particle, we can define thermal dynamical quantities, $T,\rho,P,S$, as well as a velocity field $\vec u(\vec x,t)$.

For any quantity of the fluid element at $(\vec r_0,t_0)$, say $F(\vec r_0,t_0)$, we have
$$
\begin{align*}
\Delta F&=F\left(\vec r_0+\vec u(\vec r_0)\Delta t,t_0+\Delta t\right)-F(\vec r_0,t_0)\\
&=\left(\frac{\partial F}{\partial t}+u_x\frac{\partial F}{\partial x}+u_y\frac{\partial F}{\partial y}+u_z\frac{\partial F}{\partial z}\right)\Delta t+\mathcal O(\Delta t^2)
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
  \left(\frac{\partial}{\partial t}+\vec u\cdot \nabla\right) F
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
  \vec j=\Delta t\oiint_{\delta S}\left(\vec u\cdot\vec n\right)\rho\text dS=\Delta t\iiint_{\delta V_0}\nabla\cdot\left(\rho\vec u\right)\text dV_0
  $$
  where we have applied Gauss' divergence theorem. Here $\vec n$ is the normal vector of the surface.

  If there are no source/sink of mass within the fluid element, the mass flow should exactly account for the change in mass
  $$
  \frac{\text d}{\text dt}\left(\iiint_{\delta V_0}\rho\text dV_0\right)+\iiint_{\delta V_0}\nabla\cdot\left(\rho\vec u\right)\text dV_0=0
  $$
  Since we have fixed $\Delta V$, we can write this formula so that for any $\Delta V_0$
  $$
  \iiint_{\delta V_0}\left(\frac{\partial \rho}{\partial t}+\nabla\cdot\left(\rho\vec u\right)\right)\text dV_0=0
  $$
  The arbitrariness of the choice of $\Delta V$ directly leads to the famous **equation of continuity**
  $$
  \frac{\partial \rho}{\partial t}+\nabla\cdot\left(\rho\vec u\right)=0
  $$

- In **Lagrange's picture**

  Let us consider a volume element $\delta V$ that moves with fluid particles.

  If no mass creation / annihilation
  $$
  0=\frac{\text D(\delta m)}{\text Dt}=\frac{\text D}{\text Dt}\left(\rho\delta V\right)=\frac{\text D\rho}{\text Dt}\delta V+\rho\frac{\text D}{\text Dt}\left(\delta V\right)
  $$

  $$
  \Rightarrow
  \frac{\text D\rho}{\text Dt}=-\frac{\rho}{\delta V}\frac{\text D}{\text Dt}\left(\delta V\right)=-\rho\sum_{i}\frac{1}{\delta x_i}\frac{\text D\left(\delta x_i\right)}{\text Dt}=-\rho\left(\nabla\cdot \vec u\right)
  $$

  Recall that
  $$
  \frac{\text D}{\text Dt}=\frac{\partial}{\partial t}+\vec u\cdot \nabla
  $$
  Then
  $$
  \left(\frac{\partial}{\partial t}+\vec u\cdot \nabla+\nabla\cdot\vec u\right)\rho=0\Rightarrow\frac{\partial\rho}{\partial t}+\nabla\cdot\left(\rho\vec u\right)=0
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
\frac{\text DJ}{\text Dt}=\left(\nabla \cdot \vec u\right)J
$$
Then if we reconsider the conservation of mass in Lagrange's picture,
$$
\frac{\text D}{\text Dt}\iiint_{\delta V}\rho\text{d}V=0
$$

$$
\iff 0=\frac{\text D}{\text Dt}\iiint_{\delta V}\rho J\text{d}V_0=\iiint_{\delta V}\left[\frac{\text D \rho}{\text Dt}+\rho\left(\nabla\cdot u\right)\right]J\text dV_0
$$

which also gives the continuity formula
$$
\frac{\text D \rho}{\text Dt}+\rho\left(\nabla\cdot u\right)=0
$$
Before moving to the next section, we can similarly derive several useful identities of the Lagrange's derivative.

For a function $F$,
$$
\frac{\text D }{\text Dt}\iiint_VF\text dV=\frac{\text D }{\text Dt}\iiint_VFJ\text dV_0=\iiint_V\left[\frac{\text D F}{\text Dt}+\left(\nabla \cdot \vec u\right)F\right]J\text dV_0=\iiint_V\left[\frac{\text D F}{\text Dt}+\left(\nabla \cdot \vec u\right)F\right]\text dV
$$

$$
\iff \frac{\text D }{\text Dt}\iiint_VF\text dV=\iiint_V\left[\frac{\partial F}{\partial t}+\nabla\cdot\left(F \vec u\right)\right]\text dV
$$

This is known as the **Reynolds transport theorem**. Simply let $F=\alpha\rho$, we have
$$
\begin{align*}
\frac{\text D }{\text Dt}\iiint_V\alpha\rho\text dV&=\iiint_V\left[\frac{\text D }{\text Dt}\left(\alpha\rho\right)+\left(\nabla \cdot \vec u\right)\alpha\rho\right]\text dV\\
&=\iiint_V\left\{\alpha\left[\frac{\text D \rho}{\text Dt}+\left(\nabla \cdot \vec u\right)\rho\right]+\rho\frac{\text D\alpha}{\text Dt}\right\}\text dV\\
&=\iiint_V\rho\frac{\text D\alpha}{\text Dt}\text dV
\end{align*}
$$
This identity is extremely useful in the following chapters.



## Euler Equation - Momentum Conservation

In the Lagrange's picture, the acceleration onto a mass element is given by
$$
\frac{\text D}{\text Dt}\iiint_{V(t)}\rho\vec u\text dV=\iiint_{V(t)}\rho\frac{\text D\vec u}{\text Dt}\text dV
$$
With the Reynolds transport theorem, the EoS thus gives
$$
\iiint_{V(t)}\rho\frac{\text D\vec u}{\text Dt}\text dV=\iiint_{V(t)}\vec f\text dV+\oiint_{S(t)}\vec t\text dS
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
\rho\frac{\text D\vec u}{\text Dt}=-\nabla p+\vec f
$$

$$
\iff \frac{\partial \vec u}{\partial t}+\left(\vec u\cdot \nabla\right)\vec u=-\frac1\rho\nabla p+\frac1\rho\vec f
$$

which is the famous **Euler equation** for ideal fluid.

Using the equation of continuity and the Euler equation, we can calculate the time derivative of **mass flux**
$$
\begin{align*}
\frac{\partial}{\partial t}\left(\rho u^i\right)&=u^i\frac{\partial\rho}{\partial t}+\rho\frac{\partial u^i}{\partial t}\\
&=-u^i\partial_j\left(\rho u^j\right)-\rho u^j\partial_ju^i-\partial_j\delta^{ij}p\\
&=-\partial_j\left(\rho u^iu^j+\delta^{ij}p\right)\\
&\equiv -\partial_j\Pi^{ij}
\end{align*}
$$
So in the Eulerian picture, the **momentum conservation** is
$$
\frac{\partial}{\partial t}\left(\rho u^i\right)+\partial_j\Pi^{ij}=0
$$
Integrate the above equation over a fixed volume $V$
$$
\begin{align*}
\frac{\text d}{\text dt}\iiint_V\rho u^i\text dV&=-\iiint\partial^i p\text dV-\iiint\partial_j\left(\rho u^iu^j\right)\text dV\\
&=-\oiint_Spn^i\text dS-\oiint_S\rho u^iu^jn_j\text dS
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
\frac{\text Ds}{\text Dt}=\frac{\partial s}{\partial t}+\left(\vec u\cdot \nabla\right)s=0
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
\frac{\partial \vec u}{\partial t}+\left(\vec u\cdot \nabla\right)\vec u=-\frac1\rho\nabla p-\nabla\phi
$$

$$
\Rightarrow \frac{\partial \vec u}{\partial t}+\nabla\left(\frac12u^2+h+\phi\right)=\vec u\times\vec\omega
$$

where the **vorticity** is defined as
$$
\vec\omega=\nabla\times\vec u
$$
and we have applied the identity
$$
\vec u\times\left(\nabla\times\vec u\right)=\left(\nabla\cdot\vec u\right) \vec u-\left(\vec u\cdot\nabla\right) \vec u=\frac12\nabla u^2-\left(\vec u\cdot\nabla\right) \vec u
$$

- For steady flow
  $$
  \frac{\partial u}{\partial t}=0
  $$
  thus
  $$
  \vec u\cdot\nabla\left(\frac12u^2+h+\phi\right)=\vec u\cdot\left(\vec u\times\vec\omega\right)=0
  $$
  which means $\frac12u^2+h+\phi$ is conserved along each streamline.

- No vorticity
  $$
  \nabla\times \vec u=0\Rightarrow \vec u=-\nabla\psi
  $$
  thus
  $$
  \frac{\partial\psi}{\partial t}+\frac12u^2+h+\phi=F(t)
  $$
  and $\nabla F(t)=0$.

- Steady & no vorticity
  $$
  \frac{\partial \psi}{\partial t}=0
  $$
  Then $\frac12u^2+h+\phi$ remains a constant everywhere.



## Energy Conservation

For fluid dynamics, the energy change in a unit time is given by
$$
\frac{\text D}{\text D t}\iiint_{V(t)}\rho\left(e+\frac12 u^2\right)\text dV=\iiint_{V(t)}\vec f\cdot\vec u\text dV+\oiint_{S(t)}\vec t\cdot\vec u\text dS
$$
where $e$ is the specific internal energy.

If $T^{ij}$ is simply given by $-p\delta^{ij}$, the second term
$$
\oiint_{S(t)}\vec t\cdot\vec u\text dS=-\iiint_{V(t)}\nabla\cdot\left(p\vec u\right)\text dV
$$
Again with Reynolds transport theorem,
$$
\iiint_{V(t)}\left[\rho\frac{\text D}{\text Dt}\left(e+\frac12 u^2\right)+\nabla\cdot\left(p\vec u\right)\right]\text dV=\iiint_{V(t)}\vec f\cdot \vec u\text dV
$$

$$
\Rightarrow \rho\frac{\text D}{\text Dt}\left(e+\frac12 u^2\right)+\nabla\cdot\left(p\vec u\right)=\vec f\cdot \vec u
$$

$$
\iff \frac{\text D}{\text Dt}\left[\rho\left( e+\frac12 u^2\right)\right]-\left(e+\frac12 u^2\right)\frac{\text D\rho}{\text Dt}+\nabla\cdot\left(p\vec u\right)=\vec f\cdot \vec u
$$

$$
\iff \frac{\partial}{\partial t}\left[\rho\left( e+\frac12 u^2\right)\right]+\left(\nabla\cdot \vec u+\vec u\cdot \nabla\right)\left[\rho\left( e+\frac12 u^2\right)\right]+\nabla\cdot\left(p\vec u\right)=\vec f\cdot \vec u
$$

$$
\iff \frac{\partial}{\partial t}\left[\rho\left( e+\frac12 u^2\right)\right]+\nabla\cdot\left[\rho\vec u\left( e+\frac12 u^2+\frac{p}{\rho}\right)\right]=\vec f\cdot \vec u
$$

which is known as the **energy equation**.

We can integrate and expand the second term so that
$$
\iiint_V \nabla\cdot\left[\rho\vec u\left( e+\frac12 u^2+\frac{p}{\rho}\right)\right]\text dV=\oiint\rho u_{\vec n}\left( e+\frac12 u^2\right)\text dS+\oiint pu_{\vec n}\text dS
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
  \frac{\partial}{\partial t}\left[\rho\left( e+\frac12 u^2+\phi\right)\right]+\nabla\cdot\left[\rho\vec u\left(\frac12 u^2+h+\phi\right)\right]=0
  $$

### Kinetic Energy

We derive the equation of the kinetic energy from Euler equation,
$$
\vec u\cdot\left[\frac{\partial \vec u}{\partial t}+\left(\vec u\cdot \nabla\right)\vec u+\frac1\rho\nabla p-\frac1\rho\vec f\right]=0
$$

$$
\iff \rho\left(\frac{\partial}{\partial t}+\vec u\cdot\nabla\right)\left(\frac12u^2\right)+\left(\vec u\cdot\nabla\right) p=\vec f\cdot\vec u
$$

$$
\iff \rho\frac{\text D}{\text Dt}\left(\frac12u^2\right)+\left(\vec u\cdot\nabla\right) p=\vec f\cdot\vec u
$$



### Thermal Energy (Total - Kinetic)

$$
\rho\frac{\text D}{\text Dt}\left(e+\frac12 u^2\right)-\rho\frac{\text D}{\text Dt}\left(\frac12u^2\right)+\nabla\cdot\left(p\vec u\right)-\left(\vec u\cdot\nabla\right) p=0
$$

$$
\iff \rho\frac{\text De}{\text Dt}+\left(\nabla\cdot\vec u\right) p=0
$$

Since
$$
\frac{\text D}{\text Dt}\left(\frac1\rho\right)=\frac1\rho\nabla\cdot\vec u
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

