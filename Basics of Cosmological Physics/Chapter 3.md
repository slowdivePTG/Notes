## Chapter 3 Relativistic Cosmology

### Robertson-Walker Metric

- Flat (Euclid) space
  $$
  (\text{d}l)^2=(\text{d}x)^2+(\text{d}y)^2+(\text{d}z)^2\\
  \Rightarrow \Delta l=\int_1^2\sqrt{(\text{d}x)^2+(\text{d}y)^2+(\text{d}z)^2}
  $$

- Flat (Minkowski) spacetime
  $$
  (\text{d}l)^2=(c\text{d}t)^2-(\text{d}x)^2-(\text{d}y)^2-(\text{d}z)^2\\
  \Rightarrow \Delta l=\int_1^2\sqrt{(c\text{d}t)^2-(\text{d}x)^2-(\text{d}y)^2-(\text{d}z)^2}
  $$

- Proper distance

  distance at $t_A=t_B$ (hypothesis on the existence of a well-defined universal time)

- Curvature
  $$
  K=\frac{3}{\pi}\lim_{D\to 0}\frac{2\pi D-C}{D^3}
  $$
  where $D​$ is the radius, $C​$ is the perimeter

  Some **2-D​** examples

  - Plain - zero curvature
  - Sphere - positive curvature
  - Hyperbolic paraboloid (马鞍面；双曲抛物面) - negative curvature

- 2-D curvature

  Spherical polar coordinates $(r,\theta,\phi)$
  $$
  \begin{aligned}
  (\text{d}l)^2&=(\text{d}D)^2+(r\text{d}\phi)^2\\
  &=(R\text{d}\theta)^2+(r\text{d}\phi)^2\\
  &=\left(\frac{\text{d}r}{\cos\theta}\right)^2+(r\text{d}\phi)^2\\
  &=\left(\frac{\text{d}r}{\sqrt{1-r^2/R^2}}\right)^2+(r\text{d}\phi)^2
  \end{aligned}
  $$
  In general, 2-D curvature
  $$
  (\text{d}l)^2=\left(\frac{\text{d}r}{\sqrt{1-kr^2}}\right)^2+(r\text{d}\phi)^2
  $$

- 3-D curvature
  $$
  (\text{d}l)^2=\left(\frac{\text{d}r}{\sqrt{1-kr^2}}\right)^2+(r\text{d}\theta)^2+(r\sin\theta\text{d}\phi)^2
  $$

- R-W Metric
  $$
  (\text ds)^2=(c\text dt)^2-\left(\frac{\text{d}r}{\sqrt{1-kr^2}}\right)^2-(r\text{d}\theta)^2-(r\sin\theta\text{d}\phi)^2
  $$

  - Proper distance
    $$
    \Delta L=\sqrt{(-\Delta s)^2},\ \text dt=0
    $$

  - Comoving distance
    $$
    K(t)=\frac{k}{a^2(t)},\ r(t)=a(t)x\\
    \Rightarrow (\text ds)^2=(c\text dt)^2-a^2(t)\left[\left(\frac{\text{d}x}{\sqrt{1-kx^2}}\right)^2-(x\text{d}\theta)^2-(x\sin\theta\text{d}\phi)^2\right]
    $$
    Traditionally, we use $r$ to represent **comoving radial distance**
    $$
    \Rightarrow (\text ds)^2=(c\text dt)^2-a^2(t)\left[\frac{\text{d}r^2}{1-kr^2}-r^2(\text{d}\theta^2+\sin^2\theta\text{d}\phi^2)\right]
    $$

- SR model - [the Milne Model](https://en.wikipedia.org/wiki/Milne_model) - **empty universe**

  <img src="./fig/World_line.png" style="zoom:30%" />
  - Time dilution
    $$
    \tau=\gamma^{-1}t\\
    (t,r)\Rightarrow(\tau,l)
    $$
    

### Friedmann Equation

- Einstein's field equation
  $$
  G_{\alpha\beta}=\frac{8\pi G}{c^2}T_{\alpha\beta}
  $$

  - Einstein tensor
    $$
    G_{\alpha\beta}=R_{\alpha\beta}-\frac{1}{2}g_{\alpha\beta}R
    $$

  - Metric
    $$
    \mathrm ds^2=g_{\alpha\beta}\mathrm dx^\alpha\mathrm dx^\beta
    $$
    

- Friedmann equation
  $$
  \left(\frac{\dot{a}}{a}\right)^2+\frac{kc^2}{a^2}=\frac{8\pi G}{3}\rho\\
  \frac{\ddot a}{a}=-\frac{4\pi G}{3}\left(\rho+\frac{3P}{c^2}\right)
  $$
  the second is known as acceleration equation

- At present time
  $$
  \Omega_0=\frac{\rho_0}{\rho_c},\ \rho_c=\frac{3H_0^2}{8\pi G}
  $$
  rewrite Friedmann equation
  $$
  \dot a_0^2=\frac{8\pi}{3}Ga_0^2\rho_0-kc^2\\
  \Rightarrow H_0^2a_0^2=H_0^2a_0^2\Omega_0-kc^2\\
  \Rightarrow kc^2=H_0^2a_0^2(\Omega_0-1),\ k=+1,0,-1
  $$

  - $\Omega_0>1$, overcritical density, $k=+1$
  - $\Omega=1$, critical density, $k=0$
  - $0<\Omega_0<1$, undercritical density, $k=-1$

- Difference between Newtonion cosmology

  - Newtonion
    $$
    kc^2=-\frac{2U}{mc^2}
    $$

  - GR, $k$ stands for curvature

### Cosmological constant

- Static universe

  - $a$ is a constant, $\dot a=\ddot a=0$

  - $H=0$

  - Age of the universe is infinite

  - Friedmann equation
    $$
    \frac{kc^2}{a^2}=\frac{8\pi G}{3}\rho=-\frac{8\pi G}{c^2}P_0
    $$

  - To make sure that $\rho>0$, $P_0<0$ , Einstein introduced a constant, Lorentz-invariant term $\Lambda$
    $$
    G_{\alpha\beta}-\Lambda{g_{\alpha\beta}}=\frac{8\pi G}{c^4}T_{\alpha\beta}
    $$
    rewrite Friedmann equation
    $$
    \left(\frac{\dot{a}}{a}\right)^2+\frac{kc^2}{a^2}=\frac{8\pi G}{3}\rho+\frac{\Lambda c^2}{3}\\
    2\frac{\ddot a}{a}+\left(\frac{\dot{a}}{a}\right)^2+\frac{kc^2}{a^2}=-\frac{8\pi G}{c^2}P+\Lambda c^2
    $$

  - Define **vacuum energy density**
    $$
    \rho_{vac}=\frac{\Lambda c^2}{8\pi G}
    $$
    we have
    $$
    2\frac{\ddot a}{a}+\left(\frac{\dot{a}}{a}\right)^2+\frac{kc^2}{a^2}=-\frac{8\pi G}{c^2}(P-\rho_{vac})
    $$

  - For Newtonion cosmology, we have to introduce an additional potential energy term
    $$
    V_\Lambda\equiv-\frac{1}{6}\Lambda mc^2r^2
    $$

    $$
    \begin{aligned}
    \Rightarrow U&=T+V+V_\Lambda\\
    &=\frac{1}{2}m\dot{r}^2-\frac{4\pi}{3}G\rho r^2m-\frac{1}{6}\Lambda mc^2r^2
    \end{aligned}
    $$

    $$
    \Rightarrow \vec F_\Lambda=-\nabla V_\Lambda
    $$


