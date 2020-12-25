# Chapter 5 Redshifts and Distances

## Cosmological Redshifts

$$
1+z_e=\frac{a_0}{a(t=e)}
$$

$e$ stands for the era when the photons were emitted

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
  \dot{a}^{2}=H_{0}^{2} \Omega_{\mathrm{m}, 0} a^{-1}+H_{0}^{2} \Omega_{\Lambda, 0} a^{2}-k
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

The distance between event A and B, which happens **simultaneously** - a universal time $t$ - only useful when $s/c\ll1/H$

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

  - Flat universe, $k=0$, the proper distance is the coordinate distance
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

  - the particle horizon represents the largest comoving distance from which light could have reached the observer by a specific time
  - the event horizon is the largest comoving distance from which light emitted now can *ever* reach the observer in the future

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

  - When the light rays were emitted, the universe was smaller and certain proper diameter distance occupied a larger coordinate size

  - $z_{max}$ stands for an emission distance equal to the particle horizon at the time of emission

  - Einstein-de Sitter cosmology - $z_{max}=1.25$
    $$
    \delta \theta_{\min }=\delta \theta\left(z_{\mathrm{m}}\right)=3.375 \frac{H_{0} D}{c}
    $$
    A galaxy cluster of typical diameter 1 Mpc, would never subtend on the sky an angle smaller than
    $$
    \delta \theta_{\min }=\frac{3.375 \cdot 100 h \cdot 1}{3 \times 10^{5}} \simeq 1.13 \times 10^{-3} h \text { radians } \simeq 4 h \text { arcmin }
    $$

### Luminosity Distance

$$
F_{\mathrm{obs}}=\frac{L}{4 \pi d_{\mathrm{L}}^{2}}
$$

$L$ is the absolute bolometric luminosity (all wavelengths), but is not observable, and $F$ is the observed flux

- The photons emitted are spread out over the surface of a sphere
  $$
  A=4\pi r_1^2
  $$

- but the total power received at $r_1$ is not the same with the total power emitted because of the red shift

  - Emitted - wavelength $\lambda_1$ in time interval $\delta t_1$

  - Received - wavelength $\lambda_0$ in time interval $\delta t_0$

  - Wavelengths and time intervals are related by
    $$
    \frac{\lambda_{1}}{\lambda_{0}}=\frac{\delta t_{1}}{\delta t_{0}}=\frac{a_{1}}{a_{0}}
    $$
    while the energy of a single photon is $hc/\lambda$, the energy emitted/received in time interval $\delta t$ is thus
    $$
    \frac{hc}{\lambda\delta t}
    $$
    hence the ratio of received flux and emitted flux is
    $$
    \frac{a_{1}^{2}}{a_{0}^{2}}
    $$

- The flux measured on the surface of the sphere is then
  $$
  F_{\mathrm{obs}}=L \cdot \frac{1}{4 \pi a_{0}^{2} r_{1}^{2}} \cdot \frac{a_{1}^{2}}{a_{0}^{2}}
  $$
  for $a_0=1$, we have
  $$
  d_{\mathrm{L}}=\frac{r_{1}}{a_1}=(1+z) r_{1}
  $$
  or
  $$
  d_{\mathrm{L}}(z)=\frac{c(1+z)}{\sqrt{\left|\Omega_{\mathrm{k}, 0}\right|} H_{0}} S_{k}\left(H_{0} \sqrt{\left|\Omega_{\mathrm{k}, 0}\right|} \int_{0}^{z} \frac{d z}{H(z)}\right)=(1+z)^{2} \cdot d_{\mathrm{A}}
  $$

### The deceleration parameter

- $r_1$ - radial distance

- $d_P$ - proper distance

- $d_A$ - angular distance

- $d_L$ - luminosity distance

- For small $z$ and small $r_1$
  $$
  d_{\mathrm{P}} \simeq d_{\mathrm{A}} \simeq d_{\mathrm{L}} \simeq r_{1}
  $$

- For small $z$, using Taylor expansion
  $$
  E(z)=\Omega_{\mathrm{m}, 0}(1+3 z)+\left(1-\Omega_{\mathrm{m}, 0}-\Omega_{\Lambda, 0}\right)(1+2 z)+\Omega_{\Lambda, 0}=1+2z(1+q_0)
  $$
  where
  $$
  q_0=\frac{\Omega_{\mathrm{m}, 0}}{2}-\Omega_{\Lambda, 0}
  $$

- The parameter
  $$
  q(t)=-\frac{1}{H^{2}} \frac{\ddot{a}}{a}=-a \frac{\ddot{a}}{\dot{a}^{2}}
  $$
  is called deceleration parameter

  - $q<0$ , acceleration of expansion
  - $q>0$, slowing down of expansion
  - At present - accelerating
  
- The approximation of luminosity distance for small $z$
  $$
  \int_{0}^{z} \frac{d z}{H(z)}=\frac{1}{H_{0}} \int_{0}^{z} \frac{d z}{E(z)^{1 / 2}} \approx \frac{1}{H_{0}} \int_{0}^{z}\left[1-z\left(q_{0}+1\right)\right] d z \approx \frac{1}{H_{0}}\left[z-\left(q_{0}+1\right) \frac{z^{2}}{2}\right]
  $$

  $$
  d_{\mathrm{L}}=(1+z) r_{1} \approx \frac{c}{H_{0}}\left[z+\frac{1}{2}\left(1-q_{0}\right) z^{2}+\cdots\right]
  $$

  

