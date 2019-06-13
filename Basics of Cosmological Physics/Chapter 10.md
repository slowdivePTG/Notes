# Chapter 10 Recombination and CMB

- Early universe - high electron density - Thomson scattering
  $$
  \sigma_{\mathrm{T}}=\frac{1}{6 \pi \epsilon_{0}^{2}}\left(\frac{\mathrm{e}^{2}}{m_{\mathrm{e}} c^{2}}\right)^{2}=6.6 \times 10^{-25}\ \mathrm{cm}^{2}
  $$
  Mean free path
  $$
  \lambda=\frac{1}{n_{\mathrm{e}} \sigma_{\mathrm{T}}}
  $$
  The rate at which a photon undergoes scattering
  $$
  \Gamma_{\mathrm{T}, \mathrm{e}}=\frac{c}{\lambda}=n_{\mathrm{e}} \sigma_{\mathrm{T}} c
  $$
  Optical depth
  $$
  \tau=\int \Gamma_{\mathrm{T}, \mathrm{e}}(t) d t
  $$

- Assuming the universe is totally ionized today that $n_{\mathrm{e}} \simeq n_{\mathrm{b}}=n_{\mathrm{b}, 0}(1+z)^{3}$
  $$
  \Gamma_{\mathrm{T}, \mathrm{e}} \simeq5 \times 10^{-21}(1+z)^{3} \mathrm{s}^{-1}
  $$

## Matter Domination

- Occurred at $z_{\text{eq}}=3380$, $T_{\mathrm{eq}}=2.7255 \times 3381=9215 \mathrm{K}$
- The expansion is then be driven by pressure less matter until either the curvature or the dark energy donimates

## Recombination

- Cooling universe - ions (protons and $\ce{He^2+}$) and electrons combine and form neutral atoms

- $n_\rm{e}$ decreases rapidly - $\Gamma_{\mathrm{T}, \mathrm{e}}$ drops below the expansion rate $H$ - the photons decouple from the electrons and can stream freely

- The temperature at which recombination takes place

  - Baryon-to-photon ratio $\eta$

  - Ionization potential of the species involved ($\ce{H}$ : $Q=13.6\text{ eV}$, neglect $\ce{He+}$ and $\ce{He^2+}$)
    $$
    \ce{H + \gamma <-> p + e-}
    $$

  - The distribution of particles with different masses (MB distribution)
    $$
    n_{\mathrm{x}}=g_{\mathrm{x}}\left(\frac{m_{\mathrm{x}} k T}{2 \pi \hbar^{2}}\right)^{3 / 2} \exp \left[-\frac{m_{\mathrm{x}} c^{2}}{k T}\right]
    $$
    Then for $\ce{H}$ atoms, protons and free electrons
    $$
    \frac{n_{\mathrm{H}}}{n_{\mathrm{p}} n_{\mathrm{e}}}=\frac{g_{\mathrm{H}}}{g_{\mathrm{p}} g_{\mathrm{e}}}\left(\frac{m_{\mathrm{H}}}{m_{\mathrm{p}} m_{\mathrm{e}}}\right)^{3 / 2}\left(\frac{k T}{2 \pi \hbar^{2}}\right)^{-3 / 2} \exp \left[\frac{\left(m_{\mathrm{p}}+m_{\mathrm{e}}-m_{\mathrm{H}}\right) c^{2}}{k T}\right]
    $$

    - The ratio of statistical weighs is 1
    - $m_{\ce H}\approx m_{\ce{p}}$
    - $Q=\left(m_{\mathrm{p}}+m_{\mathrm{e}}-m_{\mathrm{H}}\right) c^{2}$

  - Saha equation
    $$
    \frac{n_{\mathrm{H}}}{n_{\mathrm{p}} n_{\mathrm{e}}}=\left(\frac{m_{\mathrm{e}} k T}{2 \pi \hbar^{2}}\right)^{-3 / 2} \exp \left[\frac{Q}{k T}\right]
    $$
    Ionization fraction
    $$
    X \equiv \frac{n_{\mathrm{p}}}{n_{\mathrm{p}}+n_{\mathrm{H}}}=\frac{n_{\mathrm{p}}}{n_{\mathrm{b}}}=\frac{n_{\mathrm{e}}}{n_{\mathrm{b}}}\Rightarrow \frac{1-X}{X}=n_{\mathrm{p}}\left(\frac{m_{\mathrm{e}} k T}{2 \pi \hbar^{2}}\right)^{-3 / 2} \exp \left[\frac{Q}{k T}\right]
    $$

    $$
    \eta=\frac{n_\rm{b}}{n_\gamma}=\frac{n_\rm{p}}{Xn_\gamma}
    $$

    For a blackbody spectrum
    $$
    n_{\gamma}=\frac{2.404}{\pi^{2}}\left(\frac{k T}{\hbar c}\right)^{3}=0.244\left(\frac{k T}{\hbar c}\right)^{3}\Rightarrow n_{\mathrm{p}}=0.244 X \eta\left(\frac{k T}{\hbar c}\right)^{3}
    $$
    Solving the equation of $X$
    $$
    X=\frac{-1+\sqrt{1+4 S}}{2 S}
    $$
    where
    $$
    S(T, \eta)=3.84 \eta\left(\frac{k T}{m_{\mathrm{e}} c^{2}}\right)^{3 / 2} \exp \left[\frac{Q}{k T}\right]
    $$

  - When $kT\gg Q$, $X\sim1$

  - Once $kT<Q$, $X\to0$ - difficult to achieve for $\eta$ and $\left(k T / m_{\mathrm{e}} c^{2}\right)^{3 / 2}$ are very small

  - When $X=0.5$ and for $\eta=6.1\times10^{-10}$
    $$
    k T_{\mathrm{rec}}=0.323 \mathrm{eV}=\frac{Q}{42}
    $$

    $$
    T_{\mathrm{rec}}=0.323 \mathrm{eV} \equiv 3750 \mathrm{K},\ \left(1+z_{\mathrm{rec}}\right)=1375,\ t_{\mathrm{rec}}=251000\ \mathrm{yr}
    $$

## Photon Decoupling

- Recombination was not an instantaneous process - $X=0.9\to X=0.1$ takes $\sim 70000\text{ yr}$
- The time when photons and baryons decoupled follows soon
- Overionization ($X$ is larger than what the Saha equation predicts) - the photons emitted in recombination are so easily absorbed by other $\ce{H}$ atoms
- Two-photon emission
  - Highly forbidden
  - Energy of photons too low to excite an atom from the ground state
  - $z_\text{dec}=1090$
- CMB
  - Last scattering *layer*
  - Strong evidence for the Big Bang

## CMB

- $\langle h \nu\rangle= 6.3 \times 10^{-4} \mathrm{eV}$, $\sim$ vibrational and rotational levels of molecules
- Solution to Olbers' paradox - the sky at night is bright everywhere, but at the milimeter wavelength

### Isotropy

- Closest approximation to an ideal blackbody
  $$
  \langle T\rangle=\frac{1}{4 \pi} \int T(\theta, \phi) \sin \theta d \theta d \phi=2.7255 \pm 0.0006 \mathrm{K}
  $$

- Highly isotropic
  $$
  \frac{\delta T}{T}(\theta, \phi)=\frac{T(\theta, \phi)-\langle T\rangle}{\langle T\rangle}\Rightarrow \left\langle\left(\frac{\delta T}{T}\right)^{2}\right\rangle^{1 / 2}=1.1 \times 10^{-5}
  $$

#### Horizon Problem

- Comoving horizon
  $$
  s_{\text {hor}, \operatorname{com}(t)}=\int_{0}^{t} \frac{c \mathrm{d} t}{a(t)}=\int_{0}^{a} \frac{c \mathrm{d} a}{a^{2} H(a)}
  $$

- Early in the matter-dominated era
  $$
  H(a) \simeq H_{0} \sqrt{\Omega_{\mathrm{m}, 0}} a^{-3 / 2}\Rightarrow S_{\text {hor,}\text {com}}(a) \simeq \frac{c}{H_{0}} \Omega_{\mathrm{m}, 0}^{-1 / 2} \int_{0}^{a} \frac{1}{a^{1 / 2}} \mathrm{d} a
  $$

  $$
  s_{\mathrm{hor}, \operatorname{com}}(z) \simeq 2 \frac{c}{H_{0}} \Omega_{\mathrm{m}, 0}^{-1 / 2}(1+z)^{-1 / 2}
  $$

  Then the proper horizon distance at decoupling
  $$
  S_{\text {hor,prop}}\left(z_{\text {dec}}\right)= aS_{\text {hor,com}}\left(z_{\text {dec}}\right)\simeq 2 \frac{c}{H_{0}} \Omega_{\mathrm{m}, 0}^{-1 / 2}\left(1+z_{\mathrm{dec}}\right)^{-3 / 2}
  $$

- The angle on the sky subtended by the proper horizon
  $$
  \theta_{\text {hor,dec}}=\frac{s_{\text {hor}, \text {prop}}\left(z_{\text {dec}}\right)}{d_{\mathrm{A}}\left(z_{\text {dec}}\right)}
  $$
  where $d_\rm{A}$ is the angular diameter distance
  $$
  d_{\mathrm{A}}(z)=\frac{c}{H_{0}} \frac{1}{(1+z)} \int_{0}^{z} \frac{d z}{\left[\Omega_{\mathrm{m}, 0}(1+z)^{3}+\Omega_{\Lambda, 0}\right]^{1 / 2}}
  $$
  In an open universe with no dark energy, the so-called Mattig relation applies
  $$
  d_{\mathrm{A}}(z)=2 \frac{c}{H_{0}} \frac{1}{\Omega_{\mathrm{m}, 0}^{2}(1+z)^{2}} \left[\Omega_{\mathrm{m}, 0} z+\left(\Omega_{\mathrm{m}, 0}-2\right)\left(\sqrt{1+\Omega_{\mathrm{m}, 0} z}-1\right)\right]\approx2 \frac{c}{H_{0}} \frac{1}{\Omega_{\mathrm{m}, 0} z}
  $$
  for $z\gg1$, then
  $$
  \theta_{\mathrm{hor}, \mathrm{dec}} \approx\left(\frac{\Omega_{\mathrm{m}, 0}}{z_{\mathrm{dec}}}\right)^{1 / 2}=\left(\frac{0.312}{1090}\right)^{1 / 2}=0.017\ \mathrm{radians} \sim 1^{\circ}
  $$

- Under the cosmic model in consensus, $\theta_{\mathrm{hoor}, \mathrm{dec}} \approx 1.8^{\circ}$

- CMB photons coming to us from two directions separated by more than $\sim 2^\circ$ originated from regions which were not in causal contact at $z_\rm{dec}$

- Inflation



- After decoupling, the photo-baryon fluid cecame a pair of gases
  - Baryons - free gravitational collapse
  - Gravity turned the tiny temperature fluctuations into large scale structure
  - The anisotropies in the temperature of the CMB radiation encode a host of cosmological parameters

## Statistical Description of the Fluctuations

$$
\frac{\delta T}{T}(\theta, \phi)=\frac{T(\theta, \phi)-\langle T\rangle}{\langle T\rangle}=\sum_{\ell=0}^{\infty} \sum_{m=-\ell}^{\ell} a_{\ell}^{m} Y_{\ell}^{m}(\theta, \phi)
$$

- The correlation function
  $$
  C(\theta)=\left\langle\frac{\delta T}{T}(\mathbf{r}) \frac{\delta T}{T}\left(\mathbf{r}^{\prime}\right)\right\rangle_{\mathbf{r} \cdot \mathbf{r}^{\prime}=\cos \theta}=\frac{1}{4 \pi} \sum_{\ell=0}^{\infty}(2 \ell+1) C_{\ell} P_{\ell}(\cos \theta)
  $$

  - $C_\ell$ is a measure of $\delta T/T$ on the angular scale $\theta\sim180^\circ/\ell$
  - $\ell=0$ (monopole) - vanish
  - $\ell=1$ (dipole) - the motion of the Earth through space
  - $\ell\ge2$ - the fluctuations present at the time of last scattering

- Power spectrum
  $$
  \Delta_{\mathrm{T}}^{2} \equiv \frac{\ell(\ell+1)}{2 \pi} C_{\ell}\langle T\rangle^{2}
  $$

## Dipole

- Earth's motion relative to the local comoving frame of reference
  $$
  T(\theta) \approx\langle T\rangle\left(1+\frac{v}{c} \cos \theta\right)
  $$

## Higher Multipoles

### photon-baryon fluid acoustic oscillations

- $\theta\sim1^\circ$ - Sound horizon
- Baryon-photon fluid - relativistic
  - As gravity tries to compress the fluid, radiation pressure resists
    - Sound is a travelling change of pressure
    - Stops oscillating at decoupling - the pattern of maxima and minima in the density is frozen - temperature fluctuation
    - Maximum compression - highest density - hottest
  - Modes caught at extrema of their oscillations - the peaks in the CMB power spectrum - **Acoustic peaks** or **Doppler peaks**
    - First peak - compressed once inside potential wells before recombination
    - Second peak - compressed and then rarefied
    - Third peak - compressed then rarefied then compressed
    - ...
- The angular scales and amplitudes of the acoustic peaks are the main route to determining the cosmological parameters encoded in the temperature anisotropy of the CMB

### The First Doppler Peak: a Measure of the Curvature of the Universe
- EoS
  $$
  p=w \rho c^{2}
  $$
  Sound speed
  $$
  c_{\mathrm{s}}^{2}=\frac{d p}{d \rho}=\omega c^2
  $$
  For radiation, $\omega=1/3\Rightarrow c_\mathrm{s}=c/\sqrt{3}$

- Sound horizon
  $$
  s_{\mathrm{hor}, \mathrm{s}} \simeq \frac{2}{\sqrt{3}} \frac{c}{H_{0}} \Omega_{\mathrm{m}, 0}^{-1 / 2}\left(1+z_{\mathrm{dec}}\right)^{-3 / 2}
  $$
  For $z\gg1$ and $\Omega_\Lambda=0$
  $$
  \theta_{\mathrm{hor}, \mathrm{s}} \simeq \frac{1}{\sqrt{3}}\left[\frac{\left(1-\Omega_{\mathrm{k}, 0}\right)}{z_{\mathrm{dec}}}\right]^{1 / 2}
  $$

- **Larger $\Omega_{\text{k},0}$ gives smaller $\theta_{\mathrm{hor}, \mathrm{s}}$, thus the first acoustic peak moves to larger $\ell$ values**

- In a $\Omega_{\mathrm{k}, 0}=0, \Omega_{\mathrm{m}, 0}+\Omega_{\Lambda, 0}=1$ cosmology, we expect the first peak is located at
  $$
  \theta_{\mathrm{hor}, s} \approx \frac{1.8^{\circ}}{\sqrt{3}} \simeq 1^{\circ}
  $$

## Higher Doppler Peaks

- Inside the sound horizon at decoupling - subject to physical effects acting on baryon-photon fluid

### Baryon Loading: a Measure of $\Omega_{\mathrm{b}, 0}$

- Baryon loading - take the gravitational and inertial mass of the baryons into account

  - Higher amplitude of compression peaks (odd peaks) than rarefaction peaks (even peaks)
    - The fluid compress further inside before rarefactions

  - Decrease the frequency of oscillations
    - Slowed down by baryons - the wavelength decays as the velocity stays a constant
    - All the peaks get slightly higher $\ell$ (smaller $\theta$)

### The Damping Tail

- As we approach the epoch of decoupling, the coupling between baryons and photons is not perfect
  - Anisotropies removed by diffusion of photons (with higher mean free path)
  - The acoustic oscillations are exponentially damped on scales smaller than the distance photons random walk
- The shape of the damping tail
  - Increasing the baryon density 
    - The photon-baryon fluid more tightly coupled at recombination
    - The mean free path of the photons is shorter
    - The damping tail shifts to smaller angular scales
  - Total matter density
    - The age of the Universe at $z_\text{rec}$
    - Angular diameter distance $d_\rm{A}$
    - Both are smaller for larger matter density - more damping at a fixed multiple moment

## Super-horizon Scales

- The principal source of temperature fluctuations are the intrinsic inhomogeneities in the distribution of matter

### Sachs-Wolfe Effect

- Variations in the gravitational potential - temperature fluctuation
  $$
  \left(\frac{\delta T}{T}\right)_{\mathrm{S}-\mathrm{W}}=\frac{1}{3} \frac{\delta \Phi}{c^{2}}
  $$

- Two competing effects

  - Photons climbing out of potential well experience a gravitational redshift, and lose energy in the process
    - The potential wells appear slightly colder than the mean in the CMB map
  - Photons scattered from regions of higher density than average and received today were scattered at slightly earlier times, when the CMB temperature was slightly higher - what we see is earlier CMB
    - The potential wells appear slightly hotter than the mean in the CMB map

- No scale dependence

  - A constant $\Delta_{\mathrm{T}}^{2}$ in power spectrum

- Cosmic variance

  - Only $2\ell+1$ independent sampling can be made of our CMB sky

  - Limit of precision
    $$
    \left(\frac{\Delta C_{\ell}}{C_{\ell}}\right)^{2}=\frac{2}{2 \ell+1}
    $$

### Peculiar Velocities

- Density fluctuations are always related to peculiar velocities of matter

- Photons last scattered by gas receding from us with a speed slightly larger
  than the average Hubble expansion will experience an additional redshift which reduces the temperature measured in that direction
  $$
  \left(\frac{\delta T}{T}\right)_{\mathrm{v}, \mathrm{pec}}=\frac{1}{3} \frac{\delta \Phi}{c^{2}} \frac{\theta_{\mathrm{hor}, \mathrm{rec}}}{\theta}\Rightarrow \Delta_{\mathrm{T}}^{2} \propto \theta^{-1}
  $$

## Secondary Fluctuations

### Thomson Scattering

- Free electrons in IGM, following the so-called epoch of reionization
- The fluctuation amplitude decreases by a factor of $e^{-\tau}$ - help deduce $z_\text{reion}\approx8.5\pm1.3$

### Gravitational Lensing

- The gravitational field of the cosmic density fluctuations leads to changes in the photon direction
- The correlation function of the temperature fluctuations is slightly smeared out on small angular scales

###  Integrated Sachs-Wolfe effect

- The gravitational potential of the large-scale structure changes over timescales comparable to the travel time of CMB photons through the structures
  - Important over the largest angular scales and when dark energy dominates the expansion
- The blueshift that a CMB photon undergoes as is travels down a potential well is more significant than the corresponding redshift as it climbs out

### The Sunyaev-Zel’dovich (S-Z) Effect

- Inverse Compton scattering of CMB photons by electrons in the intracluster gas (ICM) of massive galaxy clusters

- The **isotropy** of the cosmic background ensures that, on average, the total number of CMB photons reaching us is unchanged

- Frequency distribution

  - Raleigh-Jeans part ($\lambda\ge1\text{ mm}$) - removed
  - Wien part - boosted

- Intensity - related to the physical properties of the cluster
  $$
  \frac{\Delta I_{\nu}^{\mathrm{RJ}}}{I_{\nu}^{\mathrm{RJ}}}=-2 y
  $$
  where
  $$
  y=\int \frac{k T}{m_{\mathrm{e}} c^{2}} \sigma_{\mathrm{T}} n_{\mathrm{e}} \mathrm{d} l
  $$

  - Independent of redshift and of the details of the gas distribution within the cluster - identification of clusters at high redshifts