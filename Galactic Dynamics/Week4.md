# Week4: Orbits

## Spherical potential $\Phi(r)$

In the spherical coordinates, the Lagrangian is
$$
\mathcal L=\frac12v^2-\Phi(r)=\frac12\dot r^2+\frac12\left(r\dot\theta\right)^2+\frac12\left(r\sin\theta\dot\phi\right)^2-\Phi(r)
$$
The corresponding generalized momenta are
$$
p_r=\frac{\partial \mathcal L}{\partial \dot r}=\dot r\\
p_\theta=\frac{\partial \mathcal L}{\partial \dot \theta}=r^2\dot \theta\\
p_\phi=\frac{\partial \mathcal L}{\partial \dot \phi}=r^2\sin^2 \theta\dot\phi
$$
The Hamiltonian
$$
H=\vec p\cdot\vec q-\mathcal L=\frac{p^2_r}{2}+\frac{p_\theta^2}{2r^2}+\frac{p_\phi^2}{2r^2\sin^2\theta}+\Phi(r)
$$
We can define
$$
p_\alpha^2=p_\theta^2+\frac{p_\phi^2}{\sin^2\theta}
$$
so that we can simplify the Hamiltonian
$$
H=\frac{p^2_r}{2}+\frac{p_\alpha^2}{2r^2}+\Phi(r)
$$
$\alpha$ is a new generalized coordinate which satisfies
$$
p_\alpha=\frac{\partial \mathcal L}{\partial \dot\alpha}=r^2\sqrt{\dot\theta^2+\sin^2\theta\dot\phi^2}=r\sqrt{v_\theta^2+v_\phi^2}=rv_\perp
$$
Since
$$
\dot p_\alpha=-\frac{\partial H}{\partial \alpha}=0
$$
the generalized momentum, or the angular momentum perpendicular to the plane determined by $\vec v$ and $\vec v+\text d\vec v$ is conserved, and we can reselect the coordinates and consider the 2D problem with coordinates $(r,\theta)$

- Conservation of angular momentum
  $$
  \dot p_\theta=-\frac{\partial H}{\partial \theta}=0\Rightarrow p_\theta=r^2\dot\theta=L
  $$

 - Conservation of energy
   $$
   \frac{\partial H}{\partial t}=0\Rightarrow \frac{p^2_r}{2}+\frac{p_\theta^2}{2r^2}+\Phi(r)\equiv \frac{\dot r^2}{2}+\Phi_{eff}=E
   $$

Physically, the radial distance $r$ is reachable only when
$$
E\ge\Phi_{eff}(r)
$$
If this is satisfied in an closed interval $[r_1, r_2]$, intuitionally, $r$ could oscillate between $r_1$ and $r_2$, whose period (so-called **radial period**) is
$$
T_r=2\int_{r_1}^{r_2}\frac{\text dt}{\text dr}\text dr=2\int_{r_1}^{r_2}\frac{\text dr}{\sqrt{2[E-\Phi(r)]-{L^2}/{r^2}}}
$$
In one complete radial period ($r_1\to r_2\to r_1$), usually $\Delta\theta\neq 2\pi$ (Kepler orbits are so special!). In fact

$$
\Delta\theta=2\int_{r_1}^{r_2}\frac{\text d\theta}{\text dr}\text dr=2\int_{r_1}^{r_2}\frac{\text Ldr}{r^2\sqrt{2[E-\Phi(r)]-{L^2}/{r^2}}}
$$
And the **azimuthal period** is thus determined to be
$$
T_\theta=\frac{2\pi}{\Delta\theta}T_r
$$
Of course usually $T_\theta\neq T_r$, but if $T_\theta/T_r$ is at least rational, the orbit will turn out to be **closed**. Below we discuss several special closed orbits

1. Kepler
   $$
   T_\theta=T_r=2\pi\sqrt{\frac{a^3}{GM}}, \  T_\theta:T_r=1:1
   $$

2. Homogeneous sphere (see in last week's notes)
   $$
   \Phi(r)=C+\frac12\Omega^2r^2=C+\frac12\Omega^2(x^2+y^2)
   $$
   Newton's second law gives
   $$
   \left\{\begin{array}{c}
   {\ddot x=-\Phi_x(x,y)=-\Omega x\\
   \ddot y=-\Phi_y(x,y)=-\Omega y}
   \end{array}\right.
   \Rightarrow \text{Harmonic oscillators!}
   $$
   The corresponding orbits are thus eclipses centered at the coordinate origin, so every $2\pi$ angle the object goes around, the variation of $r$ undergoes two orbits
   $$
   T_\theta=\frac{2\pi}{\Omega},\ T_r=\frac{T_\theta}{2},\ T_\theta:T_r=2:1
   $$

In general,
$$
1<\frac{T_\theta}{T_r}<2
$$
A more intuitional picture is that the orbit continuously **precesses** at a rate of
$$
\Omega_P=\frac{\Delta\theta-2\pi}{T_r}
$$

- $\Omega_P<0$ - Retrograde
- $\Omega_P>0$ - Prograde