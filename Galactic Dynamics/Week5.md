# Week5: Orbits

## Integral and constants of motion

In spherical potential, we consider the degrees of freedom of the system. In the Hamiltonian, we have six free parameters, that is, the generalized coordinates and momenta
$$
(x,y,z,p_x,p_y,p_z) \text{ or } (r,\theta,\phi,p_r,p_\theta,p_\phi)
$$
The vanished partial derivative of $H$ (with respect to $t$ and $\alpha$, see in last week's notes) conserves the energy and the angular momentum (three-dimensions), thus the DoF is reduced by **four**.

In general, to simplify our analysis, we would like to find out some **integrals** as functions of only the coordinates in the phase-space
$$
I(\vec q,\vec p)=C
$$
to help us reduce the DoF.

More generally we can discuss **constants of motion**, which are functions of both the coordinates in the phase-space and time, but is invariant in an orbit. Integrals are constants of motions, while the converse is not necessarily true.

### Discuss the integrals in a spherical potential

Can we find a **fifth** integral in a spherical potential?

With the general form of how $u=1/r$ is related to $\psi$ in a plane
$$
\frac{\mathrm{d}^{2} u}{\mathrm{d} \psi^{2}}+u=\frac{1}{L^{2} u^{2}} \frac{\mathrm{d} \Phi}{\mathrm{d} r}(1 / u)
$$
we examine the potential
$$
\Phi(r)=-GM\left(\frac1r+\frac{a}{r^2}\right)\Rightarrow \partial_r\Phi(r)=GM\left(\frac{1}{r^2}+\frac{2a}{r^3}\right)
$$
so that
$$
\frac{\mathrm{d}^{2} u}{\mathrm{d} \psi^{2}}+\left(1-\frac{2 G M a}{L^{2}}\right) u=\frac{G M}{L^{2}}
$$
The general solution is
$$
u=C \cos \left(\frac{\psi-\psi_{0}}{K}\right)+\frac{G M K^{2}}{L^{2}},\quad K=\left(1-\frac{2GMa}{L^2}\right)^{-1/2}
$$
Hence
$$
\frac{\psi-\psi_{0}}{K}=\pm\arccos\left[\frac{1}{C}\left(\frac{1}{r}-\frac{G M K^{2}}{L^{2}}\right)\right]+2\pi n,\quad n\in N
$$
which is a function of $r, E, L$

- **Non-isolating integrals**: If $K$ is irrational, we can make $\psi-\psi_0$ modulo $2\pi$ approximately any given number as closely as we wish, so given $r, E, L$, an orbit that is known to have a given value of the integral $\psi_0$ can have an azimuthal angle as close as we please to any number between $0$ and $2\pi$.

  As a result, even if we select a $\psi_0$ randomly, the **phase-space distribution** of an orbit will not be affected

- **Isolating integrals**: If $K$ is rational, say, $K=k_1/k_2$ where $k_1,k_2\in N$ 
  $$
  \psi-\psi_0\equiv \pm\arccos\left[\frac{1}{C}\left(\frac{1}{r}-\frac{G M K^{2}}{L^{2}}\right)\right]+2\pi \frac{nk_1}{k_2}\quad(\mod 2\pi)
  $$
  Since $nk_1$ modulo $k_2$ has no more than $k_2$ possible values, the number of $\psi$ is also limited



## Axisymmetric potential $\Phi(R,z)$

The Lagrangian
$$
\mathcal L=\frac12\left[\dot R^2+R^2\dot\phi^2+\dot z^2\right]-\Phi(R,z)
$$

Generalized momenta
$$
p_R=\dot R,\quad p_\phi=R^2\phi,\quad p(z)=\dot z
$$

The Hamiltonian
$$
H=\frac12\left(p_R^2+\frac{p_\phi^2}{R^2}+p_z^2\right)+\Phi(R,z)
$$

$$
\Rightarrow\left\{
\begin{align*}
\dot p_R&=-\frac{\partial H}{\partial R}=\frac{p_\phi^2}{R^3}-\frac{\partial }{\partial R}\Phi(R,z)\\
\dot p_\phi&=-\frac{\partial H}{\partial \phi}=0\quad \Rightarrow p_\phi\equiv L_z\\
\dot p_z&=-\frac{\partial H}{\partial z}=-\frac{\partial}{\partial z}\Phi(R,z)\\
\end{align*}
\right.
$$

We can also define an effective potential to be
$$
\Phi_{eff}\equiv\frac{L_z^2}{2R^2}+\Phi(R,z)
$$
so that
$$
\dot p_R=\ddot R=-\frac{\partial \Phi_{eff}}{\partial R},\quad \dot p_z=\ddot z=-\frac{\partial \Phi_{eff}}{\partial z}
$$
In this way, the 3-D motion can be reduced to a 2-D one in the $(R,z)$ plane (**meridional plane**) under the Hamiltonion
$$
H=H=\frac12\left(p_R^2+p_z^2\right)+\Phi_{eff}(R,z)
$$
The orbit is, obviously, restricted to the area in the meridional plane satisfying $E\ge \Phi_{eff}$

Consider the minimum of $\Phi_{eff}(R,z)$, where
$$
0=\frac{\partial \Phi_{{eff}}}{\partial R}=\frac{\partial \Phi}{\partial R}-\frac{L_{z}^{2}}{R^{3}}, \quad 0=\frac{\partial \Phi_{{eff}}}{\partial z}
$$
The latter is satisfied everywhere on the $z=0$ plane, assuming the symmetry of $\Phi$ with respect to this plane. And when the former is also satisfied
$$
\left(\frac{\partial \Phi}{\partial R}\right)_{(R_g,0)}=\frac{L_z^2}{R_g^3}=R_g\dot\phi^2
$$
which is simply the condition for a circular orbit with angular speed $\dot\phi$. $R_g$ is known as the **guiding-center radius**, since $(R_g,0)$ is the center of a group of closed isopotential curves.



### Surfaces of section

When it is difficult to visualize the 4-D motion ($R,z,p_R,p_z$), we can determine whether orbits in the $(R,z)$ plane admit an additional isolating integral.

Since the Hamiltonian is a constant, we could plot the motion in the reduced phase space, say $(R,z,p_R)$, and $|p_z|$ will be determined.

An even simpler solution for visualizing the 4-D motion indirectly is to plot the points where the star crosses some plane, say $z=0$. Such a plot is known as a **surface of section**.

- **Consequents**: the points $(R,p_R)$ where a star crosses the plane $z=0$ (when $p_z>0$ to remove the sign ambiguity in $p_z$)
- **Zero-velocity curve**: the curve bounding the possible orbits in the plane $z=0$, on which $E=\Phi_{eff}$
- **Shell orbit**: the trajectory of the star restricted to a 2-D motion
- **Invariant curve**: a smooth curve on which the consequents of an orbit lie, suggesting the existence of some isolating integral $I(R,p_R)_{z=0}=Const$ - the **third integral**, no analytical form



### Nearly circular orbits

Now we take a look at some nearly circular orbits. Since they are close to circles, $R$ should not be far from $R_g$ ($z=0$) and we can define $x=R-R_g$ to be the separation, with which we expand the effective potential
$$
\Phi_{eff}(R)=\Phi_{eff}(R_g)+\frac12\frac{\partial^2\Phi_{eff}}{\partial R^2}\Bigg|_{(R_g,0)}x^2+\frac12\frac{\partial^2\Phi_{eff}}{\partial z^2}\Bigg|_{(R_g,0)}z^2+\mathcal O({xz^2})
$$
The first-order derivatives both vanish, as well as the second-order mixed partial derivative, because $\Phi_{eff}$ is assumed to be symmetric about $z=0$

Two new quantities are thus defined
$$
\kappa^{2}\left(R_{\mathrm{g}}\right) \equiv\left(\frac{\partial^{2} \Phi_{\mathrm{eff}}}{\partial R^{2}}\right)_{\left(R_{\mathrm{g}}, 0\right)}=\left(\frac{\partial^2\Phi}{\partial R^2}\right)_{(R_g,0)}+\frac3{R_g}\left(\frac{\partial \Phi}{\partial R}\right)_{(R_g,0)}
$$

$$
\nu^{2}\left(R_{\mathrm{g}}\right) \equiv\left(\frac{\partial^{2} \Phi_{\mathrm{eff}}}{\partial z^{2}}\right)_{\left(R_{\mathrm{g}}, 0\right)}=\left(\frac{\partial^{2} \Phi}{\partial z^{2}}\right)_{\left(R_{\mathrm{g}}, 0\right)}
$$

so that
$$
\ddot x=-\kappa^2x,\quad \ddot z=-\nu^2z
$$
We call $\kappa$ and $\nu$ **epicycle frequency** and **vertical frequency**, respectively.

Since the **circular frequency** $\Omega$ is given by
$$
\Omega^2(R)=\frac{1}{R}\left(\frac{\partial \Phi}{\partial R}\right)_{(R,0)}=\frac{L_z^2}{R^4}
$$
we can rewrite $\kappa$ as
$$
\kappa^2(R_g)=\left[\frac{\partial}{\partial R}(R\Omega^2)+3\Omega^2\right]_{R_g}=\left[R\frac{\partial \Omega^2}{\partial R}+4\Omega^2\right]_{R_g}
$$
In this way, the radius and azimuthal periods are simply
$$
T_r=\frac{2\pi}{\kappa},\quad T_\psi=\frac{2\pi}{\Omega}
$$
Then
$$
1<\frac{T_\psi}{T_r}<2\Rightarrow 1<\frac{\kappa}{\Omega}<2\Rightarrow \Omega<\kappa<2\Omega
$$
If we further define the so-called **Oort constants** to be
$$
A\equiv\frac{1}{2}\left(\frac{v_{\mathrm{c}}}{R}-\frac{\mathrm{d} v_{\mathrm{c}}}{\mathrm{d} R}\right)=-\frac{1}{2} R \frac{\mathrm{d} \Omega}{\mathrm{d} R}
$$

$$
B\equiv -\frac{1}{2}\left(\frac{v_{\mathrm{c}}}{R}+\frac{\mathrm{d} v_{\mathrm{c}}}{\mathrm{d} R}\right)=-\left(\Omega+\frac{1}{2} R \frac{\mathrm{d} \Omega}{\mathrm{d} R}\right)
$$

which are much easier to be measured, then
$$
\Omega=A-B,\quad \kappa^2=-4B\Omega
$$
Now that we have measured $\kappa,\Omega,\nu$, how can we determine the properties of the galaxy, say, the density distribution $\rho(R,z)$?

Again we solve the Poisson equation, but in cylindrical coordinates
$$
\begin{align*}
4\pi G\rho&=\nabla^2\Phi\\
&=\frac{1}{R}\frac{\partial}{\partial R}\left(R\frac{\partial \Phi}{\partial R}\right)+\frac{\partial^2 \Phi}{\partial z^2}\\
&=\frac{1}{R}\frac{\partial v_c^2}{\partial R}+\nu^2\approx\nu^2
\end{align*}
$$
since $v_c$ is approximately a constant.

On the other hand, if the mass distribution is approximately spherical, we have
$$
\Omega^2\sim\frac{GM}{R^3}=\frac43\pi G\bar\rho
$$
where $\bar\rho$ is the mean density within radius $R$, so
$$
\kappa^2=\left[R\frac{\partial \Omega^2}{\partial R}+4\Omega^2\right]_{R_g}=\left[R\frac{\partial (v_c/R)^2}{\partial R}+4\Omega^2\right]_{R_g}\sim2\Omega^2=\frac{8}{3}\pi G\bar\rho
$$
Thus
$$
\frac{\nu^2}{\kappa^2}(R)\simeq\frac{3\rho(R)}{2\bar\rho}
$$
In this way, the ratio $\nu^2/\kappa^2$ reflects the degree to which the galactic material is concentrated

Consider the radial motion more specifically, we have the general solution
$$
x(t)=X\cos(\kappa t+\alpha)
$$
The corresponding angular speed $\dot \phi$ is
$$
\dot\phi=\frac{L_z}{(R_g+x)^2}\simeq \frac{L_z}{R_g^2}\left(1-\frac{2x}{R_g}\right)= \Omega\left(1-\frac{2x}{R_g}\right)
$$

$$
\Rightarrow\phi=\phi_0+\Omega t-\frac{2\Omega}{R_g}\cdot\frac{X}{\kappa}\sin(\kappa t+\alpha)\equiv\phi_0+\Omega t-\gamma\frac{X}{R_g}\sin(\kappa t+\alpha)
$$

where
$$
\gamma\equiv\frac{2\Omega}{\kappa}=-\frac{\kappa}{2B}
$$
Now we try to understand the shape of the **epicycle**, which, to the first order, should be an ellipse. The X-semi-axis is obviously $X$, while in the $y$ direction perpendicular to both $x$ and $z$
$$
y=\Delta\phi R_g=-\gamma X\sin(\kappa t+\alpha)\Rightarrow Y=\gamma X
$$
Thus
$$
\left|\frac XY\right|=\frac{\kappa}{2\Omega}
$$
Usually
$$
\frac12<\left|\frac XY\right|<1
$$
while $X/Y=1/2$ for Kepler potential and $X/Y=1$ for harmonic oscillator potential (homogeneous sphere).