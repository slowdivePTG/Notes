# Chapter 5* Monochromatic Flux, K-correction

## Monochromatic flux

- Difficult to measure **bolometric luminosity** - Astronomers use filters

- A photon with observed frequency $\nu$ has higher frequency $(1+z)\nu$ when emitted
  $$
  F_{\nu} \mathrm{d} \nu=\frac{L_{(1+z) \nu}}{4 \pi D_{L}^{2}} \mathrm{d}(1+z) \nu=(1+z) \frac{L_{(1+z) \nu}}{4 \pi D_{L}^{2}} \mathrm{d} \nu
  $$

  $$
  F_{\lambda} \mathrm{d} \lambda=\frac{L_{\lambda /(1+z)}}{4 \pi D_{L}^{2}} \mathrm{d} \lambda /(1+z)=\frac{1}{1+z} \frac{L_{\lambda /(1+z)}}{4 \pi D_{L}^{2}} \mathrm{d} \lambda
  $$

  We see the monochromatic flux is not related to the $\nu$ or $\lambda$ we receive

  Introduce the intrinsic flux
  $$
  F_{\lambda, \text {intrin}}=\frac{L_{\lambda}}{4 \pi D_{L}^{2}}
  $$
  we have
  $$
  F_\lambda=\frac{F_{\lambda, \text {intrin}}}{1+z}\frac{L_{\lambda /(1+z)}}{L_{\lambda}}
  $$

## K-correction

- Assume we use B band to calculate the distance module (DM) of a star
  $$
  m_{i n t r i n}=-2.5 \log F_{\lambda, i n t r i n}+\text {Const }=M+D M
  $$
  But for observation, the apparent magnitude is $m$ rather than $m_{intrin}$
  $$
  m=M+D M+K
  $$
  where $K$ is the K-correction
  $$
  \begin{array}{c}{K(z, \lambda)=-2.5 \log \left[\frac{1}{1+z} \frac{L_{\lambda /(1+z)}}{L_{\lambda}}\right]} \\ {K(z, \nu)=-2.5 \log \left[(1+z) \frac{L_{(1+z) \nu}}{L_{\nu}}\right]}\end{array}
  $$
  (not reliable for $z>1$)

## Surface brightness

- Define surface brightness as
  $$
  \mu=\frac{f}{\pi\theta^2}=\frac{fd_A^2}{\pi D^2}
  $$
  where $f$ is the observed flux, $\theta$ is the angular extension $D/d_A$

  Note that
  $$
  f=\frac{L}{4\pi d_L^2},\quad d_A=\frac{d_L}{(1+z)^2}
  $$
  we have
  $$
  \mu=\frac{L}{4\pi^2D^2(1+z)^4}=\frac{\mu_0}{(1+z)^4}
  $$

- For objects with high redshift, the surface brightness declines rapidly

- Similarly, we ca consider the bolometric and monochromatic fluxes
  $$
  \mu_{bol,obs}=\frac{\mu_{bol,em}}{(1+z)^4}
  $$

  $$
  \mu_{\nu}=\frac{\mu_{(1+z)\nu}}{(1+z)^3},\quad \mu_{\lambda}=\frac{\mu_{\lambda/(1+z)}}{(1+z)^5}
  $$

  This is used in the Tolman Test, which is consistent with the results from the RW metric

## Blackbody radiation

- Consider the emitted and the observed intensity (with is proportional to the surface brightness under isotropic assumption) with temperature $T$
  $$
  I_{\nu, e m}=\frac{2 h \nu^{3}}{c^{2}} \frac{1}{\exp \left(\frac{h \nu}{k T}\right)-1}
  $$

  $$
  \begin{align*}
  I_{\nu, obs}&=\frac{2 h (\nu(1+z))^{3}}{c^{2}} \frac{1}{\exp \left(\frac{h \nu(1+z)}{k T}\right)-1}\frac{1}{(1+z)^3}\\
  &=\frac{2 h \nu^{3}}{c^{2}} \frac{1}{\exp \left(\frac{h \nu}{k T/(1+z)}\right)-1}
  \end{align*}
  $$

- We see that it is still a blackbody spectrum, while the observed temperature is lower by a factor of $(1+z)$

- For CMB, $T_{obs}=2.73\text{ K}$, and back in the era of decoupling, $T\sim300\text{ K}$
  $$
  z_{em}\approx1100
  $$


# Chapter 6 Supernova cosmology

## Application of the Luminosity Distance

### Two main applications

- The luminosity distance $d_L$ is a function of redshift $z$, and there are usually two applications
  - Given observed flux $F_{obs}$, if we know the redshift of a certain galaxy and universe parameters well, we can calculate the luminosity distance, and then the absolute luminosity - luminosity function
  - Given observed flux $F_{obs}$, for some certain objects (Cepheids, SNe) we know the absolute luminosity and thus the luminosity distance - estimation of $\Omega_m,\Omega_\Lambda$

### Luminosity function

- Describes the number of galaxies per unit volume with luminosity in the range $[L, L+d L]$

- **Schechter function**
  $$
  \Phi(L) d L=\phi^{*}\left(\frac{L}{L^{*}}\right)^{\alpha} e^{-L / L^{*}} \frac{d L}{L^{*}}
  $$

  - $\alpha<0$ - Faint end slope (diverges at the faint end - there must be a turn-over)
  - $L^*$ - Characteristic (fiducial) luminosity
  - $\phi^*$ - Overall normalisation

- **Luminosity-weighted luminosity function** - $L\Phi(L)$

  - Converge if $\alpha>-2$

- Well fitted by a Schechter function in the local universe

### Distance modulus

$$
M-m=2.5\lg\left(\frac{d_{L,0}}{d_L}\right)^2=5\lg\frac{d_{L,0}}{d_L}
$$

For cosmology cases, 10 pc is too small and thus not practical, while 1 Mpc is usually used as $d_{L,0}$
$$
m=M+5\lg d_L(\text{Mpc})+25
$$
For small $z$, 
$$
d_L=(1+z)r_1\approx\frac{c}{H_{0}}\left[z+\frac{1}{2}\left(1-q_{0}\right) z^{2}+\cdots\right]
$$

$$
m=M-5 \log H_{0}+5 \log c z+\cdots+25
$$



## Type Ia Supernovae

- Nuclear explosions of carbon/oxygen white dwarfs in binary systems

- The peak luminosity appears to be well-correlated with decay time

  The larger $L_{peak}$, the slower the decay
  $$
  M_{B} \approx 0.8\left(\Delta m_{15}-1.1\right)-19.5
  $$

  - $M_B$ - peak absolute luminosity in B-band
  - $\Delta m_{15}$ - the observed change in apparent magnitude 15 days after the peak

- The maximum light of Type Ia Supernovae appears to be dimmer than that in an empty universe ($\Omega_k=1$) and that in a matter dominate universe ($\Omega_m=0.25,\ \Omega_\Lambda=0$)

- $\Omega_m\sim0.25,\ \Omega_\Lambda\sim0.75$ - accelerating universe

### Parameter estimation

- A sample of $n$ SN measurements
  - Magnitude $m_i$
  - Typical magnitude error $\pm \sigma_{m,i}$
  - Redshift $z_i$ (error can be neglected)
  - Try to estimate $\left(\Omega_{\mathrm{m}, 0}, \Omega_{\Lambda, 0}, M\right)$
    - Fix $M$ (with sufficient precision) and estimate $\Omega$s
    - **Fit simultaneously for all three**
  
- MLE

  - Likelihood function (assumption of Gaussian distribution)
    $$
    L(\theta) \propto \exp \left[-\frac{1}{2} \sum_{i=1}^{n}\left(\frac{m\left(z_{i} ; \theta\right)-m_{i}}{\sigma_{m, i}}\right)^{2}\right]
    $$
    where
    $$
    \theta =\left(\Omega_{\mathrm{m}, 0}, \Omega_{\Lambda, 0}, M\right)
    $$

  - We are not interested in $M$ so we take integration over $M$ to get the 2-D likelihood function
    $$
    L\left(\Omega_{\mathrm{m}, 0}, \Omega_{\Lambda, 0}\right)=\int d M L\left(\Omega_{\mathrm{m}, 0}, \Omega_{\Lambda, 0}, M\right)
    $$

  - We can generate $L$ in the phase space of $\left(\Omega_{\mathrm{m}, 0}, \Omega_{\Lambda, 0}\right)$ to get the estimator, and compare the allowed region (in the phase space) under certain confident levels with other tests (cluster, CMB, BAO, etc.) to narrow it down
  
  - $\Omega_{\mathrm{m}, 0} \simeq 0.3, \Omega_{\Lambda, 0} \simeq 0.7, \Omega_{\mathrm{k}, 0} \simeq 0$



## Alternative Explanations

*Astrophysical dimming*

### Evolution

- The properties of SNIa events have evolved with cosmic time (different $z$)
  - SN at high $z$ - younger population
  - Lower metallicity (abundances of carbon/oxygen)
- So far, no evidence

### Intersellar dust

- Supernovae in distant galaxies are more (or less) dimmed by dust than local supernovae
- Normal dust not only **dim** but also **redden** the light, then by comparing the colors of local/distant SNe, we may assess the importance of the effect
- No difference in reddening 

### Grey dust

- Strange particles - significantly larger than the wavelength of light, scatter light of **all wavelength** similarly

### Assessments

- Push the measurement of SN Ia light curves to redshifts $z > 1$
  - Back in $z\sim1$, the $\Lambda$ term begins to become comparable to the matter term
  - For $z>1$, the $\Lambda$ term is negligible and SNe should be **brighter** again



## Dark Energy

- The energy density related to the cosmological constant (natural units)
  $$
  \rho_{\Lambda} \equiv \frac{\Lambda}{8 \pi G}=\mathrm{constant}
  $$
  The fluid equation
  $$
  \dot{\rho}_\Lambda=-3(\rho_\Lambda+p_\Lambda) \frac{\dot{a}}{a}=0\Rightarrow p_{\Lambda}=-\rho_{\Lambda}
  $$

- We introduce constant $\omega_i$
  $$
  p_i=w_{i} \rho_{i}
  $$
  Then the fluid equation becomes
  $$
  \frac{\dot{\rho}_{i}}{\rho_{i}}=-3\left(1+w_{i}\right) \frac{\dot{a}}{a}\Rightarrow \rho_{i} \propto a^{-n_{i}}
  $$
  where $n_{i}=3\left(1+w_{i}\right)$, then we have a useful property
  $$
  \frac{\Omega_{i}}{\Omega_{j}} \propto a^{-\left(n_{i}-n_{j}\right)}
  $$

- Recall our discussions in Chapter 2

  - Dust (matter)
    $$
    \rho_{m} \propto a^{-3}\Rightarrow\omega_m=0
    $$

  - Radiation
    $$
    \rho_{r} \propto a^{-4}\Rightarrow\omega_r=\frac13
    $$

  - Cosmological constant
    $$
    \rho_\Lambda\propto a^0\Rightarrow \omega_\Lambda=-1
    $$

  - Curvature
    $$
    \Omega_{k} \equiv-k /(a H)^{2}\Rightarrow\rho_k\propto a^{-2}\Rightarrow \omega_k=-\frac13
    $$

- Hubble parameter
  $$
  H(a)=H_{0}\left(\sum_{i} \Omega_{i, 0} a^{-n_{i}}\right)^{1 / 2}
  $$

- Deceleration parameter
  $$
  q(t)=-\frac{1}{H^{2}} \frac{\ddot{a}}{a}
  $$

  - Friedmann equation
    $$
    \frac{\ddot a}{a}=-\frac{4\pi G}{3}(\rho+3p)
    $$
		Then
    $$
    \begin{align*}
    q(t)&=\frac{4\pi G}{3H^2}(\rho+3p)=\frac12\frac{\rho+3p}{\rho_c}\\
    &=\frac12\sum_{i}(1+3\omega_i)\Omega_i\\
    &=\frac12\sum_{i}(n_i-2)\Omega_i
    \end{align*}
    $$
    
- Recall that
  
  - $q<0$ , acceleration of expansion - $n_i<2$, cosmological constant
    - $q>0$, slowing down of expansion - $n_i>2$, matter, radiation
    - $q=0$, linear expansion - $n_i=2$, empty universe
  
- Most recent results of $\omega$
  $$
  \omega=-1.007\pm0.081
  $$

- The evolution of $\omega$
  $$
  w(a)=w_{0}+w_{a}(1-a)
  $$

  $$
  w_{0}=-1.02 \pm0.12,\ w_{{a}}=0.07 \pm 0.6
  $$

  

  