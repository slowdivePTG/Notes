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

## Estimation of cosmological constant $\Omega_\Lambda$

- The luminosity distance $d_L$ is a function of redshift $z$, and there are usually two applications

  - Given observed flux $F_{obs}$, if we know the redshift of a certain galaxy and universe parameters well, we can calculate the luminosity distance, and then the absolute luminosity

  - Given observed flux $F_{obs}$, for some certain objects (Cepheids, SNe) we know the absolute luminosity and thus the luminosity distance. This will help us estimate $\Omega_m,\Omega_\Lambda$

    