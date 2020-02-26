# Week2

## Determine the trajectory

### Methods: Lagrangian/Hamilton Dynamics

**Lagrangian**
$$
\mathcal{L}=K-V=\mathcal{L}(t,q,\dot{q})
$$
where $K$ is the kinetic energy, $V$ is the potential energy, and $q$ correspond to a set of **general coordinates**

**Euler-Lagrange equation**
$$
\frac{\text{d}}{\text{d}t}\left(\frac{\partial \mathcal{L}}{\partial\dot q}\right)-\frac{\partial \mathcal{L}}{\partial q}=0
$$

**General momentum**
$$
p=\frac{\partial \mathcal{L}}{\partial\dot q}
$$

**Hamiltonian**
$$
H=\sum p_i\dot q_i-\mathcal{L}=H(t,q,p)
$$
and
$$
\text{d}H=-\frac{\partial \mathcal{L}}{\partial t}\text{d} t-\frac{\partial \mathcal{L}}{\partial\dot q}\text{d}q+\dot q\text{d}p
$$

**Hamilton's canonical equations**
$$
\dot p=\frac{\partial \mathcal{L}}{\partial q}=-\frac{\partial H}{\partial q}\\
\dot q=\frac{\partial H}{\partial p}
$$

### Solve the two-body trajectory

We know that the trajectory is in a plane - two parameters (general coordinates) - $r$ and $\theta$

**(Specific) Lagrangian**
$$
\mathcal{L}=\frac12\left(\dot r^2+r^2\dot\theta^2\right)+\frac{Gm}{r}
$$
**General momenta**
$$
p_r=\dot r,\quad p_\theta=r^2\dot\theta
$$
**Hamiltonian**
$$
H=\sum p_i\dot q_i-\mathcal{L}=\frac12\left(p_r^2+\frac{p_\theta^2}{r^2}\right)-\frac{Gm}{r}
$$
Here the Hamiltonian is the (conserved) energy $E$ of the system

**Hamilton's canonical equations**
$$
\left\{\begin{align*}
\dot r&=p_r\\
\dot \theta&=\frac{p_\theta}{r^2}\\
\dot{p}_r&=-\frac{p_\theta^2}{r^3}+\frac{Gm}{r^3}\\
\dot p_\theta&=0
\end{align*}\right.
\Rightarrow 

p_\theta=L,\quad p_r=\pm\sqrt{2\left(E+\frac{Gm}{r}\right)-\frac{L^2}{r^2}}
$$

$$
\Rightarrow\frac{\text{d}r}{\text{d}\theta}=\frac{p_r}{p_\theta/r^2}=\frac{\pm\sqrt{2\left(E+\frac{Gm}{r}\right)-\frac{L^2}{r^2}}}{L/r^2}
$$

In fact
$$
\frac{L}{r}-\frac{Gm}{L}=\sqrt{2E+\frac{G^2m^2}{L^2}}\cos(\theta+\theta_0)\Rightarrow r=\frac{L^2/Gm}{1+\sqrt{1+\frac{2EL^2}{G^2m^2}}\cos\theta}
$$
We let
$$
p=\frac{L^2}{Gm},\quad e=\sqrt{1+\frac{2EL^2}{G^2m^2}}
$$

$$
\Rightarrow r=\frac{p}{1+e\cos\theta}
$$

Typical **Polar equations** of **conic sections**!

1. $E<0\Rightarrow e<1$ - ellipse

2. $E=0\Rightarrow e=1$ - parabola
   $$
   E=0\Rightarrow\frac{v^2}{2}=\frac{Gm}{r}\Rightarrow v=\sqrt{\frac{2GM}{r}}
   $$
   For parabola orbits, it is easy for us to calculate the velocity!

   If
   $$
   \left|\frac{2EL^2}{G^2m^2}\right|\ll1
   $$
   the orbit looks quite like a parabola so we can also estimate the velocity in this way

   - Example 1 - stars around a SMBH

     $v=100\text{ km/s}$, $r=1\text{ pc}$, $m=10^8\ M_{\odot}$
     $$
     \left|\frac{2EL^2}{G^2m^2}\right|\sim10^{-17}
     $$
     quite parabolic!

   - Example 2 - two galaxies in a cluster

     $v=500\text{ km/s}$, $r=100\text{ kpc}$, $m=10^{11}\ M_{\odot}$
     $$
     \frac{2EL^2}{G^2m^2}\sim10^3
     $$
     hyperbolic!

3. $E>0\Rightarrow e>1$ - hyperbola

   **Scattering**

   ![](scattering.eps)

   The (specific) energy and angular momenta are straightforward
   $$
   E=\frac{v_\infty^2}{2}=\frac{v_f^2}{2},\quad L=v_\infty b
   $$
   And it is easy to tell that throughout the scattering,
   $$
   \Delta \theta=2\theta_{cri}-\pi
   $$
   where
   $$
   \theta_{cri}=\pi-\arccos(a/c)=\arccos(-1/e)
   $$
   In this way,
   $$
   \Delta\theta=2\arccos(-1/e)-\pi=2\arcsin(1/e),\quad e\gg1\Rightarrow\Delta\theta\ll1
   $$
   In fact, when $e\gg1$, we have
   $$
   \Delta\theta\sim1/e=\left(1+\frac{2EL^2}{G^2m^2}\right)^{-1/2}\sim\sqrt{\frac{G^2m^2}{2EL^2}}=\frac{Gm}{{v_\infty^2} b}=\frac{r_{inf}}{b}
   $$
   $r_{inf}$ is a typical impact parameter with which $\Delta \theta$ becomes significant
   $$
   e\sim\sqrt{2}\Rightarrow\frac{2EL^2}{G^2m^2}\sim1\Rightarrow b\sim\frac{Gm}{v^2_\infty}\equiv r_{inf}
   $$

### Relaxation

