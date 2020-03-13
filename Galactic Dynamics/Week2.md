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
   \delta \theta=2\theta_{cri}-\pi
   $$
   where
   $$
   \theta_{cri}=\pi-\arccos(a/c)=\arccos(-1/e)
   $$
   In this way,
   $$
   \delta\theta=2\arccos(-1/e)-\pi=2\arcsin(1/e),\quad e\gg1\Rightarrow\Delta\theta\ll1
   $$
   In fact, when $e\gg1$, we have
   $$
   \delta\theta\sim1/e=\left(1+\frac{2EL^2}{G^2m^2}\right)^{-1/2}\sim\sqrt{\frac{G^2m^2}{2EL^2}}=\frac{Gm}{{v_\infty^2} b}=\frac{r_{inf}}{b}
   $$
   $r_{inf}$ is a typical impact parameter with which $\Delta \theta$ becomes significant
   $$
   e\sim\sqrt{2}\Rightarrow\frac{2EL^2}{G^2m^2}\sim1\Rightarrow b\sim\frac{Gm}{v^2_\infty}\equiv r_{inf}
   $$

### Relaxation

When a star moves in a cluster, the direction of the velocity will change under the impact of all other stars. We would like to estimate the timescale in which the orbit/initial velocity of a star significantly change ($\Delta\theta$ in velocity $\sim1$)

- When the star moves in the cluster
  $$
  \left\langle\vec\theta_f^2\right\rangle=\left\langle\left(\vec\theta_0+\sum_{i}\delta\vec\theta_i\right)^2\right\rangle=
   \left\langle\vec\theta_0^2\right\rangle
  +\left\langle\vec\theta_0\sum_{i}\delta\vec\theta_i\right\rangle
  +\left\langle\sum_{i}\left(\delta\vec\theta_i\right)^2\right\rangle
  +\left\langle\sum_{i\neq j}\delta\vec\theta_i\delta\vec\theta_i\right\rangle
  $$
  where $\langle\rangle$ stands for taking average

  Obviously, the second and the fourth terms vanish as each $\delta\vec\theta_i$ is **random** and **independent**, so we are extremely interested in the third term
  $$
  \left\langle\sum_{i}\left(\delta\vec\theta_i\right)^2\right\rangle=N\left\langle\left(\delta\vec\theta\right)^2\right\rangle\sim N\left(\frac{r_{inf}}{b}\right)^2\sim1
  $$
  where $N$ is the number of stars that have impact on the star we consider

- A more realistic model

  ![](impact.eps)

  The number of stars lying within the ring $b\sim b+\text{d}b$ can be estimated with the surface/column density (number within an unit area) $\sigma$
  $$
  \delta N=2\pi b\text{d}b\cdot \sigma\sim2\pi b\text{d}b\cdot\frac{N_*}{\pi R_*^2}
  $$
  where $N_*$ is the total star number in the cluster and $R_*$ is the cluster's radius

  So every time the star **crosses** the cluster
  $$
  \begin{align*}
  \left\langle\Delta\left(\theta^2\right)\right\rangle&=\int\delta N\left\langle(\delta\theta)^2\right\rangle\\
  &\sim\frac{2\pi N_*}{\pi R_*^2}\int_{b_{min}}^{R_*}\left(\frac{r_{inf}}{b}\right)^2 b\text{d}b
  \end{align*}
  $$
  but note that the approximation
  $$
  \delta\theta\sim\frac{r_{inf}}{b}
  $$
  is valid only when $b$ is large, say, $b>r_{inf}$, so we have to rewrite the integral
  $$
  \begin{align*}
  \left\langle\Delta\left(\theta^2\right)\right\rangle
  &\sim\frac{2N_*r_{inf}^2}{R_*^2}\left[\int_{r_{inf}}^{R_*}\frac{\text{d}b}{b}+\int_{b_{min}}^{r_{inf}}\varphi(b){\text{d}b}\right]\\
  &=\frac{2N_*r_{inf}^2}{R_*^2}\left[\ln\frac{R_*}{r_{inf}}+\int_{b_{min}}^{r_{inf}}\varphi(b){\text{d}b}\right]
  \end{align*}
  $$
  It's not easy to estimate the second term. For some systems it is negligible, usually when $b_{min}$ is large ($\sim R_{\odot}$) and is comparable to $r_{inf}$, which is true for stellar clusters. Anyway, we simply drop that term...
  $$
  \left\langle\Delta\left(\theta^2\right)\right\rangle
  \sim\frac{2N_*r_{inf}^2}{R_*^2}\ln\frac{R_*}{r_{inf}}\equiv \frac{2N_*r_{inf}^2}{R_*^2}\ln\Lambda
  $$
  The typical crossing number for that angle to become significant is
  $$
  N_{cross}=\frac{1}{\left\langle\Delta\left(\theta^2\right)\right\rangle}
  $$
  And the relaxation timescale
  $$
  \begin{align*}
  T_{relax}&=t_{cross}N_{cross}\sim\frac{2R_*}{v}\cdot \frac{R_*^2}{2N_*r_{inf}^2\ln\Lambda}\\
  &=\frac{R_*^3}{N_*v\ln\Lambda}\frac{v^4}{G^2m^2}\\
  &\sim\frac{R_*^3}{N_*v\ln\Lambda}\frac{G^2m^2N_*^2}{G^2m^2R_*^2}\quad\left(v^2\sim\frac{GM_*}{R_*}=\frac{GmN_*}{R_*}\right)\\
  &=\frac{N_*}{\ln\Lambda}\cdot\frac{R_*}{v}\\
  &=\frac{N_*}{\ln N_*}\cdot\frac{R_*}{v} \quad\left(\Lambda=\frac{R_*}{r_{inf}}=\frac{R_*v^2}{Gm}=\frac{GmN_*R_*}{GmR_*}=N_*\right)
  \end{align*}
  $$
  $T_{relax}\ll T_{Hubble}\Rightarrow$ Collisional - the cluster has changed a lot since it was formed

  - Star cluster
  $$
    N_*\sim10^5,\ T_{cross}\sim\frac{R_*}{v}\sim\frac{1\text{ pc}}{10 \text{ km/s}}\sim10^5\text{ yr}
    $$
  
    $$
    T_{relax}\sim10^{8-9}\text{ yr}\ll 10^{10}\text{ yr}\sim Age
    $$
  
  $T_{relax}\gg T_{Hubble}\Rightarrow$ Collisionless - the cluster remains what it looked like before
<<<<<<< HEAD




#### Examples

- Star clusters

  ​	$N = 10^5,\ R\approx 1\,\text{pc},\ v\approx 10\,\text{km/s}$. 

​	It's good to know that $1\,\text{km/s}\approx 1\,\text{pc/Myr}$, thus
$$
T_{\text{crossing}} \sim \frac{R_*}{v} \sim \frac{1\ \text{pc}}{10\ \text{km/s}}\sim \frac{1\ \text{pc}}{10 \text{pc/Myr}} = 10^5\ \text{yr},\\
T_{\text{relax}} \sim \frac{10^5}{5\ln 10}\times 10^5\ \text{yr} \sim 10^9\ \text{yr} = 1\ \text{Gyr}.
$$
​	Hence, within the Hubble time, a star cluster can be fully relaxed. A typical star cluster is collisional. 

- Galaxy

  ​	$N = 10^11,\ R\approx 10\,\text{kpc},\ v\approx 100\,\text{km/s}$. 

  $$
  T_{\text{crossing}} \sim \frac{R_*}{v} \sim \frac{10\ \text{kpc}}{100\ \text{km/s}}\sim \frac{10^4\ \text{pc}}{10^2 \text{pc/Myr}} = 10^2\ \text{Myr},\\
  T_{\text{relax}} \sim \frac{10^{11}}{11\ln 10}\times 10^2\ \text{Myr} \sim 10^{17}\ \text{yr} = 10^8\ \text{Gyr}.
  $$
  
  The relaxation timescale of a typical galaxy is way higher than the Hubble time.
=======
  
  - Galaxy
    $$
    N_*\sim10^{11},\ T_{cross}\sim\frac{R_*}{v}\sim\frac{10\text{ kpc}}{100 \text{ km/s}}\sim10^8\text{ yr}
    $$
  
    $$
    T_{relax}\sim10^{17-18}\text{ yr}\gg T_{Hubble}
    $$
  
    
>>>>>>> 1800a8d81a43bcd1eb43cf9322f959ecf1bf7497
