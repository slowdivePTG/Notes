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
  \ddot R=R(\dot\phi+\Omega_b)^2-\frac{\partial\Phi(R,\phi)}{\partial R}\\
  \frac{\text d}{\text dt}\left[R^2(\dot\phi+\Omega_b)\right]=-\frac{\partial\Phi(R,\phi)}{\partial \phi}
  $$
  since we regard the weak bar as perturbation, we also divide $R$ and $\phi$ into zeroth- and first-order parts
  $$
  R(t)=R_0+R_1(t),\quad \phi(t)=\phi_0(t)+\phi_1(t)
  $$
  For the zeroth-order
  $$
  R_0(\dot\phi_0+\Omega_b)^2=\left(\frac{\text d\Phi_0}{\text dR}\right)_{R_0},\quad \ddot\phi_0=0
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
  
The equations of motion yield
  $$
  \ddot R_1=\left(R_0+R_1\right)\left(\dot \phi_0+\dot \phi_1+\Omega_b\right)^2-\left[\frac{\partial}{\partial R}\left(\Phi_0+\Phi_1\right)\right]_{R_0+R_1}
  $$
  
  $$
  \frac{\text d}{\text dt}\left[(R_0+R_1)(\dot\phi_0+\dot\phi_1+\Omega_b)\right]=-\left[\frac{\partial}{\partial \phi}\left(\Phi_0+\Phi_1\right)\right]_{\phi_0+\phi_1}
  $$
  
  Since
  $$
  \begin{align*}
  \left[\frac{\partial}{\partial R}\left(\Phi_0+\Phi_1\right)\right]_{R_0+R_1}
  &=\left[\frac{\partial}{\partial R}\left(\Phi_0+\Phi_1\right)\right]_{R_0}+\left[\frac{\partial^2}{\partial R^2}\left(\Phi_0+\Phi_1\right)\right]_{R_0}R_1\\
  &=\left(\frac{\partial\Phi_0}{\partial R}\right)_{R_0}+\left[\frac{\partial\Phi_1}{\partial R}+\frac{\text d^2\Phi_0}{\text d R^2}R_1\right]_{R_0}+\mathcal{O(R_1^2)}\\
  \end{align*}
  $$
  
  $$
  \begin{align*}
  \left[\frac{\partial}{\partial \phi}\left(\Phi_0+\Phi_1\right)\right]_{\phi_0+\phi_1}
  &=\left(\frac{\partial\Phi_0}{\partial \phi}\right)_{\phi_0}+\left[\frac{\partial\Phi_1}{\partial \phi}+\frac{\partial^2\Phi_0}{\partial \phi^2}\phi_1\right]_{R_0}+\mathcal{O(\phi_1^2)}\\
  &=\left(\frac{\partial\Phi_1}{\partial \phi}\right)_{R_0}+\mathcal{O(\phi_1^2)}
  \end{align*}
  $$
  
  for the first-order, we have
  $$
  \begin{align*}
  \ddot R_1
  &=\left(R_0+R_1\right)\left(\dot \phi_0+\dot \phi_1+\Omega_b\right)^2-\left(\frac{\partial\Phi_0}{\partial R}\right)_{R_0}-\left[\frac{\partial\Phi_1}{\partial R}+\frac{\text d^2\Phi_0}{\text d R^2}R_1\right]_{R_0}\\
  &=2R_0\dot\phi_1\left(\dot\phi_0+\Omega_b\right)+R_1\left(\dot \phi_0+\dot \phi_1+\Omega_b\right)^2-\left[\frac{\partial\Phi_1}{\partial R}+\frac{\text d^2\Phi_0}{\text d R^2}R_1\right]_{R_0}\\
  &\equiv2R_0\Omega_0\dot\phi_1+R_1\left(\Omega^2-\frac{\text d^2\Phi_0}{\text d R^2}\right)_{R_0}-\left(\frac{\partial\Phi_1}{\partial R}\right)_{R_0}
  \end{align*}
  $$
  
  $$
  \iff \ddot R_1-2R_0\Omega_0\dot\phi_1+R_1\left(\frac{\text d^2\Phi_0}{\text d R^2}-\Omega^2\right)_{R_0}=-\left(\frac{\partial\Phi_1}{\partial R}\right)_{R_0}
  $$
  
  and
  $$
  \begin{align*}
  0
  &=\frac{\text d}{\text dt}\left[(R_0+R_1)^2(\dot\phi_0+\dot\phi_1+\Omega_b)\right]+\left[\frac{\partial}{\partial \phi}\left(\Phi_0+\Phi_1\right)\right]_{\phi_0+\phi_1}\\
  &=2(R_0+R_1)\dot R_1\Omega_0+(R_0+R_1)^2\ddot\phi_1 +\left(\frac{\partial\Phi_1}{\partial \phi}\right)_{R_0}\\
  &=2R_0\dot R_1\Omega_0+R_0^2\ddot\phi_1 +\left(\frac{\partial\Phi_1}{\partial \phi}\right)_{R_0}
  \end{align*}
  $$
  
  $$
  \iff \ddot\phi_1+2\Omega_0\frac{\dot R_1}{R_0}=-\frac1{R_0^2}\left(\frac{\partial\Phi_1}{\partial \phi}\right)_{R_0}
  $$
  
  To proceed further we must select a specific form of $\Phi_1$
  $$
  \Phi_1(R,\phi)=\Phi_b(R)\cos(m\phi),\quad \Phi_b(R)<0
  $$
  where $m\in N^*$, since any potential that is an **even function** of $\phi$ can be expanded as a Fourier series. If $m=2$ the potential is **barred**.
  
  At first we assume that $\phi_1\ll1$ and hence $\phi(t)$ always remains close to $(\Omega_0-\Omega_b)t$. With this assumption we have
  $$
  \ddot R_1-2R_0\Omega_0\dot\phi_1+R_1\left(\frac{\text d^2\Phi_0}{\text d R^2}-\Omega^2\right)_{R_0}\equiv-\left(\frac{\text d\Phi_b}{\text d R}\right)_{R_0}\cos\left[m\left(\Omega_0-\Omega_b\right)t\right]
  $$
  
  $$
  \ddot\phi_1+2\Omega_0\frac{\dot R_1}{R_0}=\frac{m\Phi_b(R_0)}{R_0^2}\sin\left[m\left(\Omega_0-\Omega_b\right)t\right]
  $$
  
  $$
  \Rightarrow \dot \phi_1=-2\Omega_0\frac{R_1}{R_0}-\frac{\Phi_b(R_0)}{R_0^2\left(\Omega_0-\Omega_b\right)}\cos\left[m\left(\Omega_0-\Omega_b\right)t\right]+Const
  $$
  
  Then we can eliminate $\dot\phi_1$ from the equations
  $$
  \ddot R_1+4R_1\Omega_0^2+\frac{2\Omega_0\Phi_b(R_0)}{R_0\left(\Omega_0-\Omega_b\right)}\cos\left[m\left(\Omega_0-\Omega_b\right)t\right]+R_1\left(\frac{\text d^2\Phi_0}{\text d R^2}-\Omega^2\right)_{R_0}\equiv-\left(\frac{\text d\Phi_b}{\text d R}\right)_{R_0}\cos\left[m\left(\Omega_0-\Omega_b\right)t\right]+Const
  $$
  
  $$
  \iff \ddot R_1+\left(\frac{\text d^2\Phi_0}{\text d R^2}+3\Omega^2\right)_{R_0}R_1=-\left[\frac{\text d\Phi_b}{\text d R}+\frac{2\Omega\Phi_b}{R_0\left(\Omega-\Omega_b\right)}\right]_{R_0}+Const
  $$
  
  We define
  $$
  \kappa^2=\frac{\text d^2\Phi_0}{\text d R^2}+3\Omega^2
  $$
  and
  $$
  \kappa_0^2=\left(\frac{\text d^2\Phi_0}{\text d R^2}+3\Omega^2\right)_{R_0}=\left(R\frac{\text d\Omega^2}{\text d R}+4\Omega^2\right)_{R_0}\quad\left(\kappa_0^2<4\Omega_0^2\right)
  $$
  since
  $$
  \frac{\text d^2\Phi_0}{\text d R^2}
  =\frac{\text d(R\Omega^2)}{\text d R}=R\frac{\text d\Omega^2}{\text d R}+\Omega^2
  $$
  $\kappa_0$ is just the usual **epicycle frequency**. The constant in the equation is not important as it can be absorbed into $R_1$. Then we have got an equation of motion of a harmonic oscillator of natural frequency of $\kappa_0$ that is driven at a frequency of $m\left(\Omega_0-\Omega_b\right)$. The general solution is
  $$
  R_1(t)=C_1\cos(\kappa_0t+\alpha)-\left[\frac{\text d\Phi_b}{\text d R}+\frac{2\Omega\Phi_b}{R_0\left(\Omega-\Omega_b\right)}\right]_{R_0}\frac{\cos\left[m\left(\Omega_0-\Omega_b\right)t\right]}{\Delta}
  $$
  where $C_1$ and $\alpha$ are arbitrary constants, and
  $$
  \Delta\equiv \kappa_0^2-m^2\left(\Omega_0-\Omega_b\right)^2
  $$
  We may also eliminate $t$ from this solution with the equation $\phi_0=\left(\Omega_0-\Omega_b\right)t$
  $$
  R_1(\phi_0)=C_1\cos\left(\frac{\kappa_0t}{\Omega_0-\Omega_b}+\alpha\right)+C_2\cos(m\phi_0)
  $$
  where
  $$
  C_2=-\frac{1}{\Delta}\left[\frac{\text d\Phi_b}{\text d R}+\frac{2\Omega\Phi_b}{R_0\left(\Omega-\Omega_b\right)}\right]_{R_0}
  $$
  If $C_1=0$, $R_1(\phi_0)$ becomes periodic in $\phi_0$ with period $2\pi/m$, so the orbit is a closed loop one. Orbits with $C_1\neq0$ are non-closed loop ones parented by this closed loop. 
  
  For the $C_1=0$ case, there are two sorts of singular points
  
  - $\Omega_0-\Omega_b=0$
  - $\Delta=0$
  
  The former, of which $\Omega_0=\Omega_b$, corresponds to the case of **corotation resonance**. The guiding center simply corotates with the potential.
  
  The latter, of which $m\left(\Omega_0-\Omega_b\right)=\pm\kappa_0$, is known as **Lindblad resonances**. Radii at which such resonances occur are called **Lindblad radii**.
  
  - Inner Lindblad resonance - plus sign - larger $\Omega_0$
  - Outer Lindblad resonance - minus sign - smaller $\Omega_0$
  
- Orbits trapped at resonance

  When $R_0$ approches the radius of either a Linblad resonance or the corotation resonance, the value of $R_1$ predicted with linear approximation diverges, thus we should modify the analysis.

  In the previous analysis we have assumed $\phi_1\ll1$, which is not neccessarily satisfied. If the bar strength $\Phi_1$ is proportional to some small parameter $\epsilon$, we assume $\phi_1$ is of order unity, $R_1$ is of order $\epsilon^{1/2}$, and the time derivative of any quantity is smaller than that quantity by of order $\epsilon^{1/2}$. When we further put the guiding center at $L_5$, the equations of motion go like
  $$
  \ddot R_1+\left(\kappa_0^2-4\Omega_0^2\right)R_1-2R_0\Omega_0\dot\phi_1=-\left(\frac{\partial\Phi_1}{\partial R}\right)_{R_0}
  $$

  $$
  \ddot\phi_1+2\Omega_0\frac{\dot R_1}{R_0}=-\frac1{R_0^2}\left(\frac{\partial\Phi_1}{\partial \phi}\right)_{R_0}
  $$

  According to our ordering, in the first equation, $\ddot R_1$ is of order $\epsilon^{3/2}$, $\Phi_1$ is of order unity, while other terms are of order $\epsilon^{1/2}$. In the second equation, each term is of order $\epsilon^{1/2}$. Thus
  $$
  \left(\kappa_0^2-4\Omega_0^2\right)R_1-2R_0\Omega_0\dot\phi_1=0,\quad \ddot\phi_1+2\Omega_0\frac{\dot R_1}{R_0}=-\frac1{R_0^2}\left(\frac{\partial\Phi_1}{\partial \phi}\right)_{R_0}
  $$

  $$
  \Rightarrow\ddot\phi_1\left(\frac{\kappa_0^2}{\kappa_0^2-4\Omega_0^2}\right)=-\frac1{R_0^2}\left(\frac{\partial\Phi_1}{\partial \phi}\right)_{\left(R_0,\phi_0+\phi_1\right)}
  $$

  Recall $\Phi_1=\Phi_1(R,\phi)=\Phi_b(R)\cos(m\phi)$ and let $m=2$
  $$
  \ddot\phi_1=-\frac{2\Phi_b}{R_0^2}\left(\frac{4\Omega_0^2-\kappa_0^2}{\kappa_0^2}\right)\sin\left[2\left(\phi_0+\phi_1\right)\right]
  $$
  where $\Phi_b<0$. At $L_5$ we have $\phi_0=\pi/2$, so
  $$
  \ddot\phi_1=\frac{2\Phi_b}{R_0^2}\left(\frac{4\Omega_0^2-\kappa_0^2}{\kappa_0^2}\right)\sin\left(2\phi_1\right)
  $$

  $$
  \iff \ddot\psi=-p^2\sin\psi
  $$

  where $\psi=2\phi_1$, and
  $$
  p^2=-\frac{4\left|\Phi_b\right|}{R_0^2}\left(\frac{4\Omega_0^2-\kappa_0^2}{\kappa_0^2}\right)
  $$
  This is simply the equation of a pendulum. Here the singularity appeared at corotation ($\Omega_0=\Omega_b$) no longer exists in this more careful analysis. Also, the stable equilibrium point of the pendulum, $\phi_1 = 0$, is at the maximum, not the minimum, of the potential $\Phi_1$ (the donkey effect).

  - The donkey effect - *in azimuth stars behave like donkeys, slowing down when pulled forwards and speeding up when held back* - Lynden–Bell & Kalnajs (1972)

  If the integral of motion
  $$
  E_p=\frac12\dot\psi^2-p^2\cos\psi
  $$
  is less than $p^2$, the star oscillates slowly or **librates** about the Lagragian point, whereas if $E_p>p^2$, the star is not trapped by the bar but **circulates** about the center of the galaxy.

  For small oscillations, the libration frequency is $p$.

  We may also obtain the shape of the orbit
  $$
  R_1=\frac{R_0\Omega_0}{\kappa_0^2-4\Omega_0^2}\dot\psi=\pm \frac{R_0\Omega_0}{\kappa_0^2-4\Omega_0^2}\sqrt{2\left[E_p+p^2\cos\left(2\phi_1\right)\right]}
  $$
  