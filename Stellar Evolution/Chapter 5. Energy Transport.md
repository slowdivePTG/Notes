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

*But how can we know the opacity?*



### Rosseland mean opacity

In general, there are so many sources of opacity $\kappa_\nu(\rho,T)$ like scattering and absorption.

- Electron scattering
  $$
  \kappa=\kappa_e=0.35\text{ cm}^2\text{/g}
  $$

- Free-free transition (bremsstrahlung)
  $$
  k_\nu^\text{ff}\sim f(\nu)\rho T^{-7/2}
  $$
  ![5_1](/Users/chang/Desktop/Stellar Evolution/5_1.png)

  >From Fengwei Xu's notes

For each $\nu$, the radiation flux is
$$
F_\nu=-\frac{c}{3\rho \kappa_\nu}\frac{\partial}{\partial r}U_{\text{rad},\nu}
$$
where $U_\nu$ is given by $4\pi B_\nu(T)/c$,
$$
B_\nu(T)=\frac{2h\nu^3}{c^2}\frac{1}{\exp{(h\nu/kT)}-1}
$$
Thus
$$
F_\nu=-\frac{4\pi}{3\rho \kappa_\nu}\frac{\partial B_\nu(T)}{\partial T}\frac{\partial T}{\partial r}
$$
Obviously,
$$
\frac1{\kappa_\nu}\frac{\partial B_\nu(T)}{\partial T}
$$
is $\nu$-denpendent, thus we can define the **Rosseland mean opacity** as
$$
\frac1{\kappa_R}\equiv\frac{\int\frac{1}{\kappa_\nu}\frac{\partial B_\nu(T)}{\partial T}\text d\nu}{\int\frac{\partial B_\nu(T)}{\partial T}\text d\nu}
$$
Note that by integrating $B_\nu(T)$ over the frequency the integrated radiance $L$ is
$$
L=\frac{2 \pi^{5}}{15} \frac{k^{4} T^{4}}{c^{2} h^{3}} \frac{1}{\pi}=\sigma_\text{SB} T^{4} \frac{1}{\pi}
$$
Thus
$$
\int\frac{\partial B_\nu(T)}{\partial T}\text d\nu=\frac{\partial}{\partial T}\left(\sigma_\text{SB} T^4\right)=\frac{ac}{\pi}T^3
$$
Then
$$
{\int\frac{1}{\kappa_\nu}\frac{\partial B_\nu(T)}{\partial T}\text d\nu}=\frac1{\kappa_R}\frac{ac}{\pi}T^3
$$
In this way,
$$
F=-\frac{4ac}{3\rho \kappa_R}T^3\frac{\partial T}{\partial r}
$$

## Convection

Discussed in the next chapter.



## Conduction

- Not important for normal stars
- Important for compact stars

Energy is transported via collision due to thermal motions of particles. Although the physics is different from radiation transport, the flux is simply given by
$$
F_\text{cd}=-k_\text{cd}(T,\rho)\nabla T
$$
So for a star without significant convection, the total energy flux is
$$
F_\text{tot}=F_\text{rad}+F_\text{cd}=-\left(k_\text{rad}+k_\text{cd}\right)\nabla T
$$
