# Basics of Cosmological Physics

**Physical Processes in an Expanding Universe**

*Yingjie Peng, KIAA 204, yjpeng@pku.edu.cn*

## Chapter 0

### Isotropic & Homogeneous

- Counts of faint galaxies in different directions
- CMB ( 99% of photons in the universe ) - low fluctuations ( $10^{-5}\ \mathrm{K}$ )

### Expansion

- Hubble (1929) redshift-distance relation
  $$
  z=\frac{H_0}{c}d,\ v=H_0d
  $$

- Scatter of galaxies - peculiar motions

### Cosmic distance ladder

- Cepheids
- Ia SN



## Chapter 1 Introduction

### Fundamental Observers

- Fluid (Plasma)
- Substratum (相对宇宙静止)——comoving
- **We are not fundamental observers!** (velocity relative to the sun, the Galactic center, M31, Virgo Cluster…) - subtract all the relative velocity - confirmed by highly isotropic CMB

### Distances

- 1 AU = 1.5e13 cm
- 1 Parsec = 3.26 ly, mostly kpc or Mpc (8.7 kpc away from the Galactic center)
- Radius of the Observable Universe (Inside the horizon) $\sim$ 4450 Mpc ( $c/H_0$ )

### Masses

- Solar mass $M_\odot$ = 2e33 g
- Milky Way
  - Stellar mass $\sim​$ 1e11 $M_\odot​$
  - Total mass $\sim$ 1e12 $M_\odot$

### Luminosity and Magnitudes

- For flux $F$ and apparent magnitude $m$

$$
F_1/F_2=10^{0.4(m_2-m_1)}
$$

- Absolute magnitude $M$ - a distance of 10 pc

$$
m-M=2.5\lg\left(\frac{d\ \mathrm{(pc)}}{10}\right)^2=5\lg d-5
$$

### Cosmological Principle

- Homogeneous - each point is ordinary
- Isotropic - each direction is ordinary
- Copernican Principle - humans, on the Earth or in the Solar System, are not privileged observers of the universe
- Universal cosmic time

### Redshifts

$$
z=\frac{\lambda_{obs}-\lambda_0}{\lambda_0},\mathrm{or}\ 1+z=\frac{\lambda_{obs}}{\lambda_0}
$$

- Doppler Redshift is associated with a speed of recession

  $$
  v=cz,\ v\ll c\\
  1+z=\sqrt{\frac{1+\beta}{1-\beta}},\ \text{in general}
  $$
  The SR case is used when, for example, measuring the ejection velocity of gas clouds ejected from AGNs

- We will prove that
  $$
  1+z=\frac{\lambda_{obs}}{\lambda_0}=\frac{a_{obs}}{a_{em}}
  $$
  where $a$ is the scale factor of the universe，$em$ stands for emission

### Universal Expansion

- 1929 Hubble Law - observing Cepheids

$$
v=H_0d\\
H_0\approx 70\ \mathrm{km/s/Mpc}=100\cdot h\ \mathrm{km/s/Mpc}
$$

- Today - Ia SN
- Hubble time

$$
t_H\equiv \frac{1}{H_0}\sim14\ \mathrm{Gyr}
$$

### Components of the Universe

$$
E_{tot}=\sqrt{m^2c^4+p^2c^2}
$$

- Non-relativistic $pc\ll mc^2$

$$
E_{tot}\approx mc^2+\frac{p^2}{2m}
$$

#### Baryons

- Proton + Neutron + Electron
  - None relativistic
  - 0.5% stars
  - 4% Hydrogen/Helium
  - 0.03% heavy elements

#### 0.3% Neutrinos

- mass > 0
- Relativistic

#### Radiation

- $E=h\nu=hc/\lambda$, 0 mass

#### 21% Dark Matter

- Evidence
  - Rotation velocity of galaxies
  - Cluster
  - Gravitational lensing

#### 74% Dark Energy

- Accelerate universal expansion after z = 1

#### Critical Density

$$
\rho_c=\frac{3H_0^2}{8\pi G}=1.36\times 10^{11}\ M_\odot/\text{Mpc}
$$



## Chapter 2 Newtonian Cosmology

<img src="./fig/IMG_0619.jpg" style="zoom:30%" />
$$
\vec v_A=H_0 \vec r_A,\ \vec v_B=H_0 \vec r_B
$$

- Recession velocity if B as seen by A is

  $$
  \vec v_{BA}=\vec v_B-\vec v_A=H_0(\vec r_B-\vec r_A)
  $$
  Hubble expansion is a natural property of an expanding universe that obeys the cosmological principle

### Comoving coordinates

- coordinates that are carried along with the expansion

- comoving with space distance $\vec r$, comoving distance $\vec x$ (constant)

  $$
  \vec r_{BA} = a(t)\cdot\vec x_{BA}
  $$
  $a(t)$ is the scale factor - all we want to find out

- Birkhoof's theorem: the net gravitational effect of a uniform **external** medium on a spherical cavity is zero, the net gravitational effect comes from matter internal to radius $r$ (as a mass point)

  total energy of a particle of mass $m$ at A, B, C, D

  $$
  U=T+V=\frac{1}{2}m\dot{r}^2-\frac{GMm}{r}=\frac{1}{2}m\dot{r}^2-\frac{4\pi}{3}G\rho r^2m
  $$

### Friedmann equation

$$
\left(\frac{\dot{a}}{a}\right)^2=\frac{8\pi G}{3}\rho-\frac{kc^2}{a^2},\ \text{where }kc^2=-\frac{2U}{mx^2}
$$

- $k$ must be independent of $x$, therefore $U\propto x^2$ 

- $k$ is a independent of $t$, for $U​$ is conserved

- Thus $k$ is just a constant

  - $k>0\Rightarrow U<0, |V|>T$ , collapse
  - $k<0\Rightarrow U<0, V<T$ , expand forever
  - $k=0\Rightarrow U=0$ , expansion terminates when $t\to\infty$

- Hubble parameter
  $$
  \vec v=H_0\vec r,\ \vec r=a\vec x\\
  \Rightarrow \vec v=|\dot{\vec r}|\hat{\vec r}=\frac{\dot a}{a}\vec r\\
  \Rightarrow H\equiv \frac{\dot a}{a}
  $$
  which is a function of time, so called Hubble constant $H_0$ is the Hubble parameter at present

- Using Hubble parameter we can rewrite Friedmann equation

  $$
  H^2=\frac{8\pi G}{3}\rho-\frac{kc^2}{a^2}
  $$
  if $k=0$ , the **critical density** $\rho$ is then
  $$
  \rho_c=\frac{3H_0^2}{8\pi G}
  $$

- In thermodynamics, the first law points that

  $$
  \text{d} E+P\text dV=T\text d S
  $$
  where $P$ is the pressure, $S$ is the entropy

- Expanding volume $V$ of unit comoving radius $x=1\ (r=a)$, $E=mc^2$, energy within the volume
  $$
  E=\frac{4\pi}{3}a^3\rho c^2\\
  \frac{\text dE}{\text{d} t}=4\pi a^2\rho c^2\frac{\text da}{\text{d} t}+\frac{4\pi}{3} a^3 c^2\frac{\text d\rho}{\text{d} t}\\
  \frac{\text dV}{\text{d} t}=4\pi a^2\frac{\text da}{\text{d} t}
  $$

- Assuming a reservable expansion $\text dS=0​$ , we obtain the **fluid equation** 

  $$
  \dot\rho+3\frac{\dot a}{a}\left(\rho+\frac{P}{c^2}\right)=0
  $$

  - The first term - **the dilution in the density** because the volume has increased
  - The second term - **the loss in energy** because the pressure of the material has done work as the universe’s volume increased.

- Equation of state

  There is a unique pressure associated with each density,
  $$
  P\equiv P(\rho)
  $$

    - For non-relativistic matter, $P=0$ , **dust**
    - For highly-relativistic matter , $P=\rho c^2/3$ , **radiation pressure** of **light**

- Time-derivation on both sides of the Friedmann equation

  $$
  2\frac{\dot a}{a}\frac{a\ddot a-\dot a^2}{a^2}=\frac{8\pi G}{3}\dot\rho+2\frac{kc^2}{a^3}\dot a\\
  \frac{\ddot a}{a}-\left(\frac{\ddot a}{a}\right)^2=\frac{8\pi G}{3}\rho-\frac{kc^2}{a^3}
  $$

- Acceleration equation
  $$
  \frac{\ddot a}{a}=-\frac{4\pi G}{3}\left(\rho+\frac{3P}{c^2}\right)
  $$

- Analytical solution

  - $k=0$

    - Dust, $P=0$
      $$
      \dot\rho+3\frac{\dot a}{a}\rho=0\Rightarrow\frac{\text{d}}{\text{d}t}(\rho a^3)=0
      $$

      $$
      \rho=\frac{\rho_0}{a^3}\Rightarrow\dot a^2=\frac{8\pi G\rho_0}{3}\frac{1}{a}\\\Rightarrow a(t)=\left(\frac{t}{t_0}\right)^{2/3},\ \rho(t)=\frac{\rho_0t_0^2}{t^2}\\
      \Rightarrow H(t)=\frac{\dot a}{a}=\frac{2}{3t},\ t_0=\frac{2}{3H_0}
      $$

      However, the current age of universe $t_0​$ obtained in this model is wrong

    - Radiation, $P=\rho c^2/3$
      $$
      \dot\rho+4\frac{\dot a}{a}\rho=0\Rightarrow\frac{\text{d}}{\text{d}t}(\rho a^4)=0\\
      \Rightarrow a(t)=\left(\frac{t}{t_0}\right)^{1/2},\ \rho(t)=\frac{\rho_0t_0^2}{t^2}\\
      \Rightarrow H(t)=\frac{\dot a}{a}=\frac{1}{2t}<\frac{2}{3t},\ t_0=\frac{1}{2H_0}
      $$

    - Radiation dominated universe
      $$
      a(t)\propto t^{1/2},\ \rho_{rad}\propto t^{-2},\ \rho_{dust}\propto a^{-3}\propto t^{-3/2}
      $$
      Unstable, the radiation density decreases faster than the dust density, the universe will turn to matter dominated on day

    - Matter dominated universe
      $$
      a(t)\propto t^{2/3},\ \rho_{dust}\propto t^{-2},\ \rho_{dust}\propto a^{-4}\propto t^{-8/3}
      $$
      Stable

### Olber's Paradox

- In a shell from $r​$ to $r+\mathrm d r​$, the total number of stars is $4\pi r^2n_0\mathrm d r​$, where $n_0​$ is the number density
- Total intensity of the sky

  $$
  \mu=\int_0^{r_{max}}4\pi r^2n_0\left(\frac{L_0}{4\pi r^2}\right)\mathrm d r=n_0L_0r_{max}\\
  r_{max}\to\infty\Rightarrow \mu\to\infty
  $$

  which is $10^{13}$ times brighter than it actually is

- Thermodynamic problem
  - Infinite volume
  - Infinite time to reach thermodynamic equilibrium
  - BUT the universe is not homogeneous (not the temperature of CMB)



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



## Chapter 4 World Models

- Scalar factor: $a(t)$
   natural units: $c=1$
   $$
   \left(\frac{\dot a}{a}\right)^2 + \frac{k}{a^2} = \frac{8\pi}{3}G\rho\\
    H(t)\equiv \frac{\dot a}{a},\quad \rho_\Lambda=\frac{\Lambda}{8\pi G}\\
    H^2 + \frac{k}{a^2} = \frac{8\pi G}{3}\left(\sum_i\rho_i+\rho_\Lambda\right)
   $$

    $k=0​$, flat
   $$
   \rho_\text{tot} = \sum_i\rho_i+\rho_\Lambda=\frac{3H^2}{8\pi G}\equiv\rho_\text{crit}
   $$
    define $\Omega_i\equiv\rho_i/\rho_\text{crit}$
   $$
   \left\{
    \begin{aligned}
    &\Omega_m: \text{matter}\\
    &\Omega_r: \text{radiation}\\
    &\Omega_\Lambda: \text{dark energy}
    \end{aligned}
    \right.
   $$
    all are functions of time.
    Deriving
   $$
   \frac{k}{a^2H^2}=\sum_i\Omega_i + \Omega_\Lambda - 1
   $$
    define 
   $$
   \Omega_k \equiv -k/a^2H^2\\
   \Rightarrow \sum_i\Omega_i+\Omega_\Lambda+\Omega_k=1
   $$
   

### Flat FRW Cosmologies

- Friedmann-Robertson-Walker: FRW models

- Assuming pressureless matter $ P=0$
   $\Omega_k=0\Rightarrow$ flat cosmologies
   $$
   \rho_m = \rho_{m,0}\left(\frac{a}{a_0}\right)^{-3}
   $$
   define $a_0\equiv1$
   $$
   \left(\frac{\dot a}{a}\right)^2 = \frac{8\pi G}{3}\rho_{m,0}a^{-3}+\frac{\Lambda}{3}\\
    \dot a^2=H_0^2\Omega_{m,0}a^{-1} + H_0^2\Omega_{\Lambda,0}a^2\\
    \Omega_{m,0}+\Omega_{\Lambda,0}=1
   $$

    - $\Lambda>0$
      $$
      u=\frac{2\Omega_{\Lambda,0}}{\Omega_{m,0}}a^3\\
      \dot u^2 = 9H_0^2\Omega_{\Lambda,0}(2u+u^2)=3\Lambda(2u+u^2)
      $$
      do integration to $u$, derive
      $$
      a^3=\frac{\Omega_{m,0}}{2\Omega_{\Lambda,0}}[\cosh(3\Lambda)^{1/2}t-1]
      $$

       - For small $t$, $a\propto t^{2/3}$
      - For large $t$, $a\propto e^{[(\Lambda)/3]^{1/2}t}$

    - $\Lambda<0$
      $$
      u=-\frac{2\Omega_{\Lambda,0}}{\Omega_{m,0}}a^3\\
      a^3=\frac{\Omega_{m,0}}{2(-\Omega_{\Lambda,0})}\{1-\cosh[3(-\Lambda)]^{1/2}t\}
      $$

       - For small $t$, $a\propto t^{2/3}$
       - For large $t$, $a\propto -e^{[(-\Lambda)/3]^{1/2}t}​$

    - $\Lambda=0​$
      Einstein-de Sitter
      $$
      a = \left(\frac{t}{t_0}\right)^{2/3}\\
      t_0=\frac{2}{3H_0}\\
      a = \left(\frac{9}{4}H_0^2t^2\right)^{1/3}
      $$

   - A flat, pressureless universe with a small, but non-zero, cosmological constant **initially evolves as if it were Einstein-deSitter**

### Cosmologies with $k\neq0,\ \Lambda=0$ 

$$
\left(\frac{\dot a}{a}\right)^2+\frac{k}{a^2}=\frac{8\pi G}{3}\rho\\
\dot a^2=\Omega_{m,0}H_0^2a^{-1}-k=\Omega_{m,0}H_0^2a^{-1}+\Omega_{k,0}H_0^2\\
\Omega_{m,0}+\Omega_{k,0} = 1
$$

- $\Omega_{k,0}>0, k<0$, negative curvature
  $$
  \dot a^2\sim\Omega_{k,0}H_0^2=-k>0, \ a\propto t
  $$
  $a$ grows linearly with time

- $\Omega_{k,0}<0, k>0​$, positive curvature

  let $\dot a=0$, derive $a_{max}$
  $$
  a_{\max }=\frac{\Omega_{\mathrm{m}, 0}}{\left|\Omega_{\mathrm{k}, 0}\right|}
  $$

![](/Users/chang/Desktop/宇宙学/fig/a_t.png)

|      | $\Omega_{m,0}$ | $\Omega_{\Lambda,0}$ | $\Omega_{k,0}$ |            Concordance cosmology             |
| :--: | :------------: | :------------------: | :------------: | :-----------------------------------: |
|  1   |      0.3       |         0.7          |       0        |      $a\propto\exp[(\Lambda/3)^{1/2}t]$      |
|  2   |      0.3       |          0           |      0.7       |                 $a\propto t$                 |
|  3   |       1        |          0           |       0        | $a = \left(\frac{9}{4}H_0^2t^2\right)^{1/3}$ |
|  4   |       4        |          0           |       -3       |                $a_{max}=4/3$                 |

- The age of universe can be an indirect proof for acceleration of universe expansion, for only universe with high $\Omega_\Lambda​$ can give a universe age old enough (global cluster)



## Chapter 5 Redshifts and Distances

### Cosmological Redshifts

$$
1+z_e=\frac{a_0}{a(t=e)}
$$

$e​$ stands for the era when the photons were emitted

- For r > 4200 Mpc, the receding velocity is larger than the speed of light

**PROOF**

- RW metric
  $$
  (d s)^{2}=(c d t)^{2}-a^{2}(t)\left[\frac{d r^{2}}{1-k r^{2}}+r^{2}\left(d \theta^{2}+\sin ^{2} \theta d \phi^{2}\right)\right]
  $$

  - None geodesic means $ds=0$ - propagation of light
  - Observer $r=0$
  - Radial geodesic $d\theta=d\phi=0$

  Then the equation reduces to
  $$
  \frac{c d t}{a(t)}=\pm \frac{d r}{\left(1-k r^{2}\right)^{1 / 2}}
  $$

- Imagine one crest of the light wave was emitted at $(t_e, r_e)$ and received at $(t_0,0)$, and the next crest was emitted at $(t_e+dt_e, r_e)$ (the comoving distance did not change) and received at $(t_0+dt_0,0)$

- The time it takes for successive crests to travel to earth
  $$
  \int_{t_{e}}^{t_{0}} \frac{d t}{a(t)}=-\frac{1}{c} \int_{r_{e}}^{0} \frac{d r}{\sqrt{1-k r^{2}}}
  $$
  'minus' means the light travels toward us

  For the two crests we have
  $$
  \int_{t_{e}+\Delta t_{e}}^{t_{0}+\Delta t_{0}} \frac{d t}{a(t)}-\int_{t_{e}}^{t_{0}} \frac{d t}{a(t)}=0
  $$
  But
  $$
  \int_{t_{e}+\Delta t_{e}}^{t_{0}+\Delta t_{0}} \frac{d t}{a(t)}=\int_{t_{e}}^{t_{0}} \frac{d t}{a(t)}+\int_{t_{0}}^{t_{0}+\Delta t_{0}} \frac{d t}{a(t)}-\int_{t_{e}}^{t_{e}+\Delta t_{e}} \frac{d t}{a(t)}\\
  \Rightarrow \int_{t_{0}}^{t_{0}+\Delta t_{0}} \frac{d t}{a(t)}=\int_{t_{e}}^{t_{e}+\Delta t_{e}} \frac{d t}{a(t)}
  $$

- $\Delta t_0$ and $\Delta t_e$ are so small that $a(t)$ is nearly a constant during those periods
  $$
  \frac{\Delta t_{e}}{\Delta t_{0}}=\frac{a\left(t_{e}\right)}{a\left(t_{0}\right)}
  $$

- $\Delta t$ reflects the frequency, in fact
  $$
  \lambda=c\Delta t
  $$
  and therefore
  $$
  \frac{\lambda_{0}}{\lambda_{e}}=1+z=\frac{a\left(t_{0}\right)}{a\left(t_{e}\right)}\Rightarrow a(t_e)=(1+z)^{-1}
  $$

- $z$ as a measure for time

### Time Evolution of the Hubble Parameter

- Friedmann equation
  $$
  \dot{a}^{2}=H_{0}^{2} \Omega_{\mathrm{m}, 0} a^{-1}+H_{0}^{2} \Omega_{\Lambda, 0} a^{2}
  $$
  The definition of $\Omega_k$
  $$
  \Omega_{\mathrm{k}} \equiv-k /(a H)^{2}
  $$
  Then
  $$
  \left(\frac{H(z)}{H_{0}}\right)^{2}=\Omega_{\mathrm{m}, 0} \cdot(1+z)^{3}+\Omega_{\mathrm{k}, 0} \cdot(1+z)^{2}+\Omega_{\Lambda, 0}\equiv E(z)
  $$

  $$
  H(z)=H_{0} \cdot E(z)^{1 / 2}
  $$

  - Einstein-de Sitter cosmology ($\Omega_{m,0}=1$)
    $$
    H(z)=H_{0} \cdot(1+z)^{3 / 2}
    $$

  - Today's consensus cosmology ($\Omega_{k,0}=0$)
    $$
    H(z)=H_{0} \cdot \sqrt{\Omega_{\mathrm{m}, 0} \cdot(1+z)^{3}+\Omega_{\Lambda, 0}}
    $$

  - A more general model including radiation
    $$
    \frac{H(z)}{H_{0}}=\sqrt{\Omega_{\mathrm{m}, 0}(1+z)^{3}+\Omega_{\mathrm{rad}, 0}(1+z)^{4}+\Omega_{\mathrm{k}, 0}(1+z)^{2}+\Omega_{\Lambda, 0}}
    $$
    for radiation density reduces
    $$
    \rho\propto a^{-4}
    $$

    - Volume $V\propto a^{-3}$
    - Energy per photon $\epsilon\propto\nu\propto a^{-1}$
    - Only import at high redshift, early universe (high temperature) - radiation drives the early expansion 

    Note that $\Omega_{\mathrm{m}, 0}(1+z)^{3}\sim\Omega_{\Lambda, 0}$ gives $z\sim0.3$, for smaller $z$ the dark energy dominates

### Redshift vs. Time

- The definition of Hubble parameter
  $$
  H(z) \equiv \frac{d a}{d t} \frac{1}{a}=\frac{d a}{d z} \frac{d z}{d t} \frac{(1+z)}{a_{0}}
  $$
  The scale factor
  $$
  a=\frac{a_{0}}{1+z} \Rightarrow d a=-\frac{a_{0}}{(1+z)^{2}} d z
  $$
  and therefore
  $$
  d t=-\frac{d z}{H(z)(1+z)}
  $$

  $$
  \int_{t_1}^{t_2} d t=-\frac{1}{H_{0}} \int_{z_1}^{z_2} \frac{d z}{(1+z) E(z)^{1 / 2}}
  $$

  again, if $t_1>t_2$ we have $z_1<z_2$

- The age of the Universe
  $$
  t_{0}=\int_{0}^{t_{0}} d t=\frac{1}{H_{0}} \int_{0}^{\infty} \frac{d z}{(1+z) E(z)^{1 / 2}}
  $$

  - Einstein-de Sitter model
    $$
    t_{0}=\frac{1}{H_{0}} \int_{0}^{\infty} \frac{d z}{(1+z)^{5 / 2}}=\frac{2}{3} H_{0}^{-1}\left.(1+z)^{-3 / 2}\right|_{\infty} ^{0}=\frac{2}{3} H_{0}^{-1}
    $$



## Cosmological Distances

### Proper Distance

$$
dt=0
$$

The distance between event A and B, which happens simultaneously - a universal time $t$

- RW Metric
  $$
  (d s)^{2}=(c d t)^{2}-a^{2}(t)\left[\frac{d r^{2}}{1-k r^{2}}+r^{2}\left(d \theta^{2}+\sin ^{2} \theta d \phi^{2}\right)\right]
  $$

  $$
  s(t)=\int_{0}^{s} d s^{\prime}=a(t) \int_{0}^{r} \frac{d r}{\left(1-k r^{2}\right)^{1 / 2}}
  $$

- Three solutions
  $$
  s(t)=a(t)\cdot\left\{\begin{array}{cc}{\frac{1}{\sqrt{k}} \sin ^{-1}(r \sqrt{k})} & {\text { for } k>0} \\ {r} & {\text { for } k=0} \\ {\frac{1}{\sqrt{|k|}} \sinh ^{-1}(r \sqrt{|k|})} & {\text { for } k<0}\end{array}\right.
  $$

  - Flat universe, $k=0​$, the proper distance is the coordinate distance

  - Positive curvature, $k=1$, $s(t)>a(t)\cdot r$

### The Horizon

- Proper distance to the furthest observable point, **the particle horizon**, at time $t$, is the horizon distance $S_h(t)$

- $(0, r_{hor})\to(t,0)$, consider photons, $ds=0,d\theta=d\phi=0$
  $$
  \int_{0}^{t} \frac{d t}{a(t)}=\frac{1}{c} \int_{0}^{r_{\mathrm{hor}}} \frac{d r}{\left(1-k r^{2}\right)^{1 / 2}}
  $$
  for which we find that
  $$
  r_{\mathrm{hor}}=\left\{\begin{array}{cc}{\sin \left(c \int_{0}^{t} \frac{d t}{a(t)}\right)} & {\text { for } k=1} \\ {c \int_{0}^{t} \frac{d t}{a(t)}} & {\text { for } k=0} \\ {\sinh \left(c \int_{0}^{t} \frac{d t}{a(t)}\right)} & {\text { for } k=-1}\end{array}\right.
  $$
  where $r_{hor}$ is the radial coordinate distance

- If $k=0$
  $$
  adr=-cdt=-\frac{c}{\dot a}da=-\frac{c}{Ha}da=-\frac{c}{Ha}\frac{da}{dz}dz
  $$

  $$
  \frac{da}{dz}=-\frac{a^2}{a_0}
  $$

  Thus
  $$
  a_0dr=\frac{c}{H}dz=\frac{c}{H_0E(z)^{1/2}}dz
  $$

  $$
  r=\frac{c}{H_0}\int\frac{dz}{E(z)^{1/2}}
  $$

  And
  $$
  r=c\int_{0}^{t} \frac{d t}{a(t)}
  $$

- At 4300 Mpc, the receding velocity is larger than the speed of light, but the horizon is larger than 4300 Mpc

  - What we see NOW are the photons emitted in the past, when the universe was much smaller

- If $a(t)\propto t^\alpha$ for small $t$ ($\alpha\ge1$), $r_{hor}$ diverges as we approach $t=0$ - no particle horizon

- But if we consider the proper distance from the origin to $r_{hor}$
  $$
  s_{\mathrm{hor}}(t)=a(t) \int_{0}^{r_{\mathrm{hor}}} \frac{d r}{\left(1-k r^{2}\right)^{1 / 2}}\\
  \Rightarrow s_{\mathrm{hor}}(t)=a(t) \int_{0}^{t} \frac{c d t}{a(t)}
  $$
  For zero curvature

  - In a radiational-dominated Universe, $a(t)\propto t^{1/2}$
    $$
    s_{\mathrm{hor}}(t)=2 c t
    $$

  - In a radiational-dominated Universe, $a(t)\propto t^{2/3}$
    $$
    s_{\mathrm{hor}}(t)=3 c t
    $$

  These distances are larger than $ct$

- **REASON**: in order to actually measure the size of the visible Universe at the present time, we would have to devise some contrived scenario—such as adding up distances measured by observers spread throughout the Universe all making measurements at the same time

- **The event horizon** - similar to the particle horizon, but set the limit on communications to the future

  $t\to t_{max}$ - admissible time

  - finite for closed models
  - infinite for flat and open universe

### Angular Diameter Distance

Consider a light source of size $D$ at $r=r_1, t=t_1$ subtending an angle $\delta\theta$ at the origin ($r=0,t=t_0$) . The proper distance between the two ends of object 
$$
D=a\left(t_{1}\right) r_{1} \delta \theta
$$
Angular diameter
$$
\delta \theta=\frac{D}{a\left(t_{1}\right) r_{1}}
$$
Angular diameter distance
$$
d_{\mathrm{A}} \equiv \frac{D}{\delta \theta}=a\left(t_{1}\right) r_{1}=\frac{r_{1}}{1+z}
$$

- Consider again the propagation of light, $ds=0$
  $$
  \int_{t_{1}}^{t_{0}} \frac{c d t}{a(t)}=c \int_{0}^{z} \frac{d z}{H(z)}=\frac{1}{|k|^{1 / 2}} S_{k}^{-1}\left(|k|^{1 / 2} r_{1}\right)
  $$
  where
  $$
  S_{k}(x)=\left\{\begin{array}{cc}{\sin (x)} & {\text { for } k>0} \\ {x} & {\text { for } k=0} \\ {\sinh (x)} & {\text { for } k<0}\end{array}\right.
  $$

  $$
  |k|^{1 / 2}=\frac{H_{0}}{c} \sqrt{\Omega_{\mathrm{k}, 0}}
  $$

  Thus
  $$
  d_{\mathrm{A}}(z)=\frac{c}{\sqrt{\left|\Omega_{\mathrm{k}, 0}\right|} H_{0}(1+z)} \cdot S_{k}\left(H_{0} \sqrt{\left|\Omega_{\mathrm{k}, 0}\right|} \int_{0}^{z} \frac{d z}{H(z)}\right)
  $$

- $d(z)$ depends on comological parameters $\Omega_{\Lambda, 0}, \Omega_{\mathrm{k}, 0},  \Omega_{\mathrm{m}, 0}$, while $\Omega_{k,0}=0$ according to the consensus cosmology today
  $$
  d_{\mathrm{A}}(z)=\frac{c}{H_{0}} \frac{1}{(1+z)} \int_{0}^{z} \frac{d z}{\left[\Omega_{\mathrm{m}, 0}(1+z)^{3}+\Omega_{\Lambda, 0}\right]^{1 / 2}}
  $$

- In some cosmologies $d_A(z)$ is not monotonically increasing function of $z$, for a given proper size $D$ will subtend a minimum angle $\delta\theta$ at $z=z_{max}$

  - Einstein-de Sitter cosmology - $z_{max}=1.25$
    $$
    \delta \theta_{\min }=\delta \theta\left(z_{\mathrm{m}}\right)=3.375 \frac{H_{0} D}{c}
    $$
    A galaxy cluster of typical diameter 1 Mpc, would never subtend on the sly an angle smaller than
    $$
    \delta \theta_{\min }=\frac{3.375 \cdot 100 h \cdot 1}{3 \times 10^{5}} \simeq 1.13 \times 10^{-3} h \text { radians } \simeq 4 h \text { arcmin }
    $$
    