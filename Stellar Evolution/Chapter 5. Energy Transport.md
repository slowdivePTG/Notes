# Chapter 5. Energy Transport

How is energy generated in the core transported to the surface?

- Radiation: photons
- Convection: fluid motions
- Conduction: electrons, atoms

## Radiation

The sun ($\bar\rho_\odot\sim 1.4\text{ g/cm}^3,\ \bar n_\odot\sim10^{24}\text{ cm}^{-3}$) is **optically thick**, that is, when we solely consider Thomson scattering (photons v.s. electrons), the mean free path for a photon is
$$
l_\text{mfp, photons}\simeq\frac{1}{n\sigma_\text{T}}\sim 1\text{ cm}\ll R_{\odot}\sim 7\times10^{10}\text{ cm}
$$
Therefore, photons must be scattered many times before reaching the surface, and energy is radiated by **diffusion**.

- **Diffusion**

  An example is that particles tend to escape from dense regions to the places with lower number density. The particle **flux** is approximately proportional to the density gradient
  $$
  \vec j=\rho\vec u\simeq-D\nabla n
  $$
  where $D$ is the **diffusion coefficient**
  $$
  D\sim\frac13\bar \mu l_\text{mfp},\text{ where } \bar\mu=\sqrt{\frac{kT}{\mu m_\text p}}
  $$
  Larger $l_\text{mfp}$ results in larger diffusion rate.

### Radiation Energy

$$
U_\text{rad}=aT_\text{rad}^4
$$

where $a$ is the **radiation coefficient** derived from the **Stefan–Boltzmann constant**
$$
\sigma_\text{SB}=\frac{ac}4
$$

> In a star, radiation and gas are thermalized due to numerous collisions, thus $T_\text{rad}\simeq T$.

We can similarly write down the **radiation energy flux** as
$$
F_\text{rad}=-D\nabla U_\text{rad}
$$
where
$$
D\simeq\frac{1}{3}cl_\text{mfp}=\frac13\frac{c}{n\sigma_\text{T}}\equiv\frac{c}{3\rho\kappa}
$$
Here we have defined the **opacity** $\kappa$ as
$$
\kappa\equiv\frac{\sigma_\text{T}}{m}
$$
For a spherical system (such as a star), the gradient is simply ${\partial}/{\partial r}$, thus
$$
F_\text{rad}=-\frac{4ac}{3\rho\kappa}T^3\frac{\partial T}{\partial r}
$$
The **luminosity** is
$$
L=4\pi r^2 F_\text{rad}=-\frac{16ac\pi r^2ac}{3\rho\kappa}T^3\frac{\partial T}{\partial r}=-\frac{64ac\pi^2 r^4}{3\kappa}T^3\frac{\partial T}{\partial m}
$$
