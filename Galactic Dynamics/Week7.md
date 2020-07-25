# Week7: Orbits

## Non-axisymmetric potentials

### Weak Bars

We choose a polar coordinate $(R,\phi)$ in which the line $\phi=0$ coincides with the long axis of the potential. Since we assume the bar is weak, we may write
$$
\Phi(R,\phi)=\Phi_0(R)+\Phi_1(R,\phi)
$$
where $\Phi_1/\Phi_0\ll1$ (Pertubation).

- Lindblad resonances (with a steady pattern speed $\Omega_b$)

  We seek to represent a general loop orbit as a superposition of the circular motion of a guiding center and small oscillations around this guiding center.

   Then the Lagrangian is
  $$
  \mathcal{L}=\frac12\dot R^2+\frac12\left[R(\dot\phi+\Omega_b)\right]^2-\Phi(R,\phi)
  $$
  So the equations of motion are
  $$
  \ddot R=R(\dot\phi+\Omega_b)-\frac{\partial\Phi(R,\phi)}{\partial R}\\
  \frac{\text d}{\text dt}\left[R(\dot\phi+\Omega_b)\right]=-\frac{\partial\Phi(R,\phi)}{\partial \phi}
  $$
  since we regard the weak bar as perturbation, we also divide $R$ and $\phi$ into zeroth- and first-order parts
  $$
  R(t)=R_0+R_1(t),\quad \phi(t)=\phi_0(t)+\phi_1(t)
  $$
  For the zeroth-order
  $$
  R_0(\dot\phi_0+\Omega_b)=\left(\frac{\text d\Phi_0}{\text dR}\right)_{R_0},\quad \ddot\phi_0=0
  $$
  which is the usual equation for centrifugal equilibrium at $R_0$. We further define $\Omega_0\equiv\Omega(R_0)$, where
  $$
  \Omega(R)=\pm\sqrt{\frac1R\frac{\text d\Phi_0}{\text dR}}
  $$
  is the circular frequency at $R$ in the potential $\Phi_0$. The angular speed for the circular motion then becomes
  $$
  \dot\phi_0=\Omega_0-\Omega_b
  $$
  we choose the origin of time so that
  $$
  \phi_0(t)=\left(\Omega_0-\Omega_b\right)t
  $$
  

  