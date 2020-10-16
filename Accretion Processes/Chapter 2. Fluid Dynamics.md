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
  \delta m=\Delta t\cdot\frac{\text d}{\text dt}\left(\iiint_{\delta V_0}\rho\text dV\right)
  $$
  Consider the **mass flow** at the surface
  $$
  \vec j=\Delta t\oiint_{\delta S}\left(\vec u\cdot\vec n\right)\rho\text dS=\Delta t\iiint_{\delta V_0}\nabla\cdot\left(\rho\vec u\right)\text dV
  $$
  where we have applied Gauss' divergence theorem. Here $\vec n$ is the normal vector of the surface.

  If there are no source/sink of mass within the fluid element, the mass flow should exactly account for the change in mass
  $$
  \frac{\text d}{\text dt}\left(\iiint_{\delta V_0}\rho\text dV\right)+\iiint_{\delta V_0}\nabla\cdot\left(\rho\vec u\right)\text dV=0
  $$
  Since we have fixed $\Delta V$, we can write this formula so that for any $\Delta V$
  $$
  \iiint_{\delta V_0}\left(\frac{\partial \rho}{\partial t}+\nabla\cdot\left(\rho\vec u\right)\right)\text dV=0
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



## Euler Equation - Momentum Conservation

In the Lagrange's picture, the acceleration onto a mass element is given by
$$
\frac{\text D}{\text Dt}\iiint_{V(t)}\rho\vec u\text dV=\iiint_{V(t)}\rho\frac{\text D\vec u}{\text Dt}\text dV
$$
The EoS thus gives
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
\Leftrightarrow \frac{\partial \vec u}{\partial t}+\left(\vec u\cdot \nabla\right)\vec u=-\nabla p+\vec f
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





