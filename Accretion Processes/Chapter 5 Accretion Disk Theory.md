# Chapter 5. Accretion Disk Theory

## General Picture

The inflowing has a non-zero angular momentum and forms a disk. For a specific angular momentum, $j_0=rv$. Let us ignore the pressure for this moment, and compare the gravity and centrifugal force,
$$
\frac{GM}{r^2}\sim\frac{j_0^2}{r^3}
$$
At a small radius, to conserve the specific angular momentum, the centrifugal term must dominate. The critical radius is
$$
R_\text d\equiv\frac{j_0^2}{GM}
$$
It is known as the **disk radius**, or the **centrifugal radius**. It corresponds to the radius within which a disk could form due to the net angular momentum from the accreted gas.

- **Estimation of $R_\text d$** 

  At any radius, the accreted gas has a random motion velocity of the order of the adiabatic sound speed $c_s$. The effective tangential velocity component $v$ is scaled with an order-one factor $f$, $v\sim fc_s$.

  In addition, the accretion starts at Bondi radius,
  $$
  r\lesssim R_B\sim\frac{GM}{c_\infty^2}
  $$
  Consequently,
  $$
  j_0=rv\sim R_B\cdot fc_\infty\sim f\frac{GM}{r_\infty}\Rightarrow R_\text d\sim f^2 R_B=10^{-2}\left(\frac{f}{0.1}\right)^2R_B
  $$
  Usually $f\sim0.1$, so $R_\text d$ is two orders of magnitude smaller than the Bondi radius.

  - **Black Hole**

    The so-called *surface* of the object is the event horizon, whose size is approximately Schwarzschild radius
    $$
    R_{Sch}=\frac{2GM}{c^2}=\frac{2c_\infty^2}{c^2}R_B
    $$
    For HI gas, $c_s\sim10$ km/s, thus for $f\sim0.1$
    $$
    R_{Sch}\sim10^{-9}R_B\ll R_\text d\ll R_B
    $$

  - **Sun-like Star**

    Again for $f\sim0.1$, 
    $$
    R_B\sim10^{3}R_\odot,\quad R_\text d\sim10 R_\odot,\quad R_*\sim R_\odot
    $$

The disk is, obviously, axisymmetric. All our discussion below will be in the cylindrical coordinate $(r,z)$. $z=0$ corresponds to the **equator** of the disk.



### Profile along $z-$Direction

Along $z-$direction, pressure gradient is balanced with gravity.
$$
\frac{c_s}{\rho}\frac{\text d\rho}{\text dz}=-\frac{GM}{r^2+z^2}\frac{z}{\left(r^2+z^2\right)^{1/2}}
$$
Fix $r$, and consider isothermal case in which $c_s=c_0$ for simplicity, we can solve this ODE simply by integration
$$
c_0^2\ln\rho=\frac{GM}{\left(r^2+z^2\right)^{1/2}}+C\Rightarrow \rho(r,z)=f(r)\exp\left[\frac{GM}{c_0^2\left(r^2+z^2\right)^{1/2}}\right]
$$
For $z\ll r$, we can expand the exponential index into Taylor series
$$
\frac{GM}{c_0^2\left(r^2+z^2\right)^{1/2}}=\frac{GM}{c_0^2r}\left(1-\frac12\frac{z^2}{r^2}\right)
$$
Define
$$
\tilde f(r)\equiv f(r)\exp\left(\frac{GM}{c_0^2r}\right)
$$
we have
$$
\rho(r,z)=\tilde f(r)\exp\left(-\frac12\frac{GM}{c_0^2r^3}z^2\right)\equiv\tilde f(r)\exp\left(-\frac12\frac{\Omega_K^2}{c_0^2}z^2\right)
$$
where $K$ denotes for *Keplerian*. We can further define
$$
H\equiv\frac{c_0}{\Omega_K}
$$
and the $\rho(r,z)$ develops a Gaussian profile
$$
\rho(r,z)=\tilde f(r)\exp\left(-\frac12\frac{z^2}{H^2}\right)
$$
$H$ is the **disk scale height**, which corresponds to the disk thickness.

Now we need to think of the ratio of $H$ to $r$. Only if $H/r\ll1$ is our assumption that $z\ll r$ self-consistent.
$$
\frac Hr=\frac{c_s}{\Omega_Kr}=\frac{c_s}{v_K}\sim \mathcal M^{-1}\ll1\iff\mathcal M\gg1
$$
Thus we claim that the **thin disk** is equivalent to a **cold disk**, where the thermal velocity is much smaller than the rotational velocity.



### Gas Rotation in the Disk

Consider the terms of the Navier-Stokes equation in $r-$direction,
$$
\frac{\partial v_r}{\partial t}+v_r\frac{\partial v_r}{\partial r}-\frac{v_\phi^2}{r}=-\frac1\rho\frac{\partial P}{\partial r}-\frac{GM}{r^2}+\left[\nabla\cdot \sigma\right]_r
$$
In the steady state, the time derivative vanishes. If there is no viscosity, due to the conservation of angular momentum, there should not be any mass inflow and materials simply rotate, thus $v_r=0$. So
$$
\frac{v_\phi^2}{r}=\frac1\rho\frac{\partial P}{\partial r}+\frac{GM}{r^2}=\frac{c_s^2}\rho\frac{\partial \rho}{\partial r}+\frac{GM}{r^2}\Rightarrow v_\phi^2=\frac{\partial\ln\rho}{\partial\ln r}c_s^2+v_K^2
$$
For a thin disk, $c_s\ll v_K$, and $v_\phi$ is simply the Keplerian velocity. But for a relatively thick disk,
$$
v_\phi=v_K\sqrt{\frac{\partial\ln\rho}{\partial\ln r}\frac{c_s^2}{v_K^2}+1}=v_K\sqrt{\frac{\partial\ln\rho}{\partial\ln r}\frac{H^2}{r^2}+1}
$$
Usually the density gradient is negative, so the rotation is **sub-Keplerian**, where $v_\phi<v_K$. But there could be some regions where the density gradient is positive. The rotation in such region is **super-Keplerian**.

In fact, the radial velocity is led by the viscosity. Dimensional analysis gives that
$$
v_r\sim\frac\nu r
$$
In accretion disks, the consensus is that viscosity comes from turbulence excited by magnetorotational instability (MRI). We know that the kinematic viscosity $\nu$ is determined as
$$
\nu=\bar cl_\text{mfp}=\bar cL_\text{tur}
$$
where $\bar c$, here the turbulence velocity, is of the same order as $c_s$. On the other hand, the turbulence scale has a upper limit, which is the disk scale height $H$. As a result,
$$
\nu\sim c_sH
$$
In 1973, Shakura & Sunyaev proposed a trick by introducing a factor $\alpha$ so that
$$
\nu=\alpha c_sH
$$
throughout the disk. Though they have no idea of the physical origin for $\alpha-$viscosity, recent MHD simulations for MRI proves that although $\alpha$ is a time-dependent, local parameter, the variation is reasonable and the average $\alpha$ is somehow $0.001-0.01$.

With this assumption, the inflow velocity is
$$
v_r\sim\frac\nu r\sim\alpha\left(\frac Hr\right)c_s\sim\alpha\left(\frac Hr\right)^2v_K^2
$$
So $v_r\ll c_s\ll v_K$ for thin disks.



### Energy Production

In a axisymmetric accretion system, the accretion rate is
$$
\dot M=2\pi rv_r\Sigma
$$
where
$$
v_r\Sigma\equiv\int_{-H}^Hv_r(r,z)\rho(r,z)\text dz
$$
In the thin disk limit, $v_r(r,z)\sim v_r(r)$, thus
$$
\Sigma\equiv\int_{-H}^H\rho(r,z)\text dz
$$
$\Sigma$ is the **surface density** on the disk. Using our estimation of $v_r$, we have
$$
\dot M\sim 2\pi r\cdot\frac \nu r\cdot\Sigma\sim\nu\Sigma
$$
Now we can calculate the energy generation rate (**[erg/s/cm$^2$], energy flux**) due to accretion, during which gravitational energy is transformed into thermal energy via visocity.
$$
Q^+_\text{vis}\sim\frac1{\pi r^2}\cdot\frac{GM}r\cdot\dot M\sim\nu\Sigma\Omega_K^2
$$
This relation can be derived from Navier-Stokes equation directly. In fact,
$$
Q^+_\text{vis}\sim\nu\Sigma\left(\frac{\text d\Omega}{\text d\ln r}\right)^2\sim\frac94\nu\Sigma\Omega_K^2
$$
The energy is carried away mainly via radiation, convection, and advection. The convection can be important, but is really complicated and beyond the scope of this lecture. Here we mainly discuss advection and radiation.

**Advection**

In advection, the bulk fluid motion carries certain energy away. Again, out of dimensional analysis, we have
$$
Q^-_\text{adv}\sim\frac1{\pi r^2}\cdot \dot Mc_s^2
$$
where $\dot M$ describes the bulk motion and the specific internal energy is scaled with $c_s^2$. The ratio of $Q^-_\text{adv}$ to $Q^+_\text{vis}$ is
$$
\frac{Q^-_\text{adv}}{Q^+_\text{vis}}\sim\frac{\dot Mc_s^2}{\frac{GM}r\dot M}\sim\frac{c_s^2}{v_K^2}\ll1
$$
which suggests that for thin disk case, advection cannot efficiently takes energy away. For thicker disks, however, advection can play an important role in energy transportation.

**Radiation**

In a **geometrically thin disk**, we estimate the optical depth $\tau$.
$$
\tau\sim\frac12\kappa\Sigma\sim\frac12\kappa\frac{\dot M}{2\pi rv_r}
$$
We consider the fluid behavior in the vicinity of the black hole, that is, $r\sim R_{Sch}$. Because of the steep potential well predicted in GR, the infalling velocity is approximately the speed of light. In this way,
$$
\tau\sim\frac12\frac{\dot Mc^2}{4\pi GMc/\kappa}\sim\frac12\frac{\dot Mc^2}{L_{Edd}}\sim\frac1{2\eta}\frac{\dot M}{\dot M_{Edd}}
$$
For a typical efficiency $\eta\sim0.1$, when $\dot M\sim\dot M_{Edd}$, $\tau$ is significantly larger than unity. Note that $c$ is strictly an upper limit of $v_r$, so we have underestimated the optical depth. Absolutely the disk is **optically thick**. So the energy transporting rate via radiation is
$$
Q^-_\text{rad}\sim\frac{\sigma_{SB}T^4}{\tau}
$$
